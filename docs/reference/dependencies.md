# Dependencies & integration context

## Key database objects (observed in supplied implementation)

| Object | Usage observed |
|---|---|
| `KRD_TEKLIF_DETAY` | Loan master/detail data and filtering |
| `LOAN_PAYMENT_PLAN` | Interest grace and overdue calculation inputs |
| `LOAN_ACC_TYPES_PR` | Account type configuration |
| `CS_ACCOUNT` | Balances and loan-linked accounts |
| `KRD_PYM_ORDER` | Payment allocation configuration |
| `LOAN_OPERATION_HISTORY` | Operation history and reversible changes |
| `LOAN_HISTORY_MAPPING` | Tag-to-table/column mapping for updates |
| `LOAN_INT_CALC_TYPES_PR` | Interest calculation day-count conventions |
| `LOAN_OPERATION_DESC` | Transaction caller lookup |
| `PKRD_TURKOD_PR` | Product overdue-minimum configuration |

This list is **selective**, not a complete dependency manifest. A complete list should be extracted and verified with `ALL_DEPENDENCIES` on the deployed schema.

## Safe metadata query

```sql
SELECT referenced_owner, referenced_name, referenced_type
  FROM all_dependencies
 WHERE owner = :schema_name
   AND name = 'LOAN_API'
   AND type = 'PACKAGE BODY'
 ORDER BY referenced_owner, referenced_type, referenced_name;
```

Dynamic SQL dependencies can be missed by static dependency metadata.
