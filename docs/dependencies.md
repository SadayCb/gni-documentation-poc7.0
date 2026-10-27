# LOAN_API — Dependencies

[← Overview](index.md) · [API Reference](api.md) · [Data Model](data-model.md)

Directly invoked dependencies confirmed in the supplied package body:

| Dependency | Kind | Verified usage | Used by |
|---|---|---|---|
| `LOAN_REPORT_API` | PL/SQL package | Retrieve transaction description for limit evaluation | [evaluate_limit_amount](api.md#evaluate-limit-amount) |
| `GLBL_HESAP` | PL/SQL package | Retrieve counter-account configuration | [evaluate_limit_amount](api.md#evaluate-limit-amount) |
| `TRN_BROKER` | PL/SQL package | Obtain transaction identifier for journal processing | [evaluate_limit_amount](api.md#evaluate-limit-amount) |
| `LOAN_TRANCHE_API` | PL/SQL package | Log tranche-plan changes before posting | [post_int_amount_to_plan](api.md#post-int-amount-to-plan) |
| `GLBL` | PL/SQL package | Obtain business/system processing date | [evaluate_limit_amount](api.md#evaluate-limit-amount) |
| `LOAN_API` (internal public calls) | PL/SQL package | Journal posting and history recording | [evaluate_limit_amount](api.md#evaluate-limit-amount) |

This list is selective: **absence does not imply independence**. Database tables and access modes are maintained in [Data Model](data-model.md), not duplicated here. A deployed-schema `ALL_DEPENDENCIES` query may add static dependencies but can omit those referenced only via dynamic SQL.

```sql
SELECT referenced_owner, referenced_name, referenced_type
FROM all_dependencies
WHERE owner = :schema_name
  AND name = 'LOAN_API'
  AND type = 'PACKAGE BODY'
ORDER BY referenced_owner, referenced_type, referenced_name;
```
