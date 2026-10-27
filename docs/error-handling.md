# Error Handling — LOAN_API

> **Status:** Draft. These messages and conditions are observed in supplied source code. They are not a comprehensive runtime error catalogue; helper `R(...)` and callers may translate errors differently.

## Error Messages and Conditions

| Source method | Condition | Observed message / behavior | Recommended investigation |
|---|---|---|---|
| `GET_INTEREST_CALC_INFO` | Payment day missing | `Payment day cant be null, please check!` | Verify payment-day configuration. |
| `GET_INTEREST_CALC_INFO` | Transaction date before previous calculation date | `Transaction date cant be less than last calculation date!` | Check effective dates and calculation history. |
| `GET_INTEREST_CALC_DATES` | Unsupported processing mode | `p_int_calc_at param should be EOD or SOD!!` | Supply `EOD` or `SOD`. |
| `GET_INTEREST_CALC_DATES` | Unsupported EOD/SOD flag | `P_EOD_SOD param should be E - EOD or S - SOD!!` | Supply `E` or `S`. |
| `GET_LOAN_AMOUNT` | Unsupported amount type | The message lists `TOTAL`, `DEBT`, `DUE` | Verify amount category. |
| `GET_OVERDUE_MIN_AMOUNT` | Product code not found | `Product code ... not found in pkrd_turkod_pr table!` | Verify product configuration. |
| `GET_VOUCHER_DATA_FROM_QUERY` | Empty SQL input | `-20001: p_query can be null!` | Verify calling query. |
| `GET_VOUCHER_DATA_FROM_QUERY` | Unsupported result type | `-20001: p_result_type should be SINGLE_ROW or MULTI_ROW!` | Supply a supported result type. |
| `ADD_COLUMN_UPDATE` | Tag missing in mapping | `Tag [...] not declared in [loan_history_mapping]` | Verify mapping configuration. |
| `FINALIZE_ADDTIONAL_PROCESS` | Initialization omitted | Must call `clear_addtional_data` beforehand | Follow documented state lifecycle. |

## Developer Notes

1. Check whether an error is raised directly by `RAISE_APPLICATION_ERROR`, through the package's `R(...)` helper, or by dependent packages.
2. Do not treat textual error messages as stable machine-readable error codes.
3. Before production support use, confirm actual codes, localization, log identifiers, rollback behavior and any additional business validations with the maintainers.

See [Review Findings](reference/review-findings.md).
