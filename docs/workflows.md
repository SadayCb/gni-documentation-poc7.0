# Cross-cutting workflows

These diagrams represent **conceptual groupings** corroborated by the public API surface, not a complete call graph. Method-specific side effects require verification in the package body.

## Loan account creation and accounting

```mermaid
flowchart TD
  A[Loan registration or another caller] --> B[LOAN_API.CREATE_ACCOUNT]
  B --> C[Account configuration and account records]
  A --> D[LOAN_API.CREATE_JOURNAL_ENTRIES]
  D --> E[Journal rules and accounting entries]
  A --> F[LOAN_API.CREATE_LOAN_HISTORY]
  F --> G[Loan operation history]
```

## EOD/SOD processing

```mermaid
flowchart TD
  S[EOD / SOD orchestrator] --> I[DO_INT_CALCULATION]
  S --> P[DO_AUTO_PAYMENT]
  S --> O[DO_OVERDUE_TRANSIT_OPERATION]
  S --> R[DO_LOAN_CONTROL]
  I --> C[(Loan and accounting tables)]
  P --> C
  O --> C
  R --> C
```

**Note:** Parallel order and scheduling dependencies are **not established** here. These routines must not be treated as freely interchangeable steps.

## Loan history / reversible mapped updates

```mermaid
flowchart TD
  A[CLEAR_ADDTIONAL_DATA] --> B[ADD_ADDITIONAL_INFO / ADD_COLUMN_UPDATE]
  B --> C[FINALIZE_ADDTIONAL_PROCESS]
  C --> D[Mapped table updates and JSON OLD/NEW]
  E[REVERSE_UPDATE by transaction] --> F[Read LOAN_OPERATION_HISTORY]
  F --> B
```

**Security note:** Source builds dynamic UPDATE statements from mapped metadata and values. Inspect quoting, privileges, concurrency and logging before exposing this capability to customers.
