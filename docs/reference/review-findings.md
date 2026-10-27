# Review findings and publication checklist

> **Draft findings** from supplied source, not confirmed incidents. Validate with maintainers before changing implementation.

## Implementation observations

1. **Dynamic SQL in mapped updates.** `FINALIZE_ADDTIONAL_PROCESS` constructs `UPDATE` statements by concatenating typed values and mapping metadata. Review SQL literal escaping, identifier validation and authorization; a quote-containing value can cause malformed SQL or worse if trusted boundaries fail.
2. **Dynamic SQL query execution.** `GET_VOUCHER_DATA_FROM_QUERY` parses and executes SQL passed in `p_query` via `DBMS_SQL`. Restrict who may supply queries and verify cursor cleanup in all paths.
3. **History reversal depends on JSON and mappings.** `REVERSE_UPDATE` reads `LOAN_OPERATION_HISTORY.ADDITIONAL_INFO`, reconstructs mappings, and invokes finalization. Confirm behavior for missing keys, nulls, multiple history rows and partial failure.
4. **Overloads and side effects.** `GET_PEN_INFO_FOR_CALC`, `ADD_ADDITIONAL_INFO`, `ADD_COLUMN_UPDATE` and `DO_LOAN_CONTROL` have multiple public signatures; documentation and tests must distinguish overloads.
5. **Session/package state.** Global flags and collections exist in the spec and body. Confirm lifecycle, reset behavior and pooled database session implications.
6. **Batch process safety.** Automatic payments, interest calculation, overdue transitions and task orchestration require operational runbooks, permissions, idempotency and rollback procedures.

## Before external/customer release

- [ ] Verify exact business meaning of each procedure and public parameter.
- [ ] Confirm exception behavior, commits, rollbacks and logging.
- [ ] Validate security boundaries, privileges and client-specific configuration.
- [ ] Review examples using anonymized test identifiers only.
- [ ] Exclude internal implementation details not intended for the customer.
- [ ] Obtain Technical Lead and Security approval.

## Provenance

Source: supplied `LOAN_API` package specification and package body. Descriptions labeled name-based in API catalogue are inferred summaries, not authoritative business requirements.
