# LOAN_API — Verified Workflows

[← Overview](index.md) · [API Reference](api.md) · [Data Model](data-model.md)

These workflows describe source-observed processing, not a universal loan lifecycle. Execution order across independent EOD/SOD jobs is not established by the supplied package.

## Workflow index

- [Limit evaluation and adjustment](#workflow-limit-evaluation)
- [Interest amount posting to plan](#workflow-interest-posting)
- [History reversal and mapped updates](#workflow-history-reversal)

<a id="workflow-limit-evaluation"></a>
### Limit evaluation and adjustment

**Entry point:** [evaluate_limit_amount](api.md#evaluate-limit-amount)

**Purpose:** Align the recorded credit-line limit with the calculated available limit.

```mermaid
flowchart TD
 A[Select eligible open credit lines] --> B[Calculate available limit]
 B --> C{Recorded limit differs?}
 C -->|No| D[Skip adjustment]
 C -->|Yes| E[Determine debit and credit direction]
 E --> F[Post journal entries]
 F --> G[Record limit evaluation history]
```

**Key rules:** Loan lines must meet the package's line-type, status, branch and optional document filters. Active category 667 or an elapsed loan end date sets the calculated limit to zero. Explicit commit occurs inside the loop only when both caller transaction ID and document filter are null.

**Effects:** Accounting entries and loan operation history are created for processed differences. [Data Model](data-model.md) · [Errors](error-handling.md)

<a id="workflow-interest-posting"></a>
### Interest amount posting to plan

**Entry point:** [post_int_amount_to_plan](api.md#post-int-amount-to-plan)

**Purpose:** Update scheduled interest amounts for either standard or tranche plans.

```mermaid
flowchart TD
 A[Receive loan account type and date] --> B[Check eligible account configuration]
 B --> C{Posting permitted?}
 C -->|No| D[Report application error]
 C -->|Yes| E{Tranche selector}
 E -->|N| F[Log and update standard plan]
 E -->|Y| G[Log and update tranche plan]
 E -->|Other| D
 F --> H[Check matching row]
 G --> H
```

**Key rules:** Posting is explicitly restricted to the `INT` account-type group after the configuration lookup. Grace-payment rows retain their scheduled amount. A schedule-update type 3 with zero remaining main payment results in an early return.

**Effects:** Updates `LOAN_PAYMENT_PLAN` or `LOAN_TRANCHE_PAYMENT_PLAN`; calls table logging before DML. [Errors](error-handling.md)

<a id="workflow-history-reversal"></a>
### History reversal and mapped updates

**Entry point:** [reverse_update](api.md#reverse-update) and [finalize_addtional_process](api.md#finalize-addtional-process)

```mermaid
flowchart TD
 A[Load transaction history metadata] --> B[Resolve mapped changes]
 B --> C[Reconstruct prior values]
 C --> D[Apply mapped updates]
```

**Result:** The package uses additional history metadata and mapped updates to restore recorded values. The exact rollback/commit contract of dependencies is not determined from the supplied source; test transaction boundaries separately.

[↑ Overview](index.md)
