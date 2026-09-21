# Sample output: Billing Bug Fix & Independent Review

Text output of a production run on 2026-09-16, unedited (total model cost $0.29).
---

📄 Generated Text:

There are two defects in `monthly_recurring_revenue`.

### 1. `past_due` subscriptions are incorrectly excluded

The line `if sub.status != "active":` allows only `"active"` subscriptions through.

The definition requires both `"active"` and `"past_due"` subscriptions to count, while `"trialing"` and `"canceled"` must be excluded.

Affected customers:

- **C-03** is `"past_due"` and currently contributes $0. Its required MRR is `15.00 × 4 = $60.00`, so the defect understates MRR by **$60.00**.
- **C-04** is `"past_due"` and currently contributes $0. Its required MRR is `(150.00 × 8 ÷ 12) × 80% = $80.00`, so the defect understates MRR by **$80.00**.

The status defect therefore accounts for **$140.00** of missing MRR.

It correctly excludes C-06 (`"canceled"`) and C-07 (`"trialing"`).

### 2. Annual subscriptions omit the seat count

The line `amount = sub.seat_price / 12` divides one seat’s annual price by 12 but never multiplies by `sub.seats`.

The definition requires the annual monthly amount to be `seat_price × seats ÷ 12`, before applying the discount.

For subscriptions that actually reach this line:

- **C-02** currently contributes `144.00 ÷ 12 = $12.00`. It should contribute `144.00 × 10 ÷ 12 = $120.00`. The defect understates MRR by **$108.00**.
- **C-08** currently contributes `(99.00 ÷ 12) × 85% = $7.0125`. It should contribute `(99.00 × 7 ÷ 12) × 85% = $49.0875`. The exact understatement is **$42.075**, equivalent to **$42.08** when viewed at cent precision.

C-04 is also an annual multi-seat subscription, but the status defect prevents it from reaching this line. Its entire current-output shortfall is therefore assigned to the status defect above; counting an additional annual-formula effect for C-04 would double-count the same missing revenue.

### Reconciliation

The function’s unrounded total is:

- C-01: $180.00
- C-02: $12.00
- C-05: $337.50
- C-08: $7.0125

Total: `$536.5125`, rounded half-up to **$536.51**.

The required unrounded total is:

- C-01: $180.00
- C-02: $120.00
- C-03: $60.00
- C-04: $80.00
- C-05: $337.50
- C-06: $0
- C-07: $0
- C-08: $49.0875

Total: `$826.5875`, rounded half-up to **$826.59**.

The exact missing amount is:

`$60.00 + $80.00 + $108.00 + $42.075 = $290.075`

Equivalently:

`$826.5875 - $536.5125 = $290.075`

After each total is rounded half-up to cents:

`$826.59 - $536.51 = $290.08`

Thus, the two defects account for the entire **$290.08** displayed difference.

---

💻 Code:

```python
from dataclasses import dataclass
from decimal import ROUND_HALF_UP, Decimal


@dataclass(frozen=True)
class Subscription:
    customer_id: str
    plan: str             # "monthly" or "annual"
    seat_price: Decimal   # price of one seat for one billing period
    seats: int
    status: str           # "active", "past_due", "trialing", or "canceled"
    discount_pct: int     # whole-number percent, 0-100


def monthly_recurring_revenue(subscriptions: list[Subscription]) -> Decimal:
    """Monthly recurring revenue in dollars, rounded half-up to the cent."""
    total = Decimal("0")
    for sub in subscriptions:
        if sub.status not in ("active", "past_due"):
            continue
        if sub.plan == "annual":
            amount = sub.seat_price * sub.seats / 12
        else:
            amount = sub.seat_price * sub.seats
        amount = amount * (100 - sub.discount_pct) / 100
        total += amount
    return total.quantize(Decimal("0.01"), rounding=ROUND_HALF_UP)
```

Changed status filtering to include both active and past-due subscriptions. Changed annual-plan calculation to multiply the seat price by the seat count before dividing by 12.

---

💻 Code:

```python
from decimal import Decimal

import pytest

from billing_mrr import Subscription, monthly_recurring_revenue


def subscription(
    *,
    customer_id: str = "test-customer",
    plan: str = "monthly",
    seat_price: str = "10.00",
    seats: int = 1,
    status: str = "active",
    discount_pct: int = 0,
) -> Subscription:
    return Subscription(
        customer_id=customer_id,
        plan=plan,
        seat_price=Decimal(seat_price),
        seats=seats,
        status=status,
        discount_pct=discount_pct,
    )


def test_eight_subscriptions_total_826_59() -> None:
    subscriptions = [
        subscription(
            customer_id="C-01",
            plan="monthly",
            seat_price="15.00",
            seats=12,
            status="active",
            discount_pct=0,
        ),
        subscription(
            customer_id="C-02",
            plan="annual",
            seat_price="144.00",
            seats=10,
            status="active",
            discount_pct=0,
        ),
        subscription(
            customer_id="C-03",
            plan="monthly",
            seat_price="15.00",
            seats=4,
            status="past_due",
            discount_pct=0,
        ),
        subscription(
            customer_id="C-04",
            plan="annual",
            seat_price="150.00",
            seats=8,
            status="past_due",
            discount_pct=20,
        ),
        subscription(
            customer_id="C-05",
            plan="monthly",
            seat_price="15.00",
            seats=25,
            status="active",
            discount_pct=10,
        ),
        subscription(
            customer_id="C-06",
            plan="monthly",
            seat_price="15.00",
            seats=3,
            status="canceled",
            discount_pct=0,
        ),
        subscription(
            customer_id="C-07",
            plan="annual",
            seat_price="144.00",
            seats=1,
            status="trialing",
            discount_pct=0,
        ),
        subscription(
            customer_id="C-08",
            plan="annual",
            seat_price="99.00",
            seats=7,
            status="active",
            discount_pct=15,
        ),
    ]

    assert monthly_recurring_revenue(subscriptions) == Decimal("826.59")


def test_regression_past_due_subscription_is_included() -> None:
    subscriptions = [
        subscription(
            plan="monthly",
            seat_price="15.00",
            seats=4,
            status="past_due",
        )
    ]

    assert monthly_recurring_revenue(subscriptions) == Decimal("60.00")


def test_regression_annual_plan_multiplies_by_seats() -> None:
    subscriptions = [
        subscription(
            plan="annual",
            seat_price="144.00",
            seats=10,
        )
    ]

    assert monthly_recurring_revenue(subscriptions) == Decimal("120.00")


@pytest.mark.parametrize(
    ("status", "expected"),
    [
        ("active", Decimal("10.00")),
        ("past_due", Decimal("10.00")),
        ("trialing", Decimal("0.00")),
        ("canceled", Decimal("0.00")),
    ],
)
def test_status_rule(status: str, expected: Decimal) -> None:
    subscriptions = [subscription(status=status)]

    assert monthly_recurring_revenue(subscriptions) == expected


@pytest.mark.parametrize(
    ("plan", "seat_price", "seats", "expected"),
    [
        ("monthly", "7.00", 2, Decimal("14.00")),
        ("annual", "24.00", 3, Decimal("6.00")),
    ],
)
def test_monthly_amount_rule(
    plan: str,
    seat_price: str,
    seats: int,
    expected: Decimal,
) -> None:
    subscriptions = [
        subscription(
            plan=plan,
            seat_price=seat_price,
            seats=seats,
        )
    ]

    assert monthly_recurring_revenue(subscriptions) == expected


def test_discount_percentage_rule() -> None:
    subscriptions = [
        subscription(
            seat_price="10.00",
            discount_pct=25,
        )
    ]

    assert monthly_recurring_revenue(subscriptions) == Decimal("7.50")


def test_decimal_result_and_half_up_rounding_at_exactly_half_a_cent() -> None:
    subscriptions = [subscription(seat_price="0.005")]

    result = monthly_recurring_revenue(subscriptions)

    assert isinstance(result, Decimal)
    assert result == Decimal("0.01")
```

---

📄 Generated Text:

## Statement on method

No code was executed anywhere in this workflow. Everything below is a hand check of the arithmetic and a reading of the source; it is not a test run, and I make no claim that any test passes.

## Hand trace of the eight subscriptions through the patched function

| Cust | status → kept? | branch | pre-discount amount | ×(100−d)/100 | contribution |
|---|---|---|---|---|---|
| C-01 | active → yes | monthly | 15.00×12 = 180.00 | ×100/100 | 180.00 |
| C-02 | active → yes | annual | 144.00×10/12 = 120.00 | ×100/100 | 120.00 |
| C-03 | past_due → yes | monthly | 15.00×4 = 60.00 | ×100/100 | 60.00 |
| C-04 | past_due → yes | annual | 150.00×8/12 = 100.00 | ×80/100 | 80.00 |
| C-05 | active → yes | monthly | 15.00×25 = 375.00 | ×90/100 | 337.50 |
| C-06 | canceled → no | — | — | — | 0 |
| C-07 | trialing → no | — | — | — | 0 |
| C-08 | active → yes | annual | 99.00×7/12 = 57.75 | ×85/100 | 49.0875 |

Sum = 826.5875; `quantize(Decimal("0.01"), ROUND_HALF_UP)` → **826.59**. Confirmed. Every division here is exact (1440/12, 1200/12, 693/12), so no context-precision rounding occurs in this dataset.

## Patch check

Both diagnosed defects are fixed: the status guard is now `not in ("active", "past_due")`, and the annual branch is `seat_price * seats / 12`. The multiplication is written before the division, so precision is not needlessly degraded. No new defect introduced: no per-subscription rounding was added, `total` still starts as `Decimal("0")`, and the single `quantize` remains at the end. No float appears anywhere — no float literals, no `float()`, no `round()`; only `Decimal`, `int`, and `int`-valued arithmetic, and `Decimal / int` and `Decimal * int` stay in `Decimal`.

## Generated tests against the **original** code

| Test | Result vs original | Is that the correct result? | Regression value |
|---|---|---|---|
| `test_eight_subscriptions_total_826_59` | 536.51 ≠ 826.59 → fail | correct to fail | catches both defects |
| `test_regression_past_due_subscription_is_included` | 0.00 ≠ 60.00 → fail | correct to fail | catches status defect |
| `test_regression_annual_plan_multiplies_by_seats` | 12.00 ≠ 120.00 → fail | correct to fail | catches annual defect |
| `test_status_rule[active]` | 10.00 → pass | correct (spec-conforming) | none |
| `test_status_rule[past_due]` | 0.00 ≠ 10.00 → fail | correct to fail | catches status defect |
| `test_status_rule[trialing]` | 0.00 → pass | correct | none |
| `test_status_rule[canceled]` | 0.00 → pass | correct | none |
| `test_monthly_amount_rule[monthly]` | 14.00 → pass | correct | none |
| `test_monthly_amount_rule[annual]` | 2.00 ≠ 6.00 → fail | correct to fail | catches annual defect |
| `test_discount_percentage_rule` | 7.50 → pass | correct | none |
| `test_decimal_..._half_a_cent` | 0.01, Decimal → pass | correct | none |

Six of eleven cases would pass unchanged against the buggy original. That is legitimate — they pin spec clauses the original already met — but it means only five cases actually guard the fix. All eleven match the patched behaviour by my hand trace.

## Findings by severity

**Medium**

1. *Unknown `plan` value is silently billed as monthly.* `plan == "annual"` else monthly means `"Annual"`, `"yearly"`, or `"quarterly"` is charged 12× the intended monthly amount — a revenue bug of the same family as the one just fixed. Untested; consider raising `ValueError` on unrecognised plans and adding a test.
2. *Unknown `status` value is silently dropped.* `"unpaid"`, `"ACTIVE"`, or a typo contributes zero with no signal, which understates MRR exactly as the original defect did. Untested.
3. *Non-terminating annual division is untested.* An annual amount not divisible by 12 (e.g. 100.00 for one seat → 8.333…) relies on the 28-digit default context and end-only rounding; no test pins that per-subscription rounding is *not* applied, so a future "tidy-up" could reintroduce cent drift undetected.

**Low**

4. *Empty input untested.* The function should return `Decimal("0.00")`; worth one assertion.
5. *`discount_pct` boundaries untested.* 0 is covered implicitly, but 100 (→ zero contribution) is not, and out-of-range values (negative, >100) are neither validated nor tested; a negative percent would silently inflate MRR.
6. *`seats = 0` or negative untested.* Currently contributes zero or negative revenue without complaint.
7. *No half-up tie test on an aggregate total.* The 826.5875 case rounds up on a 7, not a tie; only a single-subscription 0.005 tie is exercised. A two-subscription sum landing exactly on …5 would be a stronger check.
8. *Style.* The status tuple could be a module-level `frozenset` constant for clarity; purely cosmetic.

## Verdict

**Approve with changes.** The patch is correct against the specification, reproduces $826.59 by hand, and uses no float. Before merge, add tests for the empty list, `discount_pct = 100`, and a non-terminating annual division, and decide explicitly whether an unrecognised `plan` or `status` should raise rather than fall through silently (findings 1 and 2).
