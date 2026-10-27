# LOAN_API — Data Model

[← Overview](index.md) · [API Reference](api.md) · [Dependencies](dependencies.md)

This is a **source-observed access register**. Observed joins do not establish DDL foreign keys.

| Database object | Observed operation | Role / use | Public API |
|---|---|---|---|
| `KRD_TEKLIF_DETAY` | SELECT | Loan identity, status, line type, end date, offer and limit configuration | [evaluate_limit_amount](api.md#evaluate-limit-amount) |
| `CS_ACCOUNT` | SELECT | Loan account balances and limit account values | [evaluate_limit_amount](api.md#evaluate-limit-amount) |
| `LOAN_CATEGORY` | SELECT | Check active category 667 used for limit evaluation | [evaluate_limit_amount](api.md#evaluate-limit-amount) |
| `LOAN_OPERATION_HISTORY` | SELECT | Prior tranche amounts and history metadata | [evaluate_limit_amount](api.md#evaluate-limit-amount), [reverse_update](api.md#reverse-update) |
| `LOAN_ACC_TYPES_PR` | SELECT | Eligibility and payment-plan account grouping | [post_int_amount_to_plan](api.md#post-int-amount-to-plan) |
| `LOAN_PAYMENT_PLAN` | SELECT, UPDATE | Standard repayment schedule and interest posting | [post_int_amount_to_plan](api.md#post-int-amount-to-plan), [get_amount_for_pen_calc](api.md#get-amount-for-pen-calc-1) |
| `LOAN_TRANCHE_PAYMENT_PLAN` | SELECT, UPDATE | Tranche-specific repayment schedule | [post_int_amount_to_plan](api.md#post-int-amount-to-plan) |
| `KRD_GUARANTEE_MAIN`, `KRD_GUARANTEE_RELATIONS`, `KRD_GUARANTEE_C1` | SELECT | Qualifying guarantee commitments excluded from the penalty base when enabled | [get_amount_for_pen_calc](api.md#get-amount-for-pen-calc-1) |

## Important qualifications

- Operations above are verified **for the cited methods**, not a complete database-access inventory for all 89 public declarations.
- `evaluate_limit_amount` posts journal entries through [do_journal_entry](api.md#do-journal-entry); this is not represented as a direct INSERT by the caller.
- Reconcile actual primary keys, foreign keys, triggers and indirect package effects against target-schema DDL before treating this as a physical model.
