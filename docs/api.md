# LOAN_API — API Reference

[← Back to Overview](index.md) · [API Reference](api.md) · [Workflows](workflows.md) · [Data Model](data-model.md) · [Dependencies](dependencies.md) · [Error Handling](error-handling.md)

<a id="api-index"></a>
## API Index

### [Loan operations and controls](#domain-loan-operations-and-controls)

Coordinates loan operations, validation, and operational control checks.

**Procedures**
- [do_delete_operation](#do-delete-operation)
- [do_plan_control](#do-plan-control)
- [do_loan_control](#do-loan-control-1) — varchar2, date
- [do_loan_control](#do-loan-control-2) — varchar2, date
- [do_loan_status_control](#do-loan-status-control)
- [init_global_variables](#init-global-variables)

**Functions**
- [get_amount_by_range](#get-amount-by-range)
- [get_loan_amount](#get-loan-amount)
- [get_offer_id](#get-offer-id)

### [Accounts, guarantees and closure](#domain-accounts-guarantees-and-closure)

Manages loan-linked accounts, guarantees, collateral release, and closure activities.

**Procedures**
- [create_account](#create-account)
- [do_loan_collateral_out](#do-loan-collateral-out)
- [do_guarantee_out](#do-guarantee-out)
- [do_Loan_Close_With_Collateral_Out](#do-loan-close-with-collateral-out)
- [do_non_cash_loan_close](#do-non-cash-loan-close)
- [change_account_status](#change-account-status)

**Functions**
- [get_gl_acc_active_passive](#get-gl-acc-active-passive)
- [get_gl_acc_from_matrix](#get-gl-acc-from-matrix)
- [get_account_feature](#get-account-feature)
- [get_new_acc](#get-new-acc)
- [get_acc_type_by_status](#get-acc-type-by-status)

### [Payments and balances](#domain-payments-and-balances)

Allocates and evaluates loan payments, plan amounts, and outstanding amounts.

**Procedures**
- [post_int_amount_to_plan](#post-int-amount-to-plan)
- [generate_allocated_payment_list](#generate-allocated-payment-list)
- [add_payment_details](#add-payment-details)
- [do_Auto_Payment](#do-auto-payment)

**Functions**
- [get_overdue_min_amount](#get-overdue-min-amount)
- [get_overdue_grace_days](#get-overdue-grace-days)
- [get_next_Plan_Pym](#get-next-plan-pym)
- [get_plan_payment_amount](#get-plan-payment-amount)

### [Payment schedules and dates](#domain-payment-schedules-and-dates)

Produces and adjusts repayment schedules, installment dates, and grace-period information.

**Procedures**
- [recalculate_int_payment_plan](#recalculate-int-payment-plan)
- [do_schedule_allignment](#do-schedule-allignment)
- [do_com_schedule_allignment](#do-com-schedule-allignment)
- [get_special_schedule](#get-special-schedule)
- [get_created_schedule](#get-created-schedule)
- [create_schedule](#create-schedule)
- [UPDATE_PAYMENT_PLAN](#update-payment-plan)

**Functions**
- [get_formatted_grace_from_list](#get-formatted-grace-from-list)
- [get_grace_info](#get-grace-info)
- [get_commission_schedule](#get-commission-schedule)
- [add_months_for_loan](#add-months-for-loan)
- [get_Plan_Month_Count](#get-plan-month-count)
- [get_plan_paid_month_count](#get-plan-paid-month-count)
- [get_plan_error](#get-plan-error)
- [get_Annuity_Amount](#get-annuity-amount)
- [get_Pym_Startdate](#get-pym-startdate)
- [is_Payment_Date](#is-payment-date)
- [get_schedule_from_memo](#get-schedule-from-memo)
- [get_standart_schedule](#get-standart-schedule)
- [get_annuity_schedule](#get-annuity-schedule)

### [Interest, penalties and rates](#domain-interest-penalties-and-rates)

Calculates or retrieves interest, penalty bases, rates, and recognition information.

**Procedures**
- [get_interest_calc_info](#get-interest-calc-info)
- [loan_int_diff_operation](#loan-int-diff-operation)
- [do_int_calculation](#do-int-calculation)
- [do_commission_recognition](#do-commission-recognition)

**Functions**
- [get_amount_for_pen_calc](#get-amount-for-pen-calc-1) — date, varchar2
- [get_interest_calc_dates](#get-interest-calc-dates)
- [get_interest_calc_dates_ex](#get-interest-calc-dates-ex)
- [get_basis_year_days_cnt](#get-basis-year-days-cnt)
- [Get_Delay_Int_Rate](#get-delay-int-rate)
- [get_amount_for_pen_calc](#get-amount-for-pen-calc-2) — Varchar2, Date
- [get_flow_ratio_info](#get-flow-ratio-info)
- [get_stop_ratio_info](#get-stop-ratio-info)
- [get_incorrect_days](#get-incorrect-days)
- [get_incorrect_days_count](#get-incorrect-days-count)

### [Delinquency and status](#domain-delinquency-and-status)

Determines overdue transitions, overdue dates, and related overdue processing.

**Procedures**
- [do_overdue_transit_operation](#do-overdue-transit-operation)

**Functions**
- [get_ovd_trs_oper_type](#get-ovd-trs-oper-type)
- [get_ovd_date](#get-ovd-date)
- [get_ovd_date_old](#get-ovd-date-old)

### [Limits, tranches and overdrafts](#domain-limits-tranches-and-overdrafts)

Evaluates credit limits, creates tranches, and processes overdraft contracts.

**Procedures**
- [evaluate_limit_amount](#evaluate-limit-amount)
- [do_create_tranche](#do-create-tranche)
- [create_overdrafts](#create-overdrafts)

**Functions**
- [get_new_ov_cont_no](#get-new-ov-cont-no)

### [Accounting and audit](#domain-accounting-and-audit)

Creates accounting postings and retrieves accounting mappings and journal information.

**Procedures**
- [table_log_operation](#table-log-operation)
- [do_journal_entry](#do-journal-entry)
- [create_journal_entries](#create-journal-entries)
- [do_journal_control](#do-journal-control)

**Functions**
- [get_trn_caller_id](#get-trn-caller-id)
- [get_voucher_data_from_query](#get-voucher-data-from-query)
- [get_gl_value](#get-gl-value)

### [History, metadata and reversal](#domain-history-metadata-and-reversal)

Captures transaction metadata and loan operation history, and supports reversal of recorded changes.

**Procedures**
- [clear_addtional_data](#clear-addtional-data)
- [add_additional_group](#add-additional-group)
- [add_additional_info](#add-additional-info-1) — varchar2, varchar2
- [add_additional_info](#add-additional-info-2) — varchar2, date
- [add_column_update](#add-column-update-1) — varchar2, varchar2
- [add_column_update](#add-column-update-2) — varchar2, date
- [finalize_addtional_process](#finalize-addtional-process)
- [reverse_update](#reverse-update)
- [create_loan_history](#create-loan-history)
- [update_loan_history](#update-loan-history)

**Functions**
- [get_additional_info](#get-additional-info)
- [is_online_offer](#is-online-offer)

<a id="domain-loan-operations-and-controls"></a>
## Loan operations and controls

**Responsibility:** Coordinates loan operations, validation, and operational control checks.

[↑ API Index](#api-index)

### Procedures

<a id="do-delete-operation"></a>
#### do_delete_operation

**Type:** Procedure

**Purpose:** Reverses a recorded loan transaction subject to the requested date and plan controls.

**Signature**

```sql
procedure do_delete_operation(p_tx_fid       number,
                                p_date_control varchar2 default 'Y',
                                p_plan_control varchar2 default 'Y');
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_tx_fid` | IN | Transaction identifier |
| `p_date_control` | IN | Supplied `p_date_control` input (varchar2) |
| `p_plan_control` | IN | Supplied `p_plan_control` input (varchar2) |

**Business Logic**

- Reads `LOAN_OPERATION_HISTORY`, `GL_JOURNAL_LINES` to obtain operation inputs or existing loan data.
- Changes `GLBL_TRANSACTION` as part of the operation.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** `LOAN_TRANCHE_API`, `MM_ACCOUNTING#`, `KRD_EOD` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-loan-operations-and-controls)

---

<a id="do-plan-control"></a>
#### do_plan_control

**Type:** Procedure

**Purpose:** Performs the plan control operation for the supplied inputs.

**Signature**

```sql
procedure do_plan_control(p_document_no in varchar2,
                            p_date        date default glbl.getsysdate);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_document_no` | IN | Supplied `p_document_no` input (varchar2) |
| `p_date` | IN | Effective/processing date |

**Business Logic**

- Reads `LOAN_EOD_CONTROL_EXP` to obtain operation inputs or existing loan data.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-loan-operations-and-controls)

---

<a id="do-loan-control-1"></a>
#### do_loan_control

**Type:** Procedure

**Purpose:** Performs the loan control operation for the supplied inputs.

**Signature**

```sql
procedure do_loan_control(p_oper_type varchar2 default null,
                            p_date      date default glbl.getsysdate);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_oper_type` | IN | Operation type selector |
| `p_date` | IN | Effective/processing date |

**Business Logic**

- Reads `LOAN_EOD_CONTROL`, `KRD_TEKLIF_DETAY` to obtain operation inputs or existing loan data.
- Delegates related processing to `GNI_UTILITY`.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** `GNI_UTILITY` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-loan-operations-and-controls)

---

<a id="do-loan-control-2"></a>
#### do_loan_control

**Type:** Procedure

**Purpose:** Performs the loan control operation for the supplied inputs.

**Signature**

```sql
procedure do_loan_control(p_oper_type varchar2 default null,
                            p_date      date default glbl.getsysdate,
                            p_min_rowid rowid,
                            p_max_rowid rowid);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_oper_type` | IN | Operation type selector |
| `p_date` | IN | Effective/processing date |
| `p_min_rowid` | IN | Supplied `p_min_rowid` input (rowid) |
| `p_max_rowid` | IN | Supplied `p_max_rowid` input (rowid) |

**Business Logic**

- Reads `KRD_TEKLIF_DETAY`, `LOAN_EOD_CONTROL_EXP`, `LOAN_OPERATION_HISTORY` to obtain operation inputs or existing loan data.
- Changes `LOAN_EOD_CONTROL` as part of the operation.
- Contains an explicit `COMMIT`; transaction scope depends on the shown conditions.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** `GLBL` · [Dependency register](dependencies.md).

**Errors:** No explicit business error identified; see [Error Handling](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-loan-operations-and-controls)

---

<a id="do-loan-status-control"></a>
#### do_loan_status_control

**Type:** Procedure

**Purpose:** Performs the loan status control operation for the supplied inputs.

**Signature**

```sql
procedure do_loan_status_control(p_branch_no   in number,
                                   p_customer_no in number,
                                   p_loan_acc    in number);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_branch_no` | IN | Branch identifier |
| `p_customer_no` | IN | Customer identifier |
| `p_loan_acc` | IN | Supplied `p_loan_acc` input (number) |

**Business Logic**

- Reads `LOAN_PORTFOLIO_LITE` to obtain operation inputs or existing loan data.
- Delegates related processing to `GNI_MESSAGE`.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** `GNI_MESSAGE` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-loan-operations-and-controls)

---

<a id="init-global-variables"></a>
#### init_global_variables

**Type:** Procedure

**Purpose:** Provides init global variables behavior for loan processing.

**Signature**

```sql
Procedure init_global_variables(p_doc_no varchar2,
                                  p_reset  boolean default false);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_doc_no` | IN | Loan document identifier |
| `p_reset` | IN | Supplied `p_reset` input (boolean) |

**Business Logic**

- Reads `KRD_TEKLIF_DETAY`, `KRD_TEKLIF`, `KRD_TESIS`, `KRD_ODEME_PLAN` to obtain operation inputs or existing loan data.

**Business Rules**

- [krd_teklif_detay] is invalid
- [krd_teklif] is invalid
- [krd_tesis] is invalid

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-loan-operations-and-controls)

---

### Functions

<a id="get-amount-by-range"></a>
#### get_amount_by_range

**Type:** Function

**Purpose:** Selects a configured amount range for the supplied operation, account and tranche information.

**Signature**

```sql
function get_amount_by_range(p_oper_type    in varchar2,
                               p_acc_type     in varchar2,
                               p_tranche_type in varchar2 default null,
                               p_amount       in number) return number;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_oper_type` | IN | Operation type selector |
| `p_acc_type` | IN | Loan account type |
| `p_tranche_type` | IN | Supplied `p_tranche_type` input (varchar2) |
| `p_amount` | IN | Amount supplied for processing |

**Returns:** `number` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Reads `LOAN_AMOUNT_RANGE_INFO` to obtain operation inputs or existing loan data.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-loan-operations-and-controls)

---

<a id="get-loan-amount"></a>
#### get_loan_amount

**Type:** Function

**Purpose:** Retrieves an amount for the specified loan and amount category.

**Signature**

```sql
function get_loan_amount(p_doc_no      in varchar2,
                           p_amount_type in varchar2,
                           p_date        in date default glbl.getsysdate,
                           p_oper_type   in varchar2 default null)
    return number;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_doc_no` | IN | Loan document identifier |
| `p_amount_type` | IN | Supplied `p_amount_type` input (varchar2) |
| `p_date` | IN | Effective/processing date |
| `p_oper_type` | IN | Operation type selector |

**Returns:** `number` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Reads `CS_ACCOUNT` to obtain operation inputs or existing loan data.
- Delegates related processing to `P`, `O`.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** `P`, `O` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-loan-operations-and-controls)

---

<a id="get-offer-id"></a>
#### get_offer_id

**Type:** Function

**Purpose:** Retrieves or evaluates offer id information.

**Signature**

```sql
Function get_offer_id(p_branch_id In Number Default Glbl.Getsube,
                        P_date      In Date Default Glbl.Getsysdate)
    Return Varchar2;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_branch_id` | IN | Supplied `p_branch_id` input (Number) |
| `P_date` | IN | Effective/processing date |

**Returns:** `Varchar2` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Changes `KRD_TEKLIF_NO` as part of the operation.
- Contains an explicit `COMMIT`; transaction scope depends on the shown conditions.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** No explicit business error identified; see [Error Handling](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-loan-operations-and-controls)

---

<a id="domain-accounts-guarantees-and-closure"></a>
## Accounts, guarantees and closure

**Responsibility:** Manages loan-linked accounts, guarantees, collateral release, and closure activities.

[↑ API Index](#api-index)

### Procedures

<a id="create-account"></a>
#### create_account

**Type:** Procedure

**Purpose:** Creates loan-linked accounts using account-type configuration.

**Signature**

```sql
procedure create_account(p_doc_no      in varchar2,
                           p_oper_type   in varchar2,
                           p_acc_type    in varchar2 default null,
                           p_tx_fid      in number,
                           p_created_acc out g_loan_accounts_tab);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_doc_no` | IN | Loan document identifier |
| `p_oper_type` | IN | Operation type selector |
| `p_acc_type` | IN | Loan account type |
| `p_tx_fid` | IN | Transaction identifier |
| `p_created_acc` | OUT | g_loan_accounts_tab value populated by the operation |

**Business Logic**

- Reads `KRD_TEKLIF_DETAY`, `KRD_TESIS`, `SP_FAIZ_GUN_TANIM_PR`, `LOAN_ACC_TYPES_PR` to obtain operation inputs or existing loan data.
- Changes `KRD_TESIS`, `KRD_TEKLIF_DETAY` as part of the operation.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** `GLBL_TARIH`, `GLBL_NAME`, `GNI_MESSAGE` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-accounts-guarantees-and-closure)

---

<a id="do-loan-collateral-out"></a>
#### do_loan_collateral_out

**Type:** Procedure

**Purpose:** Performs the loan collateral out operation for the supplied inputs.

**Signature**

```sql
procedure do_loan_collateral_out(p_doc_no in varchar2);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_doc_no` | IN | Loan document identifier |

**Business Logic**

- Reads `CS_ACCOUNT`, `KRD_TEMINAT_TIP_PR`, `KRD_SCOR_REAL_ESTATE_C`, `KRD_SCOR_AUTO_C` to obtain operation inputs or existing loan data.
- Changes `KRD_SCOR_REAL_ESTATE_C`, `KRD_SCOR_AUTO_C`, `KRD_SCOR_ESYA_C`, `KRD_SCOR_EMANET_C` as part of the operation.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** `GLBL_EOD`, `TRN_BROKER`, `GLBL_CCY`, `PA_API#`, `MM_ACCOUNTING#` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-accounts-guarantees-and-closure)

---

<a id="do-guarantee-out"></a>
#### do_guarantee_out

**Type:** Procedure

**Purpose:** Performs the guarantee out operation for the supplied inputs.

**Signature**

```sql
Procedure do_guarantee_out(p_branch_id   In Number Default Null,
                             p_customer_no In Number Default Null,
                             p_loan_acc    In Number Default Null);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_branch_id` | IN | Supplied `p_branch_id` input (Number) |
| `p_customer_no` | IN | Customer identifier |
| `p_loan_acc` | IN | Supplied `p_loan_acc` input (Number) |

**Business Logic**

- Reads `KRD_TESIS` to obtain operation inputs or existing loan data.
- Delegates related processing to `GLBL_BAKIYE`, `APEX_KRD2220_0_API_P`, `TRN_BROKER`.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** `GLBL_BAKIYE`, `APEX_KRD2220_0_API_P`, `TRN_BROKER`, `KRD2220_0_API` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-accounts-guarantees-and-closure)

---

<a id="do-loan-close-with-collateral-out"></a>
#### do_Loan_Close_With_Collateral_Out

**Type:** Procedure

**Purpose:** Performs the loan close with collateral out operation for the supplied inputs.

**Signature**

```sql
procedure do_Loan_Close_With_Collateral_Out(p_doc_no in varchar2);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_doc_no` | IN | Loan document identifier |

**Business Logic**

- Reads `LOAN_PORTFOLIO_LITE`, `LOAN_EOD_AUTO_CLOSE`, `LOAN_TRANCHE_LIMIT_CHANGES_HISTORY` to obtain operation inputs or existing loan data.
- Changes `KRD_TEKLIF_DETAY`, `KRD_FON_VERILME`, `LOAN_EOD_AUTO_CLOSE` as part of the operation.
- Contains an explicit `COMMIT`; transaction scope depends on the shown conditions.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** `GLBL_EOD`, `GLBL_HESAP`, `TRN_BROKER` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-accounts-guarantees-and-closure)

---

<a id="do-non-cash-loan-close"></a>
#### do_non_cash_loan_close

**Type:** Procedure

**Purpose:** Performs the non cash loan close operation for the supplied inputs.

**Signature**

```sql
Procedure do_non_cash_loan_close(p_doc_no in varchar2,
                                   p_Date   In Date Default Glbl.Getsysdate);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_doc_no` | IN | Loan document identifier |
| `p_Date` | IN | Effective/processing date |

**Business Logic**

- Reads `KRD_TESIS`, `CS_ACCOUNT` to obtain operation inputs or existing loan data.
- Delegates related processing to `GLBL_BAKIYE`, `APEX_KRD2220_0_API_P`, `TRN_BROKER`.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** `GLBL_BAKIYE`, `APEX_KRD2220_0_API_P`, `TRN_BROKER`, `KRD2220_0_API` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-accounts-guarantees-and-closure)

---

<a id="change-account-status"></a>
#### change_account_status

**Type:** Procedure

**Purpose:** Performs the change account status operation for the supplied inputs.

**Signature**

```sql
procedure change_account_status(p_doc_no in varchar2,
                                  p_status in varchar2);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_doc_no` | IN | Loan document identifier |
| `p_status` | IN | Supplied `p_status` input (varchar2) |

**Business Logic**

- Reads `KRD_TEKLIF_DETAY`, `CS_ACCOUNT` to obtain operation inputs or existing loan data.
- Delegates related processing to `GLBL_HESAP`, `LOAN_CATEGORY_API`.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** `GLBL_HESAP`, `LOAN_CATEGORY_API` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-accounts-guarantees-and-closure)

---

### Functions

<a id="get-gl-acc-active-passive"></a>
#### get_gl_acc_active_passive

**Type:** Function

**Purpose:** Retrieves or evaluates gl acc active passive information.

**Signature**

```sql
function get_gl_acc_active_passive(p_acc_no in varchar2) return varchar2 result_cache;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_acc_no` | IN | Supplied `p_acc_no` input (varchar2) |

**Returns:** `varchar2` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Reads `GL_ACCOUNT_DEFINE` to obtain operation inputs or existing loan data.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-accounts-guarantees-and-closure)

---

<a id="get-gl-acc-from-matrix"></a>
#### get_gl_acc_from_matrix

**Type:** Function

**Purpose:** Resolves the GL account using configured loan/product/account parameters.

**Signature**

```sql
function get_gl_acc_from_matrix(p_product_code in number default null,
                                  p_cust_type    in number default null,
                                  p_period_id    in number default null,
                                  p_currency_id  in number default null,
                                  p_base_type    in varchar2,
                                  p_loan_doc_no  in varchar2 default null,
                                  p_acc_type     in varchar2) return varchar2 result_cache;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_product_code` | IN | Supplied `p_product_code` input (number) |
| `p_cust_type` | IN | Supplied `p_cust_type` input (number) |
| `p_period_id` | IN | Supplied `p_period_id` input (number) |
| `p_currency_id` | IN | Supplied `p_currency_id` input (number) |
| `p_base_type` | IN | Supplied `p_base_type` input (varchar2) |
| `p_loan_doc_no` | IN | Supplied `p_loan_doc_no` input (varchar2) |
| `p_acc_type` | IN | Loan account type |

**Returns:** `varchar2` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Resolves accounting account mappings from product, period, currency and loan characteristics.
- Retrieves the applicable mapped GL account.

**Business Rules**

- p_gl_base_type should be MAIN - for main account, OVD_MAIN - for overdue account!
- p_acc_type is invalid!

**Dependencies:** `GLBL_HESAP` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-accounts-guarantees-and-closure)

---

<a id="get-account-feature"></a>
#### get_account_feature

**Type:** Function

**Purpose:** Retrieves or evaluates account feature information.

**Signature**

```sql
function get_account_feature(p_branch_no   number,
                               p_account_no  number,
                               p_account_sub number)
    return cs_account.account_feature%type;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_branch_no` | IN | Branch identifier |
| `p_account_no` | IN | Supplied `p_account_no` input (number) |
| `p_account_sub` | IN | Supplied `p_account_sub` input (number) |

**Returns:** `cs_account.account_feature%type` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Looks up the account feature for the supplied account number/subaccount, optionally constrained by branch.
- Returns the stored account feature value.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** `GLBL_TARIH` · [Dependency register](dependencies.md).

**Errors:** No explicit business error identified; see [Error Handling](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-accounts-guarantees-and-closure)

---

<a id="get-new-acc"></a>
#### get_new_acc

**Type:** Function

**Purpose:** Opens a new account and returns its account identifier.

**Signature**

```sql
function get_new_acc(p_branch_no       in number,
                       p_customer_no     in number,
                       p_balance_acc     in varchar2,
                       p_detail_code     in varchar2,
                       p_ccy_id          in number,
                       p_main_acc        in number default null,
                       p_cr_int_rate     in number default null,
                       p_dr_int_rate     in number default null,
                       p_com_int_rate    in number default null,
                       p_product_code    in number default null,
                       p_period_id       in number default null,
                       p_acc_description in varchar2,
                       p_loan_doc_no     in varchar2,
                       p_loan_acc_type   in varchar2,
                       p_tx_fid          in number) return number;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_branch_no` | IN | Branch identifier |
| `p_customer_no` | IN | Customer identifier |
| `p_balance_acc` | IN | Supplied `p_balance_acc` input (varchar2) |
| `p_detail_code` | IN | Supplied `p_detail_code` input (varchar2) |
| `p_ccy_id` | IN | Supplied `p_ccy_id` input (number) |
| `p_main_acc` | IN | Supplied `p_main_acc` input (number) |
| `p_cr_int_rate` | IN | Supplied `p_cr_int_rate` input (number) |
| `p_dr_int_rate` | IN | Supplied `p_dr_int_rate` input (number) |
| `p_com_int_rate` | IN | Supplied `p_com_int_rate` input (number) |
| `p_product_code` | IN | Supplied `p_product_code` input (number) |
| `p_period_id` | IN | Supplied `p_period_id` input (number) |
| `p_acc_description` | IN | Supplied `p_acc_description` input (varchar2) |
| `p_loan_doc_no` | IN | Supplied `p_loan_doc_no` input (varchar2) |
| `p_loan_acc_type` | IN | Supplied `p_loan_acc_type` input (varchar2) |
| `p_tx_fid` | IN | Transaction identifier |

**Returns:** `number` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Resolves loan account setup and creates a linked account through account services.
- Returns the newly created account identifier.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** `GNI_MESSAGE`, `GLBL_HESAP` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-accounts-guarantees-and-closure)

---

<a id="get-acc-type-by-status"></a>
#### get_acc_type_by_status

**Type:** Function

**Purpose:** Retrieves or evaluates acc type by status information.

**Signature**

```sql
function get_acc_type_by_status(p_acc_type         varchar2,
                                  p_to_loan_status   varchar2,
                                  p_from_loan_status varchar2 default 'NORM')
    return varchar2 result_cache;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_acc_type` | IN | Loan account type |
| `p_to_loan_status` | IN | Supplied `p_to_loan_status` input (varchar2) |
| `p_from_loan_status` | IN | Supplied `p_from_loan_status` input (varchar2) |

**Returns:** `varchar2` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Reads `LOAN_ACC_TYPE_MAPPING` to obtain operation inputs or existing loan data.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-accounts-guarantees-and-closure)

---

<a id="domain-payments-and-balances"></a>
## Payments and balances

**Responsibility:** Allocates and evaluates loan payments, plan amounts, and outstanding amounts.

[↑ API Index](#api-index)

### Procedures

<a id="post-int-amount-to-plan"></a>
#### post_int_amount_to_plan

**Type:** Procedure

**Purpose:** Updates scheduled interest amounts for a standard loan or a tranche loan.

**Signature**

```sql
procedure post_int_amount_to_plan(p_doc_no               in varchar2,
                                    p_tranche_no           in number,
                                    p_tx_fid               in number,
                                    p_acc_type             in varchar2,
                                    p_amount               in number,
                                    p_plan_date            in date,
                                    p_with_tranche_info_yn in varchar2);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_doc_no` | IN | Loan document identifier |
| `p_tranche_no` | IN | Tranche identifier |
| `p_tx_fid` | IN | Transaction identifier |
| `p_acc_type` | IN | Loan account type |
| `p_amount` | IN | Amount supplied for processing |
| `p_plan_date` | IN | Supplied `p_plan_date` input (date) |
| `p_with_tranche_info_yn` | IN | Supplied `p_with_tranche_info_yn` input (varchar2) |

**Business Logic**

- Validates account type configuration before posting plan interest amounts.
- Calculates the target payment amount using the supplied amount, paid amount, and preceding open-plan balances.
- Updates either standard or tranche payment plans and marks the selected plan row open.

**Business Rules**

- Only configured payment-plan account types in the specified groups are considered, with posting limited to the `INT` group.
- Plan selection requires tranche mode `Y` or standard mode `N`; the target row must exist.
- Grace-payment rows may preserve their original payment amount.

**Dependencies:** `LOAN_TRANCHE_API` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-payments-and-balances)

---

<a id="generate-allocated-payment-list"></a>
#### generate_allocated_payment_list

**Type:** Procedure

**Purpose:** Builds account-level allocations for a loan payment amount.

**Signature**

```sql
procedure generate_allocated_payment_list(p_doc_no                in varchar2,
                                            p_oper_type             in varchar2,
                                            p_pym_amount            in number,
                                            p_has_schedule_upd_type out varchar2,
                                            p_payment_list          out loan_api.g_loan_accounts_tab);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_doc_no` | IN | Loan document identifier |
| `p_oper_type` | IN | Operation type selector |
| `p_pym_amount` | IN | Supplied `p_pym_amount` input (number) |
| `p_has_schedule_upd_type` | OUT | varchar2 value populated by the operation |
| `p_payment_list` | OUT | loan_api.g_loan_accounts_tab value populated by the operation |

**Business Logic**

- Collects eligible loan accounts and balances for the specified operation.
- Produces the allocated payment list and reports whether schedule-update behavior applies.

**Business Rules**

- Payment amount cant be negative!

**Dependencies:** `P`, `O` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-payments-and-balances)

---

<a id="add-payment-details"></a>
#### add_payment_details

**Type:** Procedure

**Purpose:** Enriches the loan payment allocation list with destination and schedule information.

**Signature**

```sql
procedure add_payment_details(p_doc_no                in varchar2,
                                p_has_schedule_upd_type out varchar2,
                                p_payment_list          in out loan_api.g_loan_accounts_tab);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_doc_no` | IN | Loan document identifier |
| `p_has_schedule_upd_type` | OUT | varchar2 value populated by the operation |
| `p_payment_list` | IN OUT | loan_api.g_loan_accounts_tab value populated by the operation |

**Business Logic**

- Augments the payment list with account-specific payment metadata and current balance information.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** `O` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-payments-and-balances)

---

<a id="do-auto-payment"></a>
#### do_Auto_Payment

**Type:** Procedure

**Purpose:** Processes automatic loan payments for eligible loans in the specified EOD/SOD context.

**Signature**

```sql
Procedure do_Auto_Payment(p_min_id     number default null,
                            p_max_id     number default null,
                            p_doc_no     in varchar2 default null,
                            p_eod_sod    in varchar2 default 'E',
                            p_test_param in number default null);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_min_id` | IN | Supplied `p_min_id` input (number) |
| `p_max_id` | IN | Supplied `p_max_id` input (number) |
| `p_doc_no` | IN | Loan document identifier |
| `p_eod_sod` | IN | EOD/SOD processing selector |
| `p_test_param` | IN | Supplied `p_test_param` input (number) |

**Business Logic**

- Reads `LOAN_PAYMENT_PLAN`, `KRD_TEKLIF_DETAY`, `EOD_PROGRAMS_EXCEPTION` to obtain operation inputs or existing loan data.
- Delegates related processing to `GNI_UTILITY`, `GLBL_BAKIYE`, `GLBL_CCY`.
- Contains an explicit `COMMIT`; transaction scope depends on the shown conditions.
- Contains explicit rollback handling.

**Business Rules**

- Auto payment type should be 1-Plan payment or 2-Off plan payment!

**Dependencies:** `GNI_UTILITY`, `GLBL_BAKIYE`, `GLBL_CCY`, `LOAN_TRANCHE_API`, `APEX_KRD2204_0_API_P` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-payments-and-balances)

---

### Functions

<a id="get-overdue-min-amount"></a>
#### get_overdue_min_amount

**Type:** Function

**Purpose:** Retrieves or evaluates overdue min amount information.

**Signature**

```sql
function get_overdue_min_amount(p_product_code in number,
                                  p_acc_type     in varchar2) return number;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_product_code` | IN | Supplied `p_product_code` input (number) |
| `p_acc_type` | IN | Loan account type |

**Returns:** `number` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Reads `PKRD_TURKOD_PR` to obtain operation inputs or existing loan data.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-payments-and-balances)

---

<a id="get-overdue-grace-days"></a>
#### get_overdue_grace_days

**Type:** Function

**Purpose:** Retrieves or evaluates overdue grace days information.

**Signature**

```sql
function get_overdue_grace_days(p_product_code in number,
                                  p_acc_type     in varchar2) return number;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_product_code` | IN | Supplied `p_product_code` input (number) |
| `p_acc_type` | IN | Loan account type |

**Returns:** `number` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Reads `PKRD_TURKOD_PR` to obtain operation inputs or existing loan data.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-payments-and-balances)

---

<a id="get-next-plan-pym"></a>
#### get_next_Plan_Pym

**Type:** Function

**Purpose:** Retrieves or evaluates next plan pym information.

**Signature**

```sql
Function get_next_Plan_Pym(p_doc_no   In Varchar2,
                             P_date     In Date,
                             p_acc_type in varchar2) Return Number;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_doc_no` | IN | Loan document identifier |
| `P_date` | IN | Effective/processing date |
| `p_acc_type` | IN | Loan account type |

**Returns:** `Number` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Reads `LOAN_PAYMENT_PLAN` to obtain operation inputs or existing loan data.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** No explicit business error identified; see [Error Handling](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-payments-and-balances)

---

<a id="get-plan-payment-amount"></a>
#### get_plan_payment_amount

**Type:** Function

**Purpose:** Retrieves or evaluates plan payment amount information.

**Signature**

```sql
function get_plan_payment_amount(p_doc_no   in varchar2,
                                   p_date     in date default glbl.getsysdate,
                                   p_acc_type in varchar2 default null)
    return number;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_doc_no` | IN | Loan document identifier |
| `p_date` | IN | Effective/processing date |
| `p_acc_type` | IN | Loan account type |

**Returns:** `number` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Determines whether the loan uses tranche-specific plan information.
- Reads the relevant plan amount for the date and account type.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** `LOAN_TRANCHE_API` · [Dependency register](dependencies.md).

**Errors:** No explicit business error identified; see [Error Handling](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-payments-and-balances)

---

<a id="domain-payment-schedules-and-dates"></a>
## Payment schedules and dates

**Responsibility:** Produces and adjusts repayment schedules, installment dates, and grace-period information.

[↑ API Index](#api-index)

### Procedures

<a id="recalculate-int-payment-plan"></a>
#### recalculate_int_payment_plan

**Type:** Procedure

**Purpose:** Performs the recalculate int payment plan operation for the supplied inputs.

**Signature**

```sql
procedure recalculate_int_payment_plan(p_doc_no               in varchar2,
                                         p_acc_type             in varchar2,
                                         p_main_amount          in number,
                                         p_INT_RATIO            in number,
                                         p_int_calc_type        in varchar2,
                                         p_schedule_update_type in number);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_doc_no` | IN | Loan document identifier |
| `p_acc_type` | IN | Loan account type |
| `p_main_amount` | IN | Supplied `p_main_amount` input (number) |
| `p_INT_RATIO` | IN | Supplied `p_INT_RATIO` input (number) |
| `p_int_calc_type` | IN | Supplied `p_int_calc_type` input (varchar2) |
| `p_schedule_update_type` | IN | Supplied `p_schedule_update_type` input (number) |

**Business Logic**

- Recalculates scheduled interest amounts using principal, rate, interest calculation convention and schedule update mode.
- Updates matching interest repayment plan records.

**Business Rules**

- p_schedule_update_type should be 3 or 4!

**Dependencies:** `GLBL_FAIZ` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-payment-schedules-and-dates)

---

<a id="do-schedule-allignment"></a>
#### do_schedule_allignment

**Type:** Procedure

**Purpose:** Performs the schedule allignment operation for the supplied inputs.

**Signature**

```sql
Procedure do_schedule_allignment(p_doc_no         In Varchar2,
                                   p_payment_amount In Number,
                                   p_acc_type       In Varchar2,
                                   p_date           In Date default glbl.getsysdate);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_doc_no` | IN | Loan document identifier |
| `p_payment_amount` | IN | Supplied `p_payment_amount` input (Number) |
| `p_acc_type` | IN | Loan account type |
| `p_date` | IN | Effective/processing date |

**Business Logic**

- Reads `LOAN_PAYMENT_PLAN` to obtain operation inputs or existing loan data.
- Changes `LOAN_PAYMENT_PLAN` as part of the operation.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-payment-schedules-and-dates)

---

<a id="do-com-schedule-allignment"></a>
#### do_com_schedule_allignment

**Type:** Procedure

**Purpose:** Performs the com schedule allignment operation for the supplied inputs.

**Signature**

```sql
Procedure do_com_schedule_allignment(p_doc_no      In Varchar2,
                                       p_option_code In Varchar2,
                                       p_amount      In Number,
                                       p_plan_type   In Varchar2,
                                       p_mig_status  In Number Default 0);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_doc_no` | IN | Loan document identifier |
| `p_option_code` | IN | Supplied `p_option_code` input (Varchar2) |
| `p_amount` | IN | Amount supplied for processing |
| `p_plan_type` | IN | Supplied `p_plan_type` input (Varchar2) |
| `p_mig_status` | IN | Supplied `p_mig_status` input (Number) |

**Business Logic**

- Reads `KRD_TESIS`, `KRD_KOM_PLAN_DETAY` to obtain operation inputs or existing loan data.
- Changes `KRD_KOM_PLAN_DETAY`, `CS_ACCOUNT` as part of the operation.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** `GLOG` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-payment-schedules-and-dates)

---

<a id="get-special-schedule"></a>
#### get_special_schedule

**Type:** Procedure

**Purpose:** Retrieves or evaluates special schedule information.

**Signature**

```sql
Procedure get_special_schedule(p_doc_no             In Varchar2,
                                 p_begin_date         in Date Default Glbl.Getsysdate,
                                 p_offer_amount       In Number,
                                 p_int_ratio          In Number,
                                 p_int_calc_type      in varchar2,
                                 p_calc_int_int_grace in varchar2,
                                 p_annuity_amount     in Number Default Null,
                                 p_remain_int_amount  in number default 0);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_doc_no` | IN | Loan document identifier |
| `p_begin_date` | IN | Supplied `p_begin_date` input (Date) |
| `p_offer_amount` | IN | Supplied `p_offer_amount` input (Number) |
| `p_int_ratio` | IN | Supplied `p_int_ratio` input (Number) |
| `p_int_calc_type` | IN | Supplied `p_int_calc_type` input (varchar2) |
| `p_calc_int_int_grace` | IN | Supplied `p_calc_int_int_grace` input (varchar2) |
| `p_annuity_amount` | IN | Supplied `p_annuity_amount` input (Number) |
| `p_remain_int_amount` | IN | Supplied `p_remain_int_amount` input (number) |

**Business Logic**

- Reads `ODEME_PLAN_TMP2` to obtain operation inputs or existing loan data.
- Changes `ODEME_PLAN_TMP2` as part of the operation.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** `GLBL_FAIZ` · [Dependency register](dependencies.md).

**Errors:** No explicit business error identified; see [Error Handling](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-payment-schedules-and-dates)

---

<a id="get-created-schedule"></a>
#### get_created_schedule

**Type:** Procedure

**Purpose:** Retrieves or evaluates created schedule information.

**Signature**

```sql
Procedure get_created_schedule(p_fid number);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_fid` | IN | Supplied `p_fid` input (number) |

**Business Logic**

- Reads `CREATE_SCHEDULE_PARAMETRS` to obtain operation inputs or existing loan data.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-payment-schedules-and-dates)

---

<a id="create-schedule"></a>
#### create_schedule

**Type:** Procedure

**Purpose:** Generates and persists a loan repayment schedule from the supplied terms.

**Signature**

```sql
procedure create_schedule(p_schedule_no          number,
                            p_coll_name            varchar2 default null,
                            p_fk_id                number default null,
                            p_doc_no               varchar2 default 'XXX',
                            p_memorandum_id        varchar2 default null,
                            p_customer_no          number default null,
                            p_tx_fid               number default null,
                            p_begin_date           date default glbl.getsysdate,
                            p_last_int_Calc_Date   date default glbl.getsysdate - 1,
                            p_main_pymt_date       date,
                            p_int_pymt_date        date,
                            p_pymt_day             number default null,
                            p_end_date             date,
                            p_offer_amount         number,
                            p_ovd_main_amount      number default 0,
                            p_int_ratio            number,
                            p_int_calc_type        varchar2,
                            p_annuity_amount       number default null,
                            p_max_annuity_amount   number default null,
                            p_min_main_pay_amount  number default null,
                            p_remain_int_amount    number default 0,
                            p_main_grace_period    varchar2 default null,
                            p_int_grace_period     varchar2 default null,
                            p_main_pymt_period     number default 1,
                            p_int_pymt_period      number default 1,
                            p_product_code         number default null,
                            p_same_annuity         varchar2 default 'N',
                            p_calc_int_in_grace    varchar2 default 'Y',
                            p_return_type          varchar2 default 'NO_ZERO',
                            p_rest_main_pay_amount number default null,
                            p_rest_main_pay_months number default null,
                            p_loan_flow_rate_tab   LOAN_FLOW_RATE_TAB default null,
                            p_loan_stop_rate_tab   LOAN_STOP_RATE_TAB default null,
                            p_special_dates        loan_special_dates_tab default null);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_schedule_no` | IN | Supplied `p_schedule_no` input (number) |
| `p_coll_name` | IN | Supplied `p_coll_name` input (varchar2) |
| `p_fk_id` | IN | Supplied `p_fk_id` input (number) |
| `p_doc_no` | IN | Loan document identifier |
| `p_memorandum_id` | IN | Supplied `p_memorandum_id` input (varchar2) |
| `p_customer_no` | IN | Customer identifier |
| `p_tx_fid` | IN | Transaction identifier |
| `p_begin_date` | IN | Supplied `p_begin_date` input (date) |
| `p_last_int_Calc_Date` | IN | Supplied `p_last_int_Calc_Date` input (date) |
| `p_main_pymt_date` | IN | Supplied `p_main_pymt_date` input (date) |
| `p_int_pymt_date` | IN | Supplied `p_int_pymt_date` input (date) |
| `p_pymt_day` | IN | Supplied `p_pymt_day` input (number) |
| `p_end_date` | IN | Supplied `p_end_date` input (date) |
| `p_offer_amount` | IN | Supplied `p_offer_amount` input (number) |
| `p_ovd_main_amount` | IN | Supplied `p_ovd_main_amount` input (number) |
| `p_int_ratio` | IN | Supplied `p_int_ratio` input (number) |
| `p_int_calc_type` | IN | Supplied `p_int_calc_type` input (varchar2) |
| `p_annuity_amount` | IN | Supplied `p_annuity_amount` input (number) |
| `p_max_annuity_amount` | IN | Supplied `p_max_annuity_amount` input (number) |
| `p_min_main_pay_amount` | IN | Supplied `p_min_main_pay_amount` input (number) |
| `p_remain_int_amount` | IN | Supplied `p_remain_int_amount` input (number) |
| `p_main_grace_period` | IN | Supplied `p_main_grace_period` input (varchar2) |
| `p_int_grace_period` | IN | Supplied `p_int_grace_period` input (varchar2) |
| `p_main_pymt_period` | IN | Supplied `p_main_pymt_period` input (number) |
| `p_int_pymt_period` | IN | Supplied `p_int_pymt_period` input (number) |
| `p_product_code` | IN | Supplied `p_product_code` input (number) |
| `p_same_annuity` | IN | Supplied `p_same_annuity` input (varchar2) |
| `p_calc_int_in_grace` | IN | Supplied `p_calc_int_in_grace` input (varchar2) |
| `p_return_type` | IN | Supplied `p_return_type` input (varchar2) |
| `p_rest_main_pay_amount` | IN | Supplied `p_rest_main_pay_amount` input (number) |
| `p_rest_main_pay_months` | IN | Supplied `p_rest_main_pay_months` input (number) |
| `p_loan_flow_rate_tab` | IN | Supplied `p_loan_flow_rate_tab` input (LOAN_FLOW_RATE_TAB) |
| `p_loan_stop_rate_tab` | IN | Supplied `p_loan_stop_rate_tab` input (LOAN_STOP_RATE_TAB) |
| `p_special_dates` | IN | Supplied `p_special_dates` input (loan_special_dates_tab) |

**Business Logic**

- Prepares or persists a loan schedule using the supplied schedule number and associated loan/memorandum parameters.
- Uses the selected dates, repayment intervals and rates to determine the generated plan.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** No explicit business error identified; see [Error Handling](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-payment-schedules-and-dates)

---

<a id="update-payment-plan"></a>
#### UPDATE_PAYMENT_PLAN

**Type:** Procedure

**Purpose:** Updates the repayment plan of a specified loan.

**Signature**

```sql
PROCEDURE UPDATE_PAYMENT_PLAN(
                              P_DOC_NO             varchar2);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `P_DOC_NO` | IN | Loan document identifier |

**Business Logic**

- Loads loan and temporary payment plan data for the requested document.
- Applies the plan update using the stored account and schedule information.

**Business Rules**

- This operation cannot be initialized when [with_tranche_info_yn] =

**Dependencies:** `API_CALENDAR`, `TRN_BROKER`, `GAIA` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-payment-schedules-and-dates)

---

### Functions

<a id="get-formatted-grace-from-list"></a>
#### get_formatted_grace_from_list

**Type:** Function

**Purpose:** Retrieves or evaluates formatted grace from list information.

**Signature**

```sql
function get_formatted_grace_from_list(p_period_list in varchar2)
    return varchar2;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_period_list` | IN | Supplied `p_period_list` input (varchar2) |

**Returns:** `varchar2` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Computes or delegates the result from supplied parameters; no direct database write was identified in this method body.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-payment-schedules-and-dates)

---

<a id="get-grace-info"></a>
#### get_grace_info

**Type:** Function

**Purpose:** Retrieves or evaluates grace info information.

**Signature**

```sql
function get_grace_info(p_Doc_No          In Varchar2,
                          p_period_end_date in date,
                          p_acc_type        In Varchar2 default 'A',
                          p_info_type       in varchar2) Return varchar2;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_Doc_No` | IN | Loan document identifier |
| `p_period_end_date` | IN | Supplied `p_period_end_date` input (date) |
| `p_acc_type` | IN | Loan account type |
| `p_info_type` | IN | Supplied `p_info_type` input (varchar2) |

**Returns:** `varchar2` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Reads `LOAN_PAYMENT_PLAN` to obtain operation inputs or existing loan data.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-payment-schedules-and-dates)

---

<a id="get-commission-schedule"></a>
#### get_commission_schedule

**Type:** Function

**Purpose:** Retrieves or evaluates commission schedule information.

**Signature**

```sql
Function get_commission_schedule(p_begin_date    In Date,
                                   p_end_date      In Date,
                                   p_amount        In Number,
                                   p_int_calc_type in varchar2)
    Return Krd_Kom_Plan_Tt
    Pipelined;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_begin_date` | IN | Supplied `p_begin_date` input (Date) |
| `p_end_date` | IN | Supplied `p_end_date` input (Date) |
| `p_amount` | IN | Amount supplied for processing |
| `p_int_calc_type` | IN | Supplied `p_int_calc_type` input (varchar2) |

**Returns:** `Krd_Kom_Plan_Tt` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Delegates related processing to `GLBL_FAIZ`, `GNI_MESSAGE`, `GLBL_TARIH`.
- Pipelines generated rows to the caller.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** `GLBL_FAIZ`, `GNI_MESSAGE`, `GLBL_TARIH` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-payment-schedules-and-dates)

---

<a id="add-months-for-loan"></a>
#### add_months_for_loan

**Type:** Function

**Purpose:** Calculates a loan-adjusted date after applying a month offset and optional target day.

**Signature**

```sql
function add_months_for_loan(p_date   date,
                               p_months number,
                               p_day    number default null) return date;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_date` | IN | Effective/processing date |
| `p_months` | IN | Supplied `p_months` input (number) |
| `p_day` | IN | Supplied `p_day` input (number) |

**Returns:** `date` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Computes or delegates the result from supplied parameters; no direct database write was identified in this method body.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** No explicit business error identified; see [Error Handling](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-payment-schedules-and-dates)

---

<a id="get-plan-month-count"></a>
#### get_Plan_Month_Count

**Type:** Function

**Purpose:** Retrieves or evaluates plan month count information.

**Signature**

```sql
Function get_Plan_Month_Count(p_Start_Date    In Date,
                                p_End_Date      In Date,
                                p_int_calc_type varchar2 default '30/360 AZ',
                                p_work_days     varchar2 default 'Y',
                                p_pymt_day      number default null)
    Return Number;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_Start_Date` | IN | Supplied `p_Start_Date` input (Date) |
| `p_End_Date` | IN | Supplied `p_End_Date` input (Date) |
| `p_int_calc_type` | IN | Supplied `p_int_calc_type` input (varchar2) |
| `p_work_days` | IN | Supplied `p_work_days` input (varchar2) |
| `p_pymt_day` | IN | Supplied `p_pymt_day` input (number) |

**Returns:** `Number` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Delegates related processing to `GLBL_FAIZ`.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** `GLBL_FAIZ` · [Dependency register](dependencies.md).

**Errors:** No explicit business error identified; see [Error Handling](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-payment-schedules-and-dates)

---

<a id="get-plan-paid-month-count"></a>
#### get_plan_paid_month_count

**Type:** Function

**Purpose:** Retrieves or evaluates plan paid month count information.

**Signature**

```sql
function get_plan_paid_month_count(p_doc_no in varchar2,
                                     p_term   in number,
                                     p_date   in date) return number;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_doc_no` | IN | Loan document identifier |
| `p_term` | IN | Supplied `p_term` input (number) |
| `p_date` | IN | Effective/processing date |

**Returns:** `number` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Computes or delegates the result from supplied parameters; no direct database write was identified in this method body.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-payment-schedules-and-dates)

---

<a id="get-plan-error"></a>
#### get_plan_error

**Type:** Function

**Purpose:** Retrieves or evaluates plan error information.

**Signature**

```sql
Function get_plan_error(p_doc_no varchar2,
                          p_date   date default glbl.getsysdate)
    return varchar2;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_doc_no` | IN | Loan document identifier |
| `p_date` | IN | Effective/processing date |

**Returns:** `varchar2` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Delegates related processing to `GLBL`.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** `GLBL` · [Dependency register](dependencies.md).

**Errors:** No explicit business error identified; see [Error Handling](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-payment-schedules-and-dates)

---

<a id="get-annuity-amount"></a>
#### get_Annuity_Amount

**Type:** Function

**Purpose:** Retrieves or evaluates annuity amount information.

**Signature**

```sql
Function get_Annuity_Amount(p_Doc_No      In Varchar2,
                              p_return_type In varchar2 default 'NO_ZERO')
    Return Number;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_Doc_No` | IN | Loan document identifier |
| `p_return_type` | IN | Supplied `p_return_type` input (varchar2) |

**Returns:** `Number` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Reads `LOAN_PAYMENT_PLAN` to obtain operation inputs or existing loan data.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** No explicit business error identified; see [Error Handling](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-payment-schedules-and-dates)

---

<a id="get-pym-startdate"></a>
#### get_Pym_Startdate

**Type:** Function

**Purpose:** Retrieves or evaluates pym startdate information.

**Signature**

```sql
Function get_Pym_Startdate(p_Doc_No          In Varchar2,
                             p_pymt_date       In Date,
                             p_pymt_day        In Number,
                             p_pymt_period     In Number,
                             p_acc_type        In varchar2,
                             p_loan_end_Date   in date,
                             p_check_is_closed in varchar2 default 'Y')
    Return Date;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_Doc_No` | IN | Loan document identifier |
| `p_pymt_date` | IN | Supplied `p_pymt_date` input (Date) |
| `p_pymt_day` | IN | Supplied `p_pymt_day` input (Number) |
| `p_pymt_period` | IN | Supplied `p_pymt_period` input (Number) |
| `p_acc_type` | IN | Loan account type |
| `p_loan_end_Date` | IN | Supplied `p_loan_end_Date` input (date) |
| `p_check_is_closed` | IN | Supplied `p_check_is_closed` input (varchar2) |

**Returns:** `Date` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Reads `LOAN_PAYMENT_PLAN` to obtain operation inputs or existing loan data.
- Delegates related processing to `GLBL_TARIH`, `GNI_MESSAGE`, `GLBL_FAIZ`.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** `GLBL_TARIH`, `GNI_MESSAGE`, `GLBL_FAIZ` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-payment-schedules-and-dates)

---

<a id="is-payment-date"></a>
#### is_Payment_Date

**Type:** Function

**Purpose:** Retrieves or evaluates payment date information.

**Signature**

```sql
Function is_Payment_Date(p_Document_No In Varchar2, p_Date Date)
    Return Varchar2;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_Document_No` | IN | Supplied `p_Document_No` input (Varchar2) |
| `p_Date` | IN | Effective/processing date |

**Returns:** `Varchar2` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Reads `LOAN_PAYMENT_PLAN` to obtain operation inputs or existing loan data.
- Delegates related processing to `GLBL_TARIH`.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** `GLBL_TARIH` · [Dependency register](dependencies.md).

**Errors:** No explicit business error identified; see [Error Handling](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-payment-schedules-and-dates)

---

<a id="get-schedule-from-memo"></a>
#### get_schedule_from_memo

**Type:** Function

**Purpose:** Retrieves or evaluates schedule from memo information.

**Signature**

```sql
function get_schedule_from_memo(p_memorandum_id varchar2,
                                  p_int_ratio     number,
                                  p_int_calc_type varchar2,
                                  p_int_amount    number) return SCHEDULE_TT
    pipelined;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_memorandum_id` | IN | Supplied `p_memorandum_id` input (varchar2) |
| `p_int_ratio` | IN | Supplied `p_int_ratio` input (number) |
| `p_int_calc_type` | IN | Supplied `p_int_calc_type` input (varchar2) |
| `p_int_amount` | IN | Supplied `p_int_amount` input (number) |

**Returns:** `SCHEDULE_TT` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Reads `KRD_SCOR_ODEME_PLAN` to obtain operation inputs or existing loan data.
- Delegates related processing to `GLBL_FAIZ`.
- Pipelines generated rows to the caller.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** `GLBL_FAIZ` · [Dependency register](dependencies.md).

**Errors:** No explicit business error identified; see [Error Handling](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-payment-schedules-and-dates)

---

<a id="get-standart-schedule"></a>
#### get_standart_schedule

**Type:** Function

**Purpose:** Produces a standard repayment schedule from loan terms and date rules.

**Signature**

```sql
function get_standart_schedule(p_begin_date          date default glbl.getsysdate,
                                 p_main_pymt_date      date,
                                 p_int_pymt_date       date,
                                 p_pymt_day            number default null,
                                 p_end_date            date,
                                 p_offer_amount        number,
                                 p_ovd_main_amount     number default 0,
                                 p_int_calc_type       varchar2,
                                 p_main_grace_period   varchar2 default null,
                                 p_int_grace_period    varchar2 default null,
                                 p_remain_int_amount   number default 0,
                                 p_min_main_pay_amount number default null,
                                 p_calc_int_in_grace   varchar2 default 'Y',
                                 p_work_days           varchar2 default 'Y',
                                 p_loan_flow_rate_tab LOAN_FLOW_RATE_TAB default null,
                                 p_loan_stop_rate_tab LOAN_STOP_RATE_TAB default null,
                                 p_special_dates      loan_special_dates_tab default null)
    return SCHEDULE_TT
    pipelined;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_begin_date` | IN | Supplied `p_begin_date` input (date) |
| `p_main_pymt_date` | IN | Supplied `p_main_pymt_date` input (date) |
| `p_int_pymt_date` | IN | Supplied `p_int_pymt_date` input (date) |
| `p_pymt_day` | IN | Supplied `p_pymt_day` input (number) |
| `p_end_date` | IN | Supplied `p_end_date` input (date) |
| `p_offer_amount` | IN | Supplied `p_offer_amount` input (number) |
| `p_ovd_main_amount` | IN | Supplied `p_ovd_main_amount` input (number) |
| `p_int_calc_type` | IN | Supplied `p_int_calc_type` input (varchar2) |
| `p_main_grace_period` | IN | Supplied `p_main_grace_period` input (varchar2) |
| `p_int_grace_period` | IN | Supplied `p_int_grace_period` input (varchar2) |
| `p_remain_int_amount` | IN | Supplied `p_remain_int_amount` input (number) |
| `p_min_main_pay_amount` | IN | Supplied `p_min_main_pay_amount` input (number) |
| `p_calc_int_in_grace` | IN | Supplied `p_calc_int_in_grace` input (varchar2) |
| `p_work_days` | IN | Supplied `p_work_days` input (varchar2) |
| `p_loan_flow_rate_tab` | IN | Supplied `p_loan_flow_rate_tab` input (LOAN_FLOW_RATE_TAB) |
| `p_loan_stop_rate_tab` | IN | Supplied `p_loan_stop_rate_tab` input (LOAN_STOP_RATE_TAB) |
| `p_special_dates` | IN | Supplied `p_special_dates` input (loan_special_dates_tab) |

**Returns:** `SCHEDULE_TT` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Generates principal and interest plan rows from payment dates, terms, grace settings, and rate flow inputs.
- Pipelines the resulting schedule.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** No explicit business error identified; see [Error Handling](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-payment-schedules-and-dates)

---

<a id="get-annuity-schedule"></a>
#### get_annuity_schedule

**Type:** Function

**Purpose:** Produces an annuity repayment schedule using supplied loan terms and payment constraints.

**Signature**

```sql
function get_annuity_schedule(p_begin_date      date,
                                p_main_pymt_date  date,
                                p_int_pymt_date   date,
                                p_pymt_day        number default null,
                                p_end_date        date,
                                p_offer_amount    number,
                                p_ovd_main_amount number default 0,
                                p_int_calc_type   varchar2,
                                p_main_grace_period varchar2 default null,
                                p_int_grace_period  varchar2 default null,
                                p_annuity_amount     number default null,
                                p_max_annuity_amount number default null,
                                p_remain_int_amount  number default 0,
                                p_work_days         varchar2 default 'Y',
                                p_own_annuity       varchar2 default 'N',
                                p_calc_int_in_grace varchar2 default 'Y',
                                p_is_mortgage       varchar2 default 'N',
                                p_max_iteration number default null,
                                p_rest_main_pay_amount number default null,
                                p_rest_main_pay_months number default null,
                                p_loan_flow_rate_tab LOAN_FLOW_RATE_TAB default null,
                                p_loan_stop_rate_tab LOAN_STOP_RATE_TAB default null,
                                p_special_dates      loan_special_dates_tab default null)
    return SCHEDULE_TT
    pipelined;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_begin_date` | IN | Supplied `p_begin_date` input (date) |
| `p_main_pymt_date` | IN | Supplied `p_main_pymt_date` input (date) |
| `p_int_pymt_date` | IN | Supplied `p_int_pymt_date` input (date) |
| `p_pymt_day` | IN | Supplied `p_pymt_day` input (number) |
| `p_end_date` | IN | Supplied `p_end_date` input (date) |
| `p_offer_amount` | IN | Supplied `p_offer_amount` input (number) |
| `p_ovd_main_amount` | IN | Supplied `p_ovd_main_amount` input (number) |
| `p_int_calc_type` | IN | Supplied `p_int_calc_type` input (varchar2) |
| `p_main_grace_period` | IN | Supplied `p_main_grace_period` input (varchar2) |
| `p_int_grace_period` | IN | Supplied `p_int_grace_period` input (varchar2) |
| `p_annuity_amount` | IN | Supplied `p_annuity_amount` input (number) |
| `p_max_annuity_amount` | IN | Supplied `p_max_annuity_amount` input (number) |
| `p_remain_int_amount` | IN | Supplied `p_remain_int_amount` input (number) |
| `p_work_days` | IN | Supplied `p_work_days` input (varchar2) |
| `p_own_annuity` | IN | Supplied `p_own_annuity` input (varchar2) |
| `p_calc_int_in_grace` | IN | Supplied `p_calc_int_in_grace` input (varchar2) |
| `p_is_mortgage` | IN | Supplied `p_is_mortgage` input (varchar2) |
| `p_max_iteration` | IN | Supplied `p_max_iteration` input (number) |
| `p_rest_main_pay_amount` | IN | Supplied `p_rest_main_pay_amount` input (number) |
| `p_rest_main_pay_months` | IN | Supplied `p_rest_main_pay_months` input (number) |
| `p_loan_flow_rate_tab` | IN | Supplied `p_loan_flow_rate_tab` input (LOAN_FLOW_RATE_TAB) |
| `p_loan_stop_rate_tab` | IN | Supplied `p_loan_stop_rate_tab` input (LOAN_STOP_RATE_TAB) |
| `p_special_dates` | IN | Supplied `p_special_dates` input (loan_special_dates_tab) |

**Returns:** `SCHEDULE_TT` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Builds installment data from principal, term, interest convention, grace settings and annuity options.
- Pipelines calculated repayment rows.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** No explicit business error identified; see [Error Handling](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-payment-schedules-and-dates)

---

<a id="domain-interest-penalties-and-rates"></a>
## Interest, penalties and rates

**Responsibility:** Calculates or retrieves interest, penalty bases, rates, and recognition information.

[↑ API Index](#api-index)

### Procedures

<a id="get-interest-calc-info"></a>
#### get_interest_calc_info

**Type:** Procedure

**Purpose:** Determines interest calculation day counts and year basis from calculation conventions.

**Signature**

```sql
procedure get_interest_calc_info(p_last_calc_date       in date,
                                   p_pymt_day             in number,
                                   p_trn_date             in date,
                                   p_int_calc_type        in varchar2,
                                   p_rate_type            in varchar2,
                                   p_int_rate_periodicity in varchar2,
                                   p_calc_day_count       out number,
                                   p_year_day_count       out number);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_last_calc_date` | IN | Supplied `p_last_calc_date` input (date) |
| `p_pymt_day` | IN | Supplied `p_pymt_day` input (number) |
| `p_trn_date` | IN | Supplied `p_trn_date` input (date) |
| `p_int_calc_type` | IN | Supplied `p_int_calc_type` input (varchar2) |
| `p_rate_type` | IN | Supplied `p_rate_type` input (varchar2) |
| `p_int_rate_periodicity` | IN | Supplied `p_int_rate_periodicity` input (varchar2) |
| `p_calc_day_count` | OUT | number value populated by the operation |
| `p_year_day_count` | OUT | number value populated by the operation |

**Business Logic**

- Reads `LOAN_INT_CALC_TYPES_PR` to obtain operation inputs or existing loan data.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-interest-penalties-and-rates)

---

<a id="loan-int-diff-operation"></a>
#### loan_int_diff_operation

**Type:** Procedure

**Purpose:** Provides loan int diff operation behavior for loan processing.

**Signature**

```sql
procedure loan_int_diff_operation(p_trn_date        in date,
                                    p_oper_type       in varchar2,
                                    p_trn_type        in varchar2,
                                    p_doc_no          in varchar2,
                                    p_acc_type        in varchar2,
                                    p_source_acc_type in varchar2,
                                    p_tx_fid          number,
                                    p_original_amount in number,
                                    p_eod_sod         in varchar2,
                                    p_payment_date    in date,
                                    p_plan_int_amount in number,
                                    p_int_amount      in number,
                                    p_calc_amount     out number);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_trn_date` | IN | Supplied `p_trn_date` input (date) |
| `p_oper_type` | IN | Operation type selector |
| `p_trn_type` | IN | Transaction direction/type selector |
| `p_doc_no` | IN | Loan document identifier |
| `p_acc_type` | IN | Loan account type |
| `p_source_acc_type` | IN | Supplied `p_source_acc_type` input (varchar2) |
| `p_tx_fid` | IN | Transaction identifier |
| `p_original_amount` | IN | Supplied `p_original_amount` input (number) |
| `p_eod_sod` | IN | EOD/SOD processing selector |
| `p_payment_date` | IN | Supplied `p_payment_date` input (date) |
| `p_plan_int_amount` | IN | Supplied `p_plan_int_amount` input (number) |
| `p_int_amount` | IN | Supplied `p_int_amount` input (number) |
| `p_calc_amount` | OUT | number value populated by the operation |

**Business Logic**

- Reads `LOAN_INT_CALCULATION_DIFF_HISTORY` to obtain operation inputs or existing loan data.
- Changes `LOAN_INT_CALCULATION_DIFF_HISTORY` as part of the operation.

**Business Rules**

- original_amount or residual_amount or calc_amount or sum_residual_amount or p_plan_int_amount or p_int_amount is negative
- Operation type must be INS, OPEN, CLOSE!

**Dependencies:** `GLBL` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-interest-penalties-and-rates)

---

<a id="do-int-calculation"></a>
#### do_int_calculation

**Type:** Procedure

**Purpose:** Calculates loan interest for eligible loans and configured processing dates.

**Signature**

```sql
procedure do_int_calculation(p_min_id  number default 0,
                               p_max_id  number default 999999999,
                               p_doc_no  in varchar2 default null,
                               p_eod_sod in varchar2 default 'E',
                               p_date    in date default glbl.getsysdate);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_min_id` | IN | Supplied `p_min_id` input (number) |
| `p_max_id` | IN | Supplied `p_max_id` input (number) |
| `p_doc_no` | IN | Loan document identifier |
| `p_eod_sod` | IN | EOD/SOD processing selector |
| `p_date` | IN | Effective/processing date |

**Business Logic**

- Selects eligible loan records for the given branch range, document and processing date.
- Applies configured loan interest conventions, account balances, and permitted stop/rate information.
- Processes interest results and operational exception handling for the EOD/SOD run.

**Business Rules**

- Product code not found in pkrd_turkod_pr table, pls check 22401 app for this loan product!
- Interest ratio cant be negative:
- Interest amount cant be negative!

**Dependencies:** `GLBL_TARIH`, `PR`, `GNI_UTILITY`, `LA`, `GLBL_FAIZ` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-interest-penalties-and-rates)

---

<a id="do-commission-recognition"></a>
#### do_commission_recognition

**Type:** Procedure

**Purpose:** Performs the commission recognition operation for the supplied inputs.

**Signature**

```sql
Procedure do_commission_recognition(p_doc_no varchar2 default null,
                                      Pdate    In Date Default Glbl.Getsysdate);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_doc_no` | IN | Loan document identifier |
| `Pdate` | IN | Supplied `Pdate` input (Date) |

**Business Logic**

- Reads `KRD_KOM_PLAN_DETAY`, `KRD_TESIS`, `KRD_KOM_EOD` to obtain operation inputs or existing loan data.
- Changes `KRD_KOM_EOD` as part of the operation.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** `GLBL_TARIH`, `GLBL_BAKIYE`, `KRD_EOD` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-interest-penalties-and-rates)

---

### Functions

<a id="get-amount-for-pen-calc-1"></a>
#### get_amount_for_pen_calc

**Type:** Function

**Purpose:** Determines the penalty calculation base using overdue amounts and applicable offsets.

**Signature**

```sql
function get_amount_for_pen_calc(p_date                    in date,
                                   p_doc_no                  in varchar2,
                                   p_ovd_balance             in number,
                                   p_is_pen_calc_on_int      in varchar2,
                                   p_is_exclude_coll_amount  in varchar2,
                                   p_overdue_min_amount_main in number,
                                   p_loan_end_date           in date)
    return number;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_date` | IN | Effective/processing date |
| `p_doc_no` | IN | Loan document identifier |
| `p_ovd_balance` | IN | Supplied `p_ovd_balance` input (number) |
| `p_is_pen_calc_on_int` | IN | Supplied `p_is_pen_calc_on_int` input (varchar2) |
| `p_is_exclude_coll_amount` | IN | Supplied `p_is_exclude_coll_amount` input (varchar2) |
| `p_overdue_min_amount_main` | IN | Supplied `p_overdue_min_amount_main` input (number) |
| `p_loan_end_date` | IN | Supplied `p_loan_end_date` input (date) |

**Returns:** `number` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Combines overdue principal and, when configured, outstanding overdue interest from plan rows.
- Optionally subtracts qualifying guarantee commitments; applies the overdue minimum and loan-end-date threshold.
- Returns a nonnegative penalty calculation base.

**Business Rules**

- Negative overdue input/balances are rejected.
- Where enabled, eligible guarantee commitments reduce the penalty base.
- The result is clamped to zero and the threshold/loan-end-date conditions are applied.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-interest-penalties-and-rates)

---

<a id="get-interest-calc-dates"></a>
#### get_interest_calc_dates

**Type:** Function

**Purpose:** Determines the dates applicable to an EOD/SOD interest calculation.

**Signature**

```sql
function get_interest_calc_dates(p_last_calc_access_date in date,
                                   p_eod_sod               in varchar2,
                                   p_int_calc_at           in varchar2)
    return loan_api.g_date_tab_type;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_last_calc_access_date` | IN | Supplied `p_last_calc_access_date` input (date) |
| `p_eod_sod` | IN | EOD/SOD processing selector |
| `p_int_calc_at` | IN | Supplied `p_int_calc_at` input (varchar2) |

**Returns:** `loan_api.g_date_tab_type` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Delegates related processing to `GLBL_TARIH`.

**Business Rules**

- p_int_calc_at param should be EOD or SOD!!
- P_EOD_SOD param should be E - EOD or S - SOD!!
- Interest calculation should be done at EOD or SOD!!

**Dependencies:** `GLBL_TARIH` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-interest-penalties-and-rates)

---

<a id="get-interest-calc-dates-ex"></a>
#### get_interest_calc_dates_ex

**Type:** Function

**Purpose:** Determines interest processing dates for the supplied date and EOD/SOD context.

**Signature**

```sql
function get_interest_calc_dates_ex(p_date        in date,
                                      p_eod_sod     in varchar2,
                                      p_int_calc_at in varchar2)
    return g_date_tab_type;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_date` | IN | Effective/processing date |
| `p_eod_sod` | IN | EOD/SOD processing selector |
| `p_int_calc_at` | IN | Supplied `p_int_calc_at` input (varchar2) |

**Returns:** `g_date_tab_type` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Delegates related processing to `GLBL_TARIH`.

**Business Rules**

- p_int_calc_at param should be EOD or SOD!!
- P_EOD_SOD param should be E - EOD or S - SOD!!
- Interest calculation should be done at EOD or SOD!!

**Dependencies:** `GLBL_TARIH` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-interest-penalties-and-rates)

---

<a id="get-basis-year-days-cnt"></a>
#### get_basis_year_days_cnt

**Type:** Function

**Purpose:** Retrieves or evaluates basyear days cnt information.

**Signature**

```sql
function get_basis_year_days_cnt(p_int_calc_type in varchar2,
                                   p_date          in date) return number;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_int_calc_type` | IN | Supplied `p_int_calc_type` input (varchar2) |
| `p_date` | IN | Effective/processing date |

**Returns:** `number` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Reads `LOAN_INT_CALC_TYPES_PR` to obtain operation inputs or existing loan data.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-interest-penalties-and-rates)

---

<a id="get-delay-int-rate"></a>
#### Get_Delay_Int_Rate

**Type:** Function

**Purpose:** Retrieves or evaluates delay int rate information.

**Signature**

```sql
Function Get_Delay_Int_Rate(p_Loan_Id    In Varchar2,
                              p_Delay_Type In Varchar2) Return Number;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_Loan_Id` | IN | Supplied `p_Loan_Id` input (Varchar2) |
| `p_Delay_Type` | IN | Supplied `p_Delay_Type` input (Varchar2) |

**Returns:** `Number` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Reads `KRD_TEKLIF_DETAY` to obtain operation inputs or existing loan data.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** No explicit business error identified; see [Error Handling](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-interest-penalties-and-rates)

---

<a id="get-amount-for-pen-calc-2"></a>
#### get_amount_for_pen_calc

**Type:** Function

**Purpose:** Determines the penalty calculation base using overdue amounts and applicable offsets.

**Signature**

```sql
Function get_amount_for_pen_calc(p_doc_no        In Varchar2,
                                   P_date          In Date,
                                   p_for_spec_days in varchar2 default 'N',
                                   p_int_calc_type in varchar2 default null)
    Return Number;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_doc_no` | IN | Loan document identifier |
| `P_date` | IN | Effective/processing date |
| `p_for_spec_days` | IN | Supplied `p_for_spec_days` input (varchar2) |
| `p_int_calc_type` | IN | Supplied `p_int_calc_type` input (varchar2) |

**Returns:** `Number` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Combines overdue principal and, when configured, outstanding overdue interest from plan rows.
- Optionally subtracts qualifying guarantee commitments; applies the overdue minimum and loan-end-date threshold.
- Returns a nonnegative penalty calculation base.

**Business Rules**

- p_for_spec_days must be Y or N!

**Dependencies:** `GLBL_FAIZ` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-interest-penalties-and-rates)

---

<a id="get-flow-ratio-info"></a>
#### get_flow_ratio_info

**Type:** Function

**Purpose:** Retrieves or evaluates flow ratio info information.

**Signature**

```sql
FUNCTION get_flow_ratio_info(p_doc_no    VARCHAR2,
                               p_date      DATE DEFAULT glbl.getsysdate,
                               p_full_info varchar2 default 'N')
    RETURN LOAN_FLOW_RATE_TAB;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_doc_no` | IN | Loan document identifier |
| `p_date` | IN | Effective/processing date |
| `p_full_info` | IN | Supplied `p_full_info` input (varchar2) |

**Returns:** `LOAN_FLOW_RATE_TAB` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Reads `LOAN_FLOW_RATIO_INFO` to obtain operation inputs or existing loan data.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** No explicit business error identified; see [Error Handling](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-interest-penalties-and-rates)

---

<a id="get-stop-ratio-info"></a>
#### get_stop_ratio_info

**Type:** Function

**Purpose:** Retrieves or evaluates stop ratio info information.

**Signature**

```sql
FUNCTION get_stop_ratio_info(p_doc_no    VARCHAR2,
                               p_date      DATE DEFAULT glbl.getsysdate,
                               p_full_info varchar2 default 'N',
                               p_info_type varchar2 default 'INT')
    RETURN LOAN_STOP_RATE_TAB;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_doc_no` | IN | Loan document identifier |
| `p_date` | IN | Effective/processing date |
| `p_full_info` | IN | Supplied `p_full_info` input (varchar2) |
| `p_info_type` | IN | Supplied `p_info_type` input (varchar2) |

**Returns:** `LOAN_STOP_RATE_TAB` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Reads `LOAN_STOP_RATIO_INFO` to obtain operation inputs or existing loan data.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** No explicit business error identified; see [Error Handling](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-interest-penalties-and-rates)

---

<a id="get-incorrect-days"></a>
#### get_incorrect_days

**Type:** Function

**Purpose:** Retrieves or evaluates incorrect days information.

**Signature**

```sql
function get_incorrect_days(p_date date) return NUMBER_TT
    pipelined;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_date` | IN | Effective/processing date |

**Returns:** `NUMBER_TT` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Computes or delegates the result from supplied parameters; no direct database write was identified in this method body.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** No explicit business error identified; see [Error Handling](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-interest-penalties-and-rates)

---

<a id="get-incorrect-days-count"></a>
#### get_incorrect_days_count

**Type:** Function

**Purpose:** Retrieves or evaluates incorrect days count information.

**Signature**

```sql
function get_incorrect_days_count(p_date date) return number;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_date` | IN | Effective/processing date |

**Returns:** `number` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Computes or delegates the result from supplied parameters; no direct database write was identified in this method body.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** No explicit business error identified; see [Error Handling](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-interest-penalties-and-rates)

---

<a id="domain-delinquency-and-status"></a>
## Delinquency and status

**Responsibility:** Determines overdue transitions, overdue dates, and related overdue processing.

[↑ API Index](#api-index)

### Procedures

<a id="do-overdue-transit-operation"></a>
#### do_overdue_transit_operation

**Type:** Procedure

**Purpose:** Processes overdue balance transitions for loans meeting overdue criteria.

**Signature**

```sql
Procedure do_overdue_transit_operation(p_min_id number default null,
                                         p_max_id number default null,
                                         p_doc_no in varchar2 default null,
                                         p_date   in date default glbl.getsysdate);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_min_id` | IN | Supplied `p_min_id` input (number) |
| `p_max_id` | IN | Supplied `p_max_id` input (number) |
| `p_doc_no` | IN | Loan document identifier |
| `p_date` | IN | Effective/processing date |

**Business Logic**

- Finds overdue transit candidates using outstanding plan amounts and overdue settings.
- Determines the required overdue movement and processes account/plan adjustments.

**Business Rules**

- Loan product code not found in pkrd_turkod_pr table!

**Dependencies:** `GNI_UTILITY`, `CL`, `CR`, `LOAN_REPORT_API` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-delinquency-and-status)

---

### Functions

<a id="get-ovd-trs-oper-type"></a>
#### get_ovd_trs_oper_type

**Type:** Function

**Purpose:** Determines the overdue-transit action from loan, schedule, grace-period, and balance conditions.

**Signature**

```sql
function get_ovd_trs_oper_type(p_date               in date,
                                 p_acc_type_group     in varchar2,
                                 p_plan_date          in date,
                                 p_overdue_grace_days in number,
                                 p_balance            in number,
                                 p_overdue_min_amount in number,
                                 p_ovd_balance        in number,
                                 p_loan_end_date      in date,
                                 p_loan_status        in varchar2,
                                 P_OVERDUE_GRACE_DAYS_TYPE IN VARCHAR2,
                                 P_PLAN_TYPE               IN VARCHAR2,
                                 p_doc_no                  IN VARCHAR2 DEFAULT NULL)
    return varchar2;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_date` | IN | Effective/processing date |
| `p_acc_type_group` | IN | Supplied `p_acc_type_group` input (varchar2) |
| `p_plan_date` | IN | Supplied `p_plan_date` input (date) |
| `p_overdue_grace_days` | IN | Supplied `p_overdue_grace_days` input (number) |
| `p_balance` | IN | Supplied `p_balance` input (number) |
| `p_overdue_min_amount` | IN | Supplied `p_overdue_min_amount` input (number) |
| `p_ovd_balance` | IN | Supplied `p_ovd_balance` input (number) |
| `p_loan_end_date` | IN | Supplied `p_loan_end_date` input (date) |
| `p_loan_status` | IN | Supplied `p_loan_status` input (varchar2) |
| `P_OVERDUE_GRACE_DAYS_TYPE` | IN | Supplied `P_OVERDUE_GRACE_DAYS_TYPE` input (VARCHAR2) |
| `P_PLAN_TYPE` | IN | Supplied `P_PLAN_TYPE` input (VARCHAR2) |
| `p_doc_no` | IN | Loan document identifier |

**Returns:** `varchar2` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Evaluates overdue age, grace period, balances, status and loan maturity.
- Returns the operation type applicable to overdue transit processing.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-delinquency-and-status)

---

<a id="get-ovd-date"></a>
#### get_ovd_date

**Type:** Function

**Purpose:** Retrieves or evaluates ovd date information.

**Signature**

```sql
Function get_ovd_date(p_doc_no   varchar2,
                        p_acc_type varchar2,
                        p_date     date default glbl.getsysdate, 
                        p_calc_mode varchar2 default 'DEFAULT'
                        ) return date;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_doc_no` | IN | Loan document identifier |
| `p_acc_type` | IN | Loan account type |
| `p_date` | IN | Effective/processing date |
| `p_calc_mode` | IN | Supplied `p_calc_mode` input (varchar2) |

**Returns:** `date` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Reads `KRD_TEKLIF_DETAY`, `GAIA.CS_ACCOUNT`, `LOAN_PAYMENT_PLAN`, `CS_ACCOUNT` to obtain operation inputs or existing loan data.
- Delegates related processing to `LOAN_TRANCHE_API`.

**Business Rules**

- p_calc_mode should be FOR_PEN_CALC - for penalty calculation, DEFAULT-for reporting

**Dependencies:** `LOAN_TRANCHE_API` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-delinquency-and-status)

---

<a id="get-ovd-date-old"></a>
#### get_ovd_date_old

**Type:** Function

**Purpose:** Retrieves or evaluates ovd date old information.

**Signature**

```sql
Function get_ovd_date_old(p_doc_no   varchar2,
                        p_acc_type varchar2,
                        p_date     date default glbl.getsysdate,
                        p_calc_mode varchar2 default 'DEFAULT') return date;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_doc_no` | IN | Loan document identifier |
| `p_acc_type` | IN | Loan account type |
| `p_date` | IN | Effective/processing date |
| `p_calc_mode` | IN | Supplied `p_calc_mode` input (varchar2) |

**Returns:** `date` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Reads `KRD_TEKLIF_DETAY`, `LOAN_PAYMENT_PLAN`, `CS_ACCOUNT` to obtain operation inputs or existing loan data.
- Delegates related processing to `LOAN_TRANCHE_API`.

**Business Rules**

- p_calc_mode should be FOR_PEN_CALC - for penalty calculation, DEFAULT-for reporting

**Dependencies:** `LOAN_TRANCHE_API` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-delinquency-and-status)

---

<a id="domain-limits-tranches-and-overdrafts"></a>
## Limits, tranches and overdrafts

**Responsibility:** Evaluates credit limits, creates tranches, and processes overdraft contracts.

[↑ API Index](#api-index)

### Procedures

<a id="evaluate-limit-amount"></a>
#### evaluate_limit_amount

**Type:** Procedure

**Purpose:** Evaluates and adjusts the available credit-line limit using loan and account information.

**Signature**

```sql
procedure evaluate_limit_amount(p_min_id        number default 0,
                                  p_max_id        number default 999999999,
                                  p_doc_no        in varchar2,
                                  p_caller_tx_fid in number default null);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_min_id` | IN | Supplied `p_min_id` input (number) |
| `p_max_id` | IN | Supplied `p_max_id` input (number) |
| `p_doc_no` | IN | Loan document identifier |
| `p_caller_tx_fid` | IN | Supplied `p_caller_tx_fid` input (number) |

**Business Logic**

- Calculates available limits from offered amounts, limit increases/decreases, and outstanding main amount.
- Uses loan-history tranche principal for non-revolving lines and mapped account balances for other lines.
- Posts the resulting limit difference in the appropriate debit/credit direction and records limit-evaluation history.

**Business Rules**

- Only eligible open credit-line/card loan records are examined.
- A category `667` record or an elapsed end date produces a zero computed limit.
- The limit difference determines posting direction; caller and document inputs affect commit behavior.

**Dependencies:** `LOAN_REPORT_API`, `GLBL_HESAP` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-limits-tranches-and-overdrafts)

---

<a id="do-create-tranche"></a>
#### do_create_tranche

**Type:** Procedure

**Purpose:** Performs the create tranche operation for the supplied inputs.

**Signature**

```sql
procedure do_create_tranche(p_contract_no    varchar2,
                              p_tranche_type   varchar2 default null,
                              p_tracnhe_term   varchar2 default null,
                              p_tranche_amount number,
                              p_int_com_amount number default null,
                              p_trn_type       in varchar2,
                              p_tx_fid         in out number);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_contract_no` | IN | Supplied `p_contract_no` input (varchar2) |
| `p_tranche_type` | IN | Supplied `p_tranche_type` input (varchar2) |
| `p_tracnhe_term` | IN | Supplied `p_tracnhe_term` input (varchar2) |
| `p_tranche_amount` | IN | Supplied `p_tranche_amount` input (number) |
| `p_int_com_amount` | IN | Supplied `p_int_com_amount` input (number) |
| `p_trn_type` | IN | Transaction direction/type selector |
| `p_tx_fid` | IN OUT | Transaction identifier |

**Business Logic**

- Reads `KRD_TEKLIF_DETAY`, `GLBL_TRANSACTION` to obtain operation inputs or existing loan data.
- Delegates related processing to `LOAN_TRANCHE_API`, `APEX_KRD2204_0_API_P`, `KRD2204_0_API`.

**Business Rules**

- p_trn_type should be CREATE - for create, DELETE - for delete

**Dependencies:** `LOAN_TRANCHE_API`, `APEX_KRD2204_0_API_P`, `KRD2204_0_API` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-limits-tranches-and-overdrafts)

---

<a id="create-overdrafts"></a>
#### create_overdrafts

**Type:** Procedure

**Purpose:** Creates or processes overdraft records for the selected customers or branch range.

**Signature**

```sql
procedure create_overdrafts(p_customer in number default null,
                              p_min_id   in number default null,
                              p_max_id   in number default null, 
                              p_oper_type in varchar2 default 'CREATE_OVERDRAFT');
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_customer` | IN | Supplied `p_customer` input (number) |
| `p_min_id` | IN | Supplied `p_min_id` input (number) |
| `p_max_id` | IN | Supplied `p_max_id` input (number) |
| `p_oper_type` | IN | Operation type selector |

**Business Logic**

- Selects customer/card/loan information for overdraft handling within the requested branch or customer scope.
- Performs the selected overdraft operation and related account updates.

**Business Rules**

- p_oper_type should be CREATE_OVERDRAFT or CLOSE_LOAN

**Dependencies:** `GLBL_HESAP`, `API_VISTA` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-limits-tranches-and-overdrafts)

---

### Functions

<a id="get-new-ov-cont-no"></a>
#### get_new_ov_cont_no

**Type:** Function

**Purpose:** Retrieves or evaluates new ov cont no information.

**Signature**

```sql
function get_new_ov_cont_no(p_branch_no in number,
                              p_cust_no   in number,
                              p_acc       in number) return varchar2;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_branch_no` | IN | Branch identifier |
| `p_cust_no` | IN | Supplied `p_cust_no` input (number) |
| `p_acc` | IN | Supplied `p_acc` input (number) |

**Returns:** `varchar2` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Reads `CS_ACCOUNT`, `KRD_TEKLIF_DETAY` to obtain operation inputs or existing loan data.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-limits-tranches-and-overdrafts)

---

<a id="domain-accounting-and-audit"></a>
## Accounting and audit

**Responsibility:** Creates accounting postings and retrieves accounting mappings and journal information.

[↑ API Index](#api-index)

### Procedures

<a id="table-log-operation"></a>
#### table_log_operation

**Type:** Procedure

**Purpose:** Provides table log operation behavior for loan processing.

**Signature**

```sql
procedure table_log_operation(p_doc_no     in varchar2,
                                p_table_name in varchar2,
                                p_tx_fid     in number,
                                p_oper_type  in varchar2);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_doc_no` | IN | Loan document identifier |
| `p_table_name` | IN | Supplied `p_table_name` input (varchar2) |
| `p_tx_fid` | IN | Transaction identifier |
| `p_oper_type` | IN | Operation type selector |

**Business Logic**

- Reads `LOAN_PAYMENT_PLAN`, `LOAN_PAYMENT_PLAN_LOG`, `LOAN_FLOW_RATIO_INFO`, `LOAN_FLOW_RATIO_INFO_LOG` to obtain operation inputs or existing loan data.
- Changes `OPERATIONS.`, `LOAN_PAYMENT_PLAN_LOG`, `LOAN_PAYMENT_PLAN`, `LOAN_FLOW_RATIO_INFO_LOG` as part of the operation.

**Business Rules**

- Oper type should be LOGGING-for logging or RESTORING-for restoring
- Table name should be [LOAN_PAYMENT_PLAN],[LOAN_FLOW_RATIO_INFO],[LOAN_STOP_RATIO_INFO],[LOAN_CATEGORY],[KRD_KOM_PLAN_DETAY]

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-accounting-and-audit)

---

<a id="do-journal-entry"></a>
#### do_journal_entry

**Type:** Procedure

**Purpose:** Creates or posts debit and credit accounting entries for a loan transaction.

**Signature**

```sql
Procedure do_journal_entry(p_entries_list  g_entries_list_tab,
                             p_trn_caller_id in number,
                             p_tx_fid        in out number,
                             p_trn_type      in varchar2,
                             p_is_eod        in varchar2 default 'Y');
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_entries_list` | IN | Supplied `p_entries_list` input (g_entries_list_tab) |
| `p_trn_caller_id` | IN | Supplied `p_trn_caller_id` input (number) |
| `p_tx_fid` | IN OUT | Transaction identifier |
| `p_trn_type` | IN | Transaction direction/type selector |
| `p_is_eod` | IN | Supplied `p_is_eod` input (varchar2) |

**Business Logic**

- Processes the supplied debit/credit entry records using transaction caller and transaction type inputs.
- Hands off accounting entry persistence to the internal journal services; the caller transaction ID is an IN OUT value.

**Business Rules**

- p_trn_type must be CREATE or POST!

**Dependencies:** `TRN_BROKER`, `GLBL_FUNCTIONS`, `GLBL_HESAP`, `PA_API#`, `MM_ACCOUNTING#` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-accounting-and-audit)

---

<a id="create-journal-entries"></a>
#### create_journal_entries

**Type:** Procedure

**Purpose:** Constructs journal entries for a configured loan operation.

**Signature**

```sql
procedure create_journal_entries(p_oper_type in varchar2,
                                   p_tx_fid    in number,
                                   p_trn_type  in varchar2);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_oper_type` | IN | Operation type selector |
| `p_tx_fid` | IN | Transaction identifier |
| `p_trn_type` | IN | Transaction direction/type selector |

**Business Logic**

- Reads `LOAN_OPERATION_DESC`, `LOAN_OPERATION_VOUCHER`, `SS_MUH1201_0_LOG` to obtain operation inputs or existing loan data.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-accounting-and-audit)

---

<a id="do-journal-control"></a>
#### do_journal_control

**Type:** Procedure

**Purpose:** Performs the journal control operation for the supplied inputs.

**Signature**

```sql
procedure do_journal_control(p_branch_id   IN Number,
                               p_customer_no IN Number,
                               p_account_sub IN Number);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_branch_id` | IN | Supplied `p_branch_id` input (Number) |
| `p_customer_no` | IN | Customer identifier |
| `p_account_sub` | IN | Supplied `p_account_sub` input (Number) |

**Business Logic**

- Reads `CS_ACCOUNT` to obtain operation inputs or existing loan data.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-accounting-and-audit)

---

### Functions

<a id="get-trn-caller-id"></a>
#### get_trn_caller_id

**Type:** Function

**Purpose:** Resolves the transaction caller identifier configured for an operation type.

**Signature**

```sql
function get_trn_caller_id(p_oper_type in varchar2) return number;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_oper_type` | IN | Operation type selector |

**Returns:** `number` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Reads `LOAN_OPERATION_DESC` to obtain operation inputs or existing loan data.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-accounting-and-audit)

---

<a id="get-voucher-data-from-query"></a>
#### get_voucher_data_from_query

**Type:** Function

**Purpose:** Executes a configured voucher query and organizes returned columns by result grouping.

**Signature**

```sql
function get_voucher_data_from_query(p_query       in varchar2,
                                       p_result_type in varchar2)
    return g_col_value_tab_map;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_query` | IN | Supplied `p_query` input (varchar2) |
| `p_result_type` | IN | Supplied `p_result_type` input (varchar2) |

**Returns:** `g_col_value_tab_map` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Computes or delegates the result from supplied parameters; no direct database write was identified in this method body.

**Business Rules**

- p_result_type should be SINGLE_ROW or MULTI_ROW!
- GROUP_CODE field is not defined in query or GROUP_CODE field is null!

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-accounting-and-audit)

---

<a id="get-gl-value"></a>
#### get_gl_value

**Type:** Function

**Purpose:** Retrieves or evaluates gl value information.

**Signature**

```sql
function get_gl_value(p_parameter_name in varchar2) return varchar2;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_parameter_name` | IN | Supplied `p_parameter_name` input (varchar2) |

**Returns:** `varchar2` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Reads `LOAN_GLOBAL_PARAMETERS_PR` to obtain operation inputs or existing loan data.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-accounting-and-audit)

---

<a id="domain-history-metadata-and-reversal"></a>
## History, metadata and reversal

**Responsibility:** Captures transaction metadata and loan operation history, and supports reversal of recorded changes.

[↑ API Index](#api-index)

### Procedures

<a id="clear-addtional-data"></a>
#### clear_addtional_data

**Type:** Procedure

**Purpose:** Performs the clear addtional data operation for the supplied inputs.

**Signature**

```sql
procedure clear_addtional_data(p_state varchar2 default 'CLEAR');
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_state` | IN | Supplied `p_state` input (varchar2) |

**Business Logic**

- Delegates related processing to `RUHA3H`.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** `RUHA3H` · [Dependency register](dependencies.md).

**Errors:** No explicit business error identified; see [Error Handling](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-history-metadata-and-reversal)

---

<a id="add-additional-group"></a>
#### add_additional_group

**Type:** Procedure

**Purpose:** Performs the add additional group operation for the supplied inputs.

**Signature**

```sql
procedure add_additional_group(p_tag_name varchar2 default null);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_tag_name` | IN | Supplied `p_tag_name` input (varchar2) |

**Business Logic**

- Delegates related processing to `RUHA3H`.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** `RUHA3H` · [Dependency register](dependencies.md).

**Errors:** No explicit business error identified; see [Error Handling](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-history-metadata-and-reversal)

---

<a id="add-additional-info-1"></a>
#### add_additional_info

**Type:** Procedure

**Purpose:** Performs the add additional info operation for the supplied inputs.

**Signature**

```sql
procedure add_additional_info(p_tag_name varchar2, p_value varchar2);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_tag_name` | IN | Supplied `p_tag_name` input (varchar2) |
| `p_value` | IN | Supplied `p_value` input (varchar2) |

**Business Logic**

- Changes `OPERATIONS.` as part of the operation.
- Delegates related processing to `RUHA3H`.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** `RUHA3H` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-history-metadata-and-reversal)

---

<a id="add-additional-info-2"></a>
#### add_additional_info

**Type:** Procedure

**Purpose:** Performs the add additional info operation for the supplied inputs.

**Signature**

```sql
procedure add_additional_info(p_tag_name varchar2, p_value date);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_tag_name` | IN | Supplied `p_tag_name` input (varchar2) |
| `p_value` | IN | Supplied `p_value` input (date) |

**Business Logic**

- Computes or delegates the result from supplied parameters; no direct database write was identified in this method body.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** No explicit business error identified; see [Error Handling](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-history-metadata-and-reversal)

---

<a id="add-column-update-1"></a>
#### add_column_update

**Type:** Procedure

**Purpose:** Performs the add column update operation for the supplied inputs.

**Signature**

```sql
procedure add_column_update(p_tag_name   varchar2,
                              p_old_value  varchar2,
                              p_new_value  varchar2,
                              p_tranche_no number default null);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_tag_name` | IN | Supplied `p_tag_name` input (varchar2) |
| `p_old_value` | IN | Supplied `p_old_value` input (varchar2) |
| `p_new_value` | IN | Supplied `p_new_value` input (varchar2) |
| `p_tranche_no` | IN | Tranche identifier |

**Business Logic**

- Reads `LOAN_HISTORY_MAPPING`, `LOAN_TRANCHE_INFO` to obtain operation inputs or existing loan data.
- Changes `OPERATIONS.` as part of the operation.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** `RUHA3H` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-history-metadata-and-reversal)

---

<a id="add-column-update-2"></a>
#### add_column_update

**Type:** Procedure

**Purpose:** Performs the add column update operation for the supplied inputs.

**Signature**

```sql
procedure add_column_update(p_tag_name   varchar2,
                              p_old_value  date,
                              p_new_value  date,
                              p_tranche_no number default null);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_tag_name` | IN | Supplied `p_tag_name` input (varchar2) |
| `p_old_value` | IN | Supplied `p_old_value` input (date) |
| `p_new_value` | IN | Supplied `p_new_value` input (date) |
| `p_tranche_no` | IN | Tranche identifier |

**Business Logic**

- Computes or delegates the result from supplied parameters; no direct database write was identified in this method body.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** No explicit business error identified; see [Error Handling](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-history-metadata-and-reversal)

---

<a id="finalize-addtional-process"></a>
#### finalize_addtional_process

**Type:** Procedure

**Purpose:** Performs the finalize addtional process operation for the supplied inputs.

**Signature**

```sql
procedure finalize_addtional_process(p_doc_no   varchar2,
                                       p_offer_id varchar2);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_doc_no` | IN | Loan document identifier |
| `p_offer_id` | IN | Supplied `p_offer_id` input (varchar2) |

**Business Logic**

- Delegates related processing to `LOAN_TRANCHE_API`.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** `LOAN_TRANCHE_API` · [Dependency register](dependencies.md).

**Errors:** No explicit business error identified; see [Error Handling](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-history-metadata-and-reversal)

---

<a id="reverse-update"></a>
#### reverse_update

**Type:** Procedure

**Purpose:** Reverses mapped loan field updates using recorded transaction history.

**Signature**

```sql
procedure reverse_update(p_tx_fid number);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_tx_fid` | IN | Transaction identifier |

**Business Logic**

- Reads change-log information for the transaction and restores previously recorded field values.
- Uses recorded change metadata to reconstruct reversal operations.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-history-metadata-and-reversal)

---

<a id="create-loan-history"></a>
#### create_loan_history

**Type:** Procedure

**Purpose:** Records the specified loan operation in transaction history.

**Signature**

```sql
procedure create_loan_history(p_oper_type VARCHAR2 default null,
                                p_doc_no    VARCHAR2 default null,
                                p_trn_date  DATE default glbl.getsysdate,
                                p_tx_fid    NUMBER,
                                p_trn_type  varchar2,
                                p_add_info  add_info_tab default null);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_oper_type` | IN | Operation type selector |
| `p_doc_no` | IN | Loan document identifier |
| `p_trn_date` | IN | Supplied `p_trn_date` input (DATE) |
| `p_tx_fid` | IN | Transaction identifier |
| `p_trn_type` | IN | Transaction direction/type selector |
| `p_add_info` | IN | Supplied `p_add_info` input (add_info_tab) |

**Business Logic**

- Resolves the requested loan operation and writes transaction-linked loan history details.
- Captures operation attributes and available additional information associated with the transaction.

**Business Rules**

- p_app_oper_code not found in loan_operation_desc table!
- p_trn_type must be I-insert, U-update, D-delete

**Dependencies:** `TRN_BROKER` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-history-metadata-and-reversal)

---

<a id="update-loan-history"></a>
#### update_loan_history

**Type:** Procedure

**Purpose:** Updates stored loan operation history using existing transaction information.

**Signature**

```sql
procedure update_loan_history(p_tx_fid number);
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_tx_fid` | IN | Transaction identifier |

**Business Logic**

- Reads `LOAN_OPERATION_HISTORY`, `GL_JOURNAL_LINES`, `CS_ACCOUNT`, `LOAN_OPERATION_DESC` to obtain operation inputs or existing loan data.
- Changes `LOAN_OPERATION_HISTORY` as part of the operation.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** `LOAN_TRANCHE_API` · [Dependency register](dependencies.md).

**Errors:** [Verified business/error conditions](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-history-metadata-and-reversal)

---

### Functions

<a id="get-additional-info"></a>
#### get_additional_info

**Type:** Function

**Purpose:** Retrieves or evaluates additional info information.

**Signature**

```sql
function get_additional_info(p_Tx_fid number, p_tag_name varchar2)
    return varchar2;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_Tx_fid` | IN | Transaction identifier |
| `p_tag_name` | IN | Supplied `p_tag_name` input (varchar2) |

**Returns:** `varchar2` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Reads `LOAN_OPERATION_HISTORY` to obtain operation inputs or existing loan data.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** No explicit business error identified; see [Error Handling](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-history-metadata-and-reversal)

---

<a id="is-online-offer"></a>
#### is_online_offer

**Type:** Function

**Purpose:** Retrieves or evaluates online offer information.

**Signature**

```sql
function is_online_offer(p_memorandum_id varchar2) return varchar2;
```

**Parameters**

| Parameter | Mode | Meaning |
|---|---|---|
| `p_memorandum_id` | IN | Supplied `p_memorandum_id` input (varchar2) |

**Returns:** `varchar2` result; interpretation follows the documented purpose and source processing.

**Business Logic**

- Reads `KRD_SCOR_MAIN` to obtain operation inputs or existing loan data.

**Business Rules**

No explicit business-specific rules identified in the supplied source.

**Dependencies:** [Dependency register](dependencies.md).

**Errors:** No explicit business error identified; see [Error Handling](error-handling.md).

[↑ API Index](#api-index) · [↑ Domain](#domain-history-metadata-and-reversal)

---

