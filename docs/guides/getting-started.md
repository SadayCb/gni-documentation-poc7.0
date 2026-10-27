# Getting started — developer onboarding

## Intended readers

Developers joining a team maintaining Oracle loan processing and technical teams integrating with the loan engine.

## Learning path

1. Read the [overview](../overview.md) for functional boundaries.
2. Identify whether your change affects calculations, schedule, accounts, payments, journaling, history or batch processing.
3. Find the exact public signature in the [API reference](../api/loan-api.md).
4. Trace the corresponding package-body implementation and called routines.
5. Review dependencies, error handling and state transitions.
6. Confirm the transaction owner, rollback behavior, EOD/SOD context and audit trail with the technical owner.
7. Test with an isolated database and synthetic data.

## Important conventions

- `p_doc_no` commonly identifies a loan document; exact format and uniqueness rules are environment-specific.
- `p_tx_fid` identifies an operation transaction in several methods.
- `p_eod_sod` distinguishes EOD / SOD contexts where implemented.
- `OUT` and `IN OUT` arguments may return calculated data or transaction identifiers.
- Public types such as `g_loan_accounts_tab` are defined in the package specification.

## Safe read-only exploration

```sql
SELECT procedure_name, subprogram_id, overload
  FROM all_procedures
 WHERE owner = :schema_name
   AND object_name = 'LOAN_API'
 ORDER BY subprogram_id;
```

Do **not** call mutating methods (`DO_*`, `CREATE_*`, `FINALIZE_*`, etc.) to discover their behavior in a shared or production environment.
