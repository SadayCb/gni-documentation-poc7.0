# LOAN_API — Complete Public API Reference

**Package:** `GAIA.LOAN_API`  
**Source:** supplied Package Specification and Package Body  
**Verification:** static source inspection; runtime behavior and external packages have not been executed.

## Public API index

### Loan operations and controls

- [get_trn_caller_id](#get-trn-caller-id)
- [add_months_for_loan](#add-months-for-loan)
- [get_offer_id](#get-offer-id)
- [is_online_offer](#is-online-offer)
- [do_loan_control (overload 1)](#do-loan-control-1)
- [do_loan_control (overload 2)](#do-loan-control-2)

### Accounts, guarantees and closure

- [get_account_feature](#get-account-feature)
- [create_account](#create-account)
- [get_new_acc](#get-new-acc)
- [do_loan_collateral_out](#do-loan-collateral-out)
- [do_guarantee_out](#do-guarantee-out)
- [do_Loan_Close_With_Collateral_Out](#do-loan-close-with-collateral-out)
- [do_non_cash_loan_close](#do-non-cash-loan-close)
- [change_account_status](#change-account-status)

### Payments and balances

- [get_amount_by_range](#get-amount-by-range)
- [get_loan_amount](#get-loan-amount)
- [generate_allocated_payment_list](#generate-allocated-payment-list)
- [add_payment_details](#add-payment-details)
- [do_Auto_Payment](#do-auto-payment)

### Payment schedules and dates

- [post_int_amount_to_plan](#post-int-amount-to-plan)
- [get_overdue_grace_days](#get-overdue-grace-days)
- [get_formatted_grace_from_list](#get-formatted-grace-from-list)
- [get_grace_info](#get-grace-info)
- [get_commission_schedule](#get-commission-schedule)
- [get_next_Plan_Pym](#get-next-plan-pym)
- [get_plan_payment_amount](#get-plan-payment-amount)
- [get_Plan_Month_Count](#get-plan-month-count)
- [get_plan_paid_month_count](#get-plan-paid-month-count)
- [get_plan_error](#get-plan-error)
- [get_Annuity_Amount](#get-annuity-amount)
- [get_Pym_Startdate](#get-pym-startdate)
- [is_Payment_Date](#is-payment-date)
- [recalculate_int_payment_plan](#recalculate-int-payment-plan)
- [do_plan_control](#do-plan-control)
- [do_schedule_allignment](#do-schedule-allignment)
- [do_com_schedule_allignment](#do-com-schedule-allignment)
- [get_schedule_from_memo](#get-schedule-from-memo)
- [get_standart_schedule](#get-standart-schedule)
- [get_annuity_schedule](#get-annuity-schedule)
- [get_special_schedule](#get-special-schedule)
- [get_created_schedule](#get-created-schedule)
- [create_schedule](#create-schedule)
- [UPDATE_PAYMENT_PLAN](#update-payment-plan)

### Interest, penalties and rates

- [get_amount_for_pen_calc (overload 1)](#get-amount-for-pen-calc-1)
- [get_interest_calc_info](#get-interest-calc-info)
- [get_interest_calc_dates](#get-interest-calc-dates)
- [get_interest_calc_dates_ex](#get-interest-calc-dates-ex)
- [do_delete_operation](#do-delete-operation)
- [get_basis_year_days_cnt](#get-basis-year-days-cnt)
- [loan_int_diff_operation](#loan-int-diff-operation)
- [Get_Delay_Int_Rate](#get-delay-int-rate)
- [get_amount_for_pen_calc (overload 2)](#get-amount-for-pen-calc-2)
- [table_log_operation](#table-log-operation)
- [do_int_calculation](#do-int-calculation)
- [do_overdue_transit_operation](#do-overdue-transit-operation)
- [do_commission_recognition](#do-commission-recognition)
- [do_Loan_Delay_Int_Rate_Upd](#do-loan-delay-int-rate-upd)
- [get_flow_ratio_info](#get-flow-ratio-info)
- [get_stop_ratio_info](#get-stop-ratio-info)
- [get_incorrect_days](#get-incorrect-days)
- [get_incorrect_days_count](#get-incorrect-days-count)

### Delinquency and status

- [get_ovd_trs_oper_type](#get-ovd-trs-oper-type)
- [get_overdue_min_amount](#get-overdue-min-amount)
- [get_ovd_date](#get-ovd-date)
- [get_ovd_date_old](#get-ovd-date-old)
- [do_loan_status_control](#do-loan-status-control)
- [get_acc_type_by_status](#get-acc-type-by-status)

### Limits, tranches and overdrafts

- [evaluate_limit_amount](#evaluate-limit-amount)
- [do_create_tranche](#do-create-tranche)
- [create_overdrafts](#create-overdrafts)
- [get_new_ov_cont_no](#get-new-ov-cont-no)

### Accounting and audit

- [add_column_update (overload 1)](#add-column-update-1)
- [add_column_update (overload 2)](#add-column-update-2)
- [get_voucher_data_from_query](#get-voucher-data-from-query)
- [get_gl_value](#get-gl-value)
- [get_gl_acc_active_passive](#get-gl-acc-active-passive)
- [get_gl_acc_from_matrix](#get-gl-acc-from-matrix)
- [do_journal_entry](#do-journal-entry)
- [create_journal_entries](#create-journal-entries)
- [do_journal_control](#do-journal-control)

### History, metadata and reversal

- [clear_addtional_data](#clear-addtional-data)
- [add_additional_group](#add-additional-group)
- [end_additional_group](#end-additional-group)
- [add_additional_info (overload 1)](#add-additional-info-1)
- [add_additional_info (overload 2)](#add-additional-info-2)
- [get_additional_info](#get-additional-info)
- [finalize_addtional_process](#finalize-addtional-process)
- [reverse_update](#reverse-update)
- [create_loan_history](#create-loan-history)
- [update_loan_history](#update-loan-history)
- [init_global_variables](#init-global-variables)

---

## Loan operations and controls

<a id="get-trn-caller-id"></a>
### get_trn_caller_id

**Type:** FUNCTION  
**Source:** specification line 182; implementation begins at body line 2299.

**Purpose**

Implements **get_trn_caller_id** for the loan operations and controls domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `LOAN_OPERATION_DESC`
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `when no_data_found then`
   - `when others then`

**Business Rules**

Verified from source:
- Conditional expression: `when no_data_found then`
- Conditional expression: `when others then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
function get_trn_caller_id(p_oper_type in varchar2) return number;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_oper_type` | `varchar2` | IN | — | Input for `get_trn_caller_id` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `number`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `LOAN_OPERATION_DESC` |

**Error Handling**

- Source excerpt: `when no_data_found then r(p_text => 'Operation type ' || p_oper_type || ' not found in loan_operation_desc table!');`
- Source excerpt: `r(p_text => 'Operation type ' || p_oper_type || ' not found in loan_operation_desc table!'); when others then`
- Source excerpt: `when others then r(p_text => 'Error encountered in search of Operation type ' || p_oper_type || ' in loan_operation_desc table!');`
- Source excerpt: `r(p_text => 'Error encountered in search of Operation type ' || p_oper_type || ' in loan_operation_desc table!'); end;`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_trn_caller_id(...);
```

**Technical Notes**

- **Verified from Source:** 18 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="add-months-for-loan"></a>
### add_months_for_loan

**Type:** FUNCTION  
**Source:** specification line 236; implementation begins at body line 3054.

**Purpose**

Implements **add_months_for_loan** for the loan operations and controls domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** No direct SQL table access identified in the method segment.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if p_day is not null then`
   - `if extract(day from l_Date) = p_day or (l_date = l_last_Date and p_day > l_max_day) then`
   - `if abs(p_months) = l_find_count then`

**Business Rules**

Verified from source:
- Conditional expression: `if p_day is not null then`
- Conditional expression: `if extract(day from l_Date) = p_day or (l_date = l_last_Date and p_day > l_max_day) then`
- Conditional expression: `if abs(p_months) = l_find_count then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
function add_months_for_loan(p_date   date,
                               p_months number,
                               p_day    number default null) return date;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_date` | `date` | IN | — | Input for `add_months_for_loan` processing; semantics require caller/domain confirmation. |
| `p_months` | `number` | IN | — | Input for `add_months_for_loan` processing; semantics require caller/domain confirmation. |
| `p_day` | `number` | IN | `null` | Input for `add_months_for_loan` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `date`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| Direct SQL | None identified; called routines may perform data access. |

**Error Handling**

- No explicit error handler or raised application message identified within this method segment. Propagated exceptions from dependencies remain possible.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.add_months_for_loan(...);
```

**Technical Notes**

- **Verified from Source:** 33 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-offer-id"></a>
### get_offer_id

**Type:** FUNCTION  
**Source:** specification line 244; implementation begins at body line 3119.

**Purpose**

Implements **get_offer_id** for the loan operations and controls domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** inserts into `KRD_TEKLIF_NO`; updates `KRD_TEKLIF_NO`
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `If Sql%Rowcount < 1 Then`

**Business Rules**

Verified from source:
- Conditional expression: `If Sql%Rowcount < 1 Then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
Function get_offer_id(p_branch_id In Number Default Glbl.Getsube,
                        P_date      In Date Default Glbl.Getsysdate)
    Return Varchar2;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_branch_id` | `Number` | IN | `Glbl.Getsube` | Input for `get_offer_id` processing; semantics require caller/domain confirmation. |
| `P_date` | `Date` | IN | `Glbl.Getsysdate` | Input for `get_offer_id` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `Varchar2`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| INSERT | `KRD_TEKLIF_NO` |
| UPDATE | `KRD_TEKLIF_NO` |

**Error Handling**

- No explicit error handler or raised application message identified within this method segment. Propagated exceptions from dependencies remain possible.

**Side Effects & Transaction Notes**

- Direct DML detected: INSERT, UPDATE.
- Explicit `COMMIT` statements: **1**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_offer_id(...);
```

**Technical Notes**

- **Verified from Source:** 24 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="is-online-offer"></a>
### is_online_offer

**Type:** FUNCTION  
**Source:** specification line 312; implementation begins at body line 4423.

**Purpose**

Implements **is_online_offer** for the loan operations and controls domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `KRD_SCOR_MAIN`
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if p_memorandum_id like 'LO%' then`
   - `if t.erize_app is null then`

**Business Rules**

Verified from source:
- Conditional expression: `if p_memorandum_id like 'LO%' then`
- Conditional expression: `if t.erize_app is null then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
function is_online_offer(p_memorandum_id varchar2) return varchar2;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_memorandum_id` | `varchar2` | IN | — | Input for `is_online_offer` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `varchar2`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `KRD_SCOR_MAIN` |

**Error Handling**

- No explicit error handler or raised application message identified within this method segment. Propagated exceptions from dependencies remain possible.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.is_online_offer(...);
```

**Technical Notes**

- **Verified from Source:** 19 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="do-loan-control-1"></a>
### do_loan_control — overload 1

**Type:** PROCEDURE  
**Source:** specification line 362; implementation begins at body line 5261.

**Purpose**

Implements **do_loan_control** for the loan operations and controls domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `KRD_TEKLIF_DETAY`, `LOAN_EOD_CONTROL`
2. **Invoked external or qualified routines (static call references):** `GNI_UTILITY.RUN_TASK`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if l_count > 0 then`

**Business Rules**

Verified from source:
- Conditional expression: `if l_count > 0 then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
procedure do_loan_control(p_oper_type varchar2 default null,
                            p_date      date default glbl.getsysdate);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_oper_type` | `varchar2` | IN | `null` | Input for `do_loan_control` processing; semantics require caller/domain confirmation. |
| `p_date` | `date` | IN | `glbl.getsysdate` | Input for `do_loan_control` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `KRD_TEKLIF_DETAY`, `LOAN_EOD_CONTROL` |

Qualified procedure/function references: `GNI_UTILITY.RUN_TASK`.

**Error Handling**

- Source excerpt: `r('Errors detected after operation [' || p_oper_type || ']. Please review the table [LOAN_EOD_CONTROL] for details.'); end if;`
- Source excerpt: `r(p_text => 'Doc_no {' || m.sened_no || '} cs_account.account_closed_date column is not null, while krd_teklif_detay.kdate column is null!'); end loop;`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.do_loan_control(...);
```

**Technical Notes**

- **Verified from Source:** 43 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="do-loan-control-2"></a>
### do_loan_control — overload 2

**Type:** PROCEDURE  
**Source:** specification line 365; implementation begins at body line 5303.

**Purpose**

Implements **do_loan_control** for the loan operations and controls domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `KRD_TEKLIF_DETAY`, `LOAN_EOD_CONTROL_EXP`, `LOAN_OPERATION_HISTORY`; inserts into `LOAN_EOD_CONTROL`
2. **Invoked external or qualified routines (static call references):** `GLBL.SETUN`, `LOAN_API.GET_PLAN_ERROR`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if glbl_fwk.get_user_name is null then`
   - `if p_oper_type is null then`
   - `if l_err is not null then`
   - `if l_err is not null then`

**Business Rules**

Verified from source:
- Conditional expression: `if glbl_fwk.get_user_name is null then`
- Conditional expression: `if p_oper_type is null then`
- Conditional expression: `if l_err is not null then`
- Conditional expression: `if l_err is not null then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
procedure do_loan_control(p_oper_type varchar2 default null,
                            p_date      date default glbl.getsysdate,
                            p_min_rowid rowid,
                            p_max_rowid rowid);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_oper_type` | `varchar2` | IN | `null` | Input for `do_loan_control` processing; semantics require caller/domain confirmation. |
| `p_date` | `date` | IN | `glbl.getsysdate` | Input for `do_loan_control` processing; semantics require caller/domain confirmation. |
| `p_min_rowid` | `rowid` | IN | — | Input for `do_loan_control` processing; semantics require caller/domain confirmation. |
| `p_max_rowid` | `rowid` | IN | — | Input for `do_loan_control` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `KRD_TEKLIF_DETAY`, `LOAN_EOD_CONTROL_EXP`, `LOAN_OPERATION_HISTORY` |
| INSERT | `LOAN_EOD_CONTROL` |

Qualified procedure/function references: `GLBL.SETUN`, `LOAN_API.GET_PLAN_ERROR`.

**Error Handling**

- No explicit error handler or raised application message identified within this method segment. Propagated exceptions from dependencies remain possible.

**Side Effects & Transaction Notes**

- Direct DML detected: INSERT.
- Explicit `COMMIT` statements: **2**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.do_loan_control(...);
```

**Technical Notes**

- **Verified from Source:** 59 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

## Accounts, guarantees and closure

<a id="get-account-feature"></a>
### get_account_feature

**Type:** FUNCTION  
**Source:** specification line 304; implementation begins at body line 4391.

**Purpose**

Implements **get_account_feature** for the accounts, guarantees and closure domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `CS_ACCOUNT`
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `when others then`

**Business Rules**

Verified from source:
- Conditional expression: `when others then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
function get_account_feature(p_branch_no   number,
                               p_account_no  number,
                               p_account_sub number)
    return cs_account.account_feature%type;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_branch_no` | `number` | IN | — | Input for `get_account_feature` processing; semantics require caller/domain confirmation. |
| `p_account_no` | `number` | IN | — | Input for `get_account_feature` processing; semantics require caller/domain confirmation. |
| `p_account_sub` | `number` | IN | — | Input for `get_account_feature` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `cs_account.account_feature%type`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `CS_ACCOUNT` |

**Error Handling**

- Source excerpt: `when others then return null; end;`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_account_feature(...);
```

**Technical Notes**

- **Verified from Source:** 20 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="create-account"></a>
### create_account

**Type:** PROCEDURE  
**Source:** specification line 329; implementation begins at body line 4737.

**Purpose**

Implements **create_account** for the accounts, guarantees and closure domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `IN_LIST`, `KRD_TEKLIF_DETAY`, `KRD_TESIS`, `LOAN_ACCOUNTS`, `LOAN_ACC_TYPES_PR`, `LOAN_API.GET_GL_ACC_FROM_MATRIX`, `SP_FAIZ_GUN_TANIM_PR`; updates `KRD_TEKLIF_DETAY`, `KRD_TESIS`
2. **Invoked external or qualified routines (static call references):** `GLBL_NAME.GET_CUSTOMER_NOVU_CODE`, `GLBL_TARIH.DAYSBETWEEN`, `GNI_MESSAGE.GET_MESSAGE`, `LOAN_API.GET_GL_ACC_FROM_MATRIX`, `LOAN_API.GET_NEW_ACC`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `when others then`
   - `when others then`
   - `When Others Then`
   - `when p.acc_type_group in`
   - `when others then`
   - `if l_is_creation_enabled_yn = 'Y' Then`
   - `when m.currency_source = 'LOCAL' then`
   - `if l_bal_acc is null then`
   - `when m.acc_type_group in ('MAIN', 'OVD_MAIN') and`
   - `when m.acc_type_group in ('MAIN', 'OVD_MAIN') and`

**Business Rules**

Verified from source:
- Conditional expression: `when others then`
- Conditional expression: `when others then`
- Conditional expression: `When Others Then`
- Conditional expression: `when p.acc_type_group in`
- Conditional expression: `when others then`
- Conditional expression: `if l_is_creation_enabled_yn = 'Y' Then`
- Conditional expression: `when m.currency_source = 'LOCAL' then`
- Conditional expression: `if l_bal_acc is null then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
procedure create_account(p_doc_no      in varchar2,
                           p_oper_type   in varchar2,
                           p_acc_type    in varchar2 default null,
                           p_tx_fid      in number,
                           p_created_acc out g_loan_accounts_tab);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_doc_no` | `varchar2` | IN | — | Input for `create_account` processing; semantics require caller/domain confirmation. |
| `p_oper_type` | `varchar2` | IN | — | Input for `create_account` processing; semantics require caller/domain confirmation. |
| `p_acc_type` | `varchar2` | IN | `null` | Input for `create_account` processing; semantics require caller/domain confirmation. |
| `p_tx_fid` | `number` | IN | — | Input for `create_account` processing; semantics require caller/domain confirmation. |
| `p_created_acc` | `g_loan_accounts_tab` | OUT | — | Output produced by the method. |

**Return Value / Outputs**

OUT/IN OUT parameters: `p_created_acc`.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `IN_LIST`, `KRD_TEKLIF_DETAY`, `KRD_TESIS`, `LOAN_ACCOUNTS`, `LOAN_ACC_TYPES_PR`, `LOAN_API.GET_GL_ACC_FROM_MATRIX`, `SP_FAIZ_GUN_TANIM_PR` |
| UPDATE | `KRD_TEKLIF_DETAY`, `KRD_TESIS` |

Qualified procedure/function references: `GLBL_NAME.GET_CUSTOMER_NOVU_CODE`, `GLBL_TARIH.DAYSBETWEEN`, `GNI_MESSAGE.GET_MESSAGE`, `LOAN_API.GET_GL_ACC_FROM_MATRIX`, `LOAN_API.GET_NEW_ACC`.

**Error Handling**

- Source excerpt: `when others then r('Error encountered in loan table krd_teklif_detay!'); end;`
- Source excerpt: `r('Error encountered in loan table krd_teklif_detay!'); end; `
- Source excerpt: `When Others Then r('[' || Nvl(l_days_count, 0) || '] ' || gni_message.get_message(l_mess_name => 'GNI_2201_1_NOFTERMT'));`
- Source excerpt: `r('[' || Nvl(l_days_count, 0) || '] ' || gni_message.get_message(l_mess_name => 'GNI_2201_1_NOFTERMT')); End;`
- Source excerpt: `when others then r('Error ocured at Create condition - ' || sqlerrm); end;`
- Source excerpt: `r('Error ocured at Create condition - ' || sqlerrm); end; if l_is_creation_enabled_yn = 'Y' Then`
- Source excerpt: `r(p_text => 'Balance account for ' || m.acc_type || ' not return from loan_api.get_gl_acc_from_matrix function!'); end if;`
- Source excerpt: `when others then -- burada exception da qoydum ele bele r('ACC_TYPE: ' || m.acc_type || ' - PRODUCT: ' ||`
- Source excerpt: `r('ACC_TYPE: ' || m.acc_type || ' - PRODUCT: ' || l_info.urun_kod || ' - CUST_TPYE: ' || l_cust_type || ' - PERIOD_ID: ' || l_period_id || ' - CCY_ID: ' || L_curr_id ||`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- Direct DML detected: UPDATE.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.create_account(...);
```

**Technical Notes**

- **Verified from Source:** 214 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-new-acc"></a>
### get_new_acc

**Type:** FUNCTION  
**Source:** specification line 343; implementation begins at body line 3854.

**Purpose**

Implements **get_new_acc** for the accounts, guarantees and closure domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `CS_ACCOUNT`, `LOAN_ACC_TYPES_PR`
2. **Invoked external or qualified routines (static call references):** `GLBL_HESAP.YENI_M2_HESAPNO`, `GNI_MESSAGE.GET_MESSAGE`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `when others then`
   - `when others then`

**Business Rules**

Verified from source:
- Conditional expression: `when others then`
- Conditional expression: `when others then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

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

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_branch_no` | `number` | IN | — | Input for `get_new_acc` processing; semantics require caller/domain confirmation. |
| `p_customer_no` | `number` | IN | — | Input for `get_new_acc` processing; semantics require caller/domain confirmation. |
| `p_balance_acc` | `varchar2` | IN | — | Input for `get_new_acc` processing; semantics require caller/domain confirmation. |
| `p_detail_code` | `varchar2` | IN | — | Input for `get_new_acc` processing; semantics require caller/domain confirmation. |
| `p_ccy_id` | `number` | IN | — | Input for `get_new_acc` processing; semantics require caller/domain confirmation. |
| `p_main_acc` | `number` | IN | `null` | Input for `get_new_acc` processing; semantics require caller/domain confirmation. |
| `p_cr_int_rate` | `number` | IN | `null` | Input for `get_new_acc` processing; semantics require caller/domain confirmation. |
| `p_dr_int_rate` | `number` | IN | `null` | Input for `get_new_acc` processing; semantics require caller/domain confirmation. |
| `p_com_int_rate` | `number` | IN | `null` | Input for `get_new_acc` processing; semantics require caller/domain confirmation. |
| `p_product_code` | `number` | IN | `null` | Input for `get_new_acc` processing; semantics require caller/domain confirmation. |
| `p_period_id` | `number` | IN | `null` | Input for `get_new_acc` processing; semantics require caller/domain confirmation. |
| `p_acc_description` | `varchar2` | IN | — | Input for `get_new_acc` processing; semantics require caller/domain confirmation. |
| `p_loan_doc_no` | `varchar2` | IN | — | Input for `get_new_acc` processing; semantics require caller/domain confirmation. |
| `p_loan_acc_type` | `varchar2` | IN | — | Input for `get_new_acc` processing; semantics require caller/domain confirmation. |
| `p_tx_fid` | `number` | IN | — | Input for `get_new_acc` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `number`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `CS_ACCOUNT`, `LOAN_ACC_TYPES_PR` |

Qualified procedure/function references: `GLBL_HESAP.YENI_M2_HESAPNO`, `GNI_MESSAGE.GET_MESSAGE`.

**Error Handling**

- Source excerpt: `when others then r(gni_message.get_message('GNI_SYSTEM_DUZGUN_DEYIL', p_loan_acc_type,`
- Source excerpt: `r(gni_message.get_message('GNI_SYSTEM_DUZGUN_DEYIL', p_loan_acc_type, p_balance_acc));`
- Source excerpt: `r(p_text => gni_message.get_message('GNI_SYSTEM_OPEN_NEW_ACC', p_loan_doc_no, l_loan_acc_type));`
- Source excerpt: `when others then r(gni_message.get_message('GNI_SYSTEM_OPEN_NEW_ACC_BALANCE', p_acc_description,`
- Source excerpt: `r(gni_message.get_message('GNI_SYSTEM_OPEN_NEW_ACC_BALANCE', p_acc_description, p_balance_acc,`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_new_acc(...);
```

**Technical Notes**

- **Verified from Source:** 70 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="do-loan-collateral-out"></a>
### do_loan_collateral_out

**Type:** PROCEDURE  
**Source:** specification line 385; implementation begins at body line 6086.

**Purpose**

Implements **do_loan_collateral_out** for the accounts, guarantees and closure domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `CS_ACCOUNT`, `KRD_SCOR_AUTO_C`, `KRD_SCOR_EMANET_C`, `KRD_SCOR_ESYA_C`, `KRD_SCOR_QARANT_C`, `KRD_SCOR_REAL_ESTATE_C`, `KRD_SCOR_SEHMLER_C`, `KRD_SCOR_TEMINAT_ALAKA_C` and 3 more; updates `KRD_SCOR_AUTO_C`, `KRD_SCOR_EMANET_C`, `KRD_SCOR_ESYA_C`, `KRD_SCOR_QARANT_C`, `KRD_SCOR_REAL_ESTATE_C`, `KRD_SCOR_SEHMLER_C`, `KRD_SCOR_TEMINAT_ALAKA_C`, `KRD_SCOR_ZAMIN_C` and 1 more
2. **Invoked external or qualified routines (static call references):** `BLOKE_API.BLOKE_KOY_KALDIR`, `GLBL_CCY.GET_CUR_RATE`, `GLBL_CCY.TO_CCY_MB`, `GLBL_EOD.GETCALLERID`, `MM_ACCOUNTING#.POST_JOURNAL`, `PA_API#.CREATE_J_WSQL`, `PH_API.GET_PARAMETER`, `TRN_BROKER.REGISTER_EOD`, `TRN_BROKER.SETTXDETAILS`, `TRN_BROKER.SETTXSTATE`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `If l_Count = 0 Then`
   - `if m.tem_tip not in ('YY') then`
   - `If l_Error_No = 0 Then`
   - `when others then`

**Business Rules**

Verified from source:
- Conditional expression: `If l_Count = 0 Then`
- Conditional expression: `if m.tem_tip not in ('YY') then`
- Conditional expression: `If l_Error_No = 0 Then`
- Conditional expression: `when others then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
procedure do_loan_collateral_out(p_doc_no in varchar2);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_doc_no` | `varchar2` | IN | — | Input for `do_loan_collateral_out` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `CS_ACCOUNT`, `KRD_SCOR_AUTO_C`, `KRD_SCOR_EMANET_C`, `KRD_SCOR_ESYA_C`, `KRD_SCOR_QARANT_C`, `KRD_SCOR_REAL_ESTATE_C`, `KRD_SCOR_SEHMLER_C`, `KRD_SCOR_TEMINAT_ALAKA_C`, `KRD_SCOR_ZAMIN_C`, `KRD_SKOR_GIROV_OTHER_C`, `KRD_TEMINAT_TIP_PR` |
| UPDATE | `KRD_SCOR_AUTO_C`, `KRD_SCOR_EMANET_C`, `KRD_SCOR_ESYA_C`, `KRD_SCOR_QARANT_C`, `KRD_SCOR_REAL_ESTATE_C`, `KRD_SCOR_SEHMLER_C`, `KRD_SCOR_TEMINAT_ALAKA_C`, `KRD_SCOR_ZAMIN_C`, `KRD_SKOR_GIROV_OTHER_C` |

Qualified procedure/function references: `BLOKE_API.BLOKE_KOY_KALDIR`, `GLBL_CCY.GET_CUR_RATE`, `GLBL_CCY.TO_CCY_MB`, `GLBL_EOD.GETCALLERID`, `MM_ACCOUNTING#.POST_JOURNAL`, `PA_API#.CREATE_J_WSQL`, `PH_API.GET_PARAMETER`, `TRN_BROKER.REGISTER_EOD`, `TRN_BROKER.SETTXDETAILS`, `TRN_BROKER.SETTXSTATE`.

**Error Handling**

- Source excerpt: `when others then r(p_text => sqlERRM || chr(010) || ' Teminat cixishi sehv! Sened_no: ' || p_doc_no ||`
- Source excerpt: `r(p_text => sqlERRM || chr(010) || ' Teminat cixishi sehv! Sened_no: ' || p_doc_no || ' Teminat id: ' || m.tem_fid || ' Teminat Tip: ' ||`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- Direct DML detected: UPDATE.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.do_loan_collateral_out(...);
```

**Technical Notes**

- **Verified from Source:** 270 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="do-guarantee-out"></a>
### do_guarantee_out

**Type:** PROCEDURE  
**Source:** specification line 445; implementation begins at body line 7962.

**Purpose**

Implements **do_guarantee_out** for the accounts, guarantees and closure domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `KRD_TESIS`
2. **Invoked external or qualified routines (static call references):** `APEX_KRD2220_0_API_P.INS_KRD2220_0`, `GLBL_BAKIYE.REAL_BALANCE`, `KRD2220_0_API.JUSTDOIT`, `TRN_BROKER.STARTTX`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `If (l_Kr_Qal != 0 Or (l_Kr_Qal = 0 And l_Fz_Qal = 0)) Then`
   - `When Others Then`

**Business Rules**

Verified from source:
- Conditional expression: `If (l_Kr_Qal != 0 Or (l_Kr_Qal = 0 And l_Fz_Qal = 0)) Then`
- Conditional expression: `When Others Then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
Procedure do_guarantee_out(p_branch_id   In Number Default Null,
                             p_customer_no In Number Default Null,
                             p_loan_acc    In Number Default Null);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_branch_id` | `Number` | IN | `Null` | Input for `do_guarantee_out` processing; semantics require caller/domain confirmation. |
| `p_customer_no` | `Number` | IN | `Null` | Input for `do_guarantee_out` processing; semantics require caller/domain confirmation. |
| `p_loan_acc` | `Number` | IN | `Null` | Input for `do_guarantee_out` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `KRD_TESIS` |

Qualified procedure/function references: `APEX_KRD2220_0_API_P.INS_KRD2220_0`, `GLBL_BAKIYE.REAL_BALANCE`, `KRD2220_0_API.JUSTDOIT`, `TRN_BROKER.STARTTX`.

**Error Handling**

- Source excerpt: `When Others Then r(p_text => 'Loan acc: ' || m.Sube_Kod || '-' || m.Musteri_No || '-' || m.Kredi_Hesap_No || Chr(10) || Sqlerrm);`
- Source excerpt: `r(p_text => 'Loan acc: ' || m.Sube_Kod || '-' || m.Musteri_No || '-' || m.Kredi_Hesap_No || Chr(10) || Sqlerrm); End;`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.do_guarantee_out(...);
```

**Technical Notes**

- **Verified from Source:** 101 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="do-loan-close-with-collateral-out"></a>
### do_Loan_Close_With_Collateral_Out

**Type:** PROCEDURE  
**Source:** specification line 449; implementation begins at body line 8206.

**Purpose**

Implements **do_Loan_Close_With_Collateral_Out** for the accounts, guarantees and closure domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `LOAN_EOD_AUTO_CLOSE`, `LOAN_PORTFOLIO_LITE`, `LOAN_TRANCHE_LIMIT_CHANGES_HISTORY`; inserts into `LOAN_EOD_AUTO_CLOSE`; updates `KRD_FON_VERILME`, `KRD_TEKLIF_DETAY`
2. **Invoked external or qualified routines (static call references):** `GLBL_EOD.GETCALLERID`, `GLBL_HESAP.GET_ACCOUNT_PR`, `LOAN_API.CHANGE_ACCOUNT_STATUS`, `LOAN_API.CREATE_LOAN_HISTORY`, `LOAN_API.DO_JOURNAL_ENTRY`, `LOAN_API.G_ENTRIES_LIST_TAB`, `TRN_BROKER.REGISTER_EOD`, `TRN_BROKER.SETTXSTATE`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `If i.loan_type in ('KX') and abs(i.lim_amount) > 0 Then`
   - `if l_accounts.count > 0 then`
   - `when others then`
   - `if i.loan_amount = 0 then`
   - `if i.acc_closed_date is null then`
   - `When Others Then`

**Business Rules**

Verified from source:
- Conditional expression: `If i.loan_type in ('KX') and abs(i.lim_amount) > 0 Then`
- Conditional expression: `if l_accounts.count > 0 then`
- Conditional expression: `when others then`
- Conditional expression: `if i.loan_amount = 0 then`
- Conditional expression: `if i.acc_closed_date is null then`
- Conditional expression: `When Others Then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
procedure do_Loan_Close_With_Collateral_Out(p_doc_no in varchar2);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_doc_no` | `varchar2` | IN | — | Input for `do_Loan_Close_With_Collateral_Out` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `LOAN_EOD_AUTO_CLOSE`, `LOAN_PORTFOLIO_LITE`, `LOAN_TRANCHE_LIMIT_CHANGES_HISTORY` |
| INSERT | `LOAN_EOD_AUTO_CLOSE` |
| UPDATE | `KRD_FON_VERILME`, `KRD_TEKLIF_DETAY` |

Qualified procedure/function references: `GLBL_EOD.GETCALLERID`, `GLBL_HESAP.GET_ACCOUNT_PR`, `LOAN_API.CHANGE_ACCOUNT_STATUS`, `LOAN_API.CREATE_LOAN_HISTORY`, `LOAN_API.DO_JOURNAL_ENTRY`, `LOAN_API.G_ENTRIES_LIST_TAB`, `TRN_BROKER.REGISTER_EOD`, `TRN_BROKER.SETTXSTATE`.

**Error Handling**

- Source excerpt: `when others then r(p_text => 'Lim: ' || sqlerrm); end;`
- Source excerpt: `r(p_text => 'Lim: ' || sqlerrm); end; end if;`
- Source excerpt: `When Others Then r(p_text => 'Error: ' || i.Branch_No || '-' || i.Customer_No || '-' || i.main_Acc || Chr(10) || Sqlerrm);`
- Source excerpt: `r(p_text => 'Error: ' || i.Branch_No || '-' || i.Customer_No || '-' || i.main_Acc || Chr(10) || Sqlerrm); End;`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- Direct DML detected: INSERT, UPDATE.
- Explicit `COMMIT` statements: **1**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.do_Loan_Close_With_Collateral_Out(...);
```

**Technical Notes**

- **Verified from Source:** 167 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="do-non-cash-loan-close"></a>
### do_non_cash_loan_close

**Type:** PROCEDURE  
**Source:** specification line 451; implementation begins at body line 8372.

**Purpose**

Implements **do_non_cash_loan_close** for the accounts, guarantees and closure domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `CS_ACCOUNT`, `KRD_TESIS`
2. **Invoked external or qualified routines (static call references):** `APEX_KRD2220_0_API_P.INS_KRD2220_0`, `GLBL_BAKIYE.REAL_BALANCE`, `KRD2220_0_API.JUSTDOIT`, `TRN_BROKER.STARTTX`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if m.blok_hesap_no is not null then`
   - `When Others Then`

**Business Rules**

Verified from source:
- Conditional expression: `if m.blok_hesap_no is not null then`
- Conditional expression: `When Others Then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
Procedure do_non_cash_loan_close(p_doc_no in varchar2,
                                   p_Date   In Date Default Glbl.Getsysdate);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_doc_no` | `varchar2` | IN | — | Input for `do_non_cash_loan_close` processing; semantics require caller/domain confirmation. |
| `p_Date` | `Date` | IN | `Glbl.Getsysdate` | Input for `do_non_cash_loan_close` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `CS_ACCOUNT`, `KRD_TESIS` |

Qualified procedure/function references: `APEX_KRD2220_0_API_P.INS_KRD2220_0`, `GLBL_BAKIYE.REAL_BALANCE`, `KRD2220_0_API.JUSTDOIT`, `TRN_BROKER.STARTTX`.

**Error Handling**

- Source excerpt: `When Others Then r('Kreditde sehv: ' || m.Sube_Kod || '-' || m.Musteri_No || '-' || m.Kredi_Hesap_No || Chr(10) || Sqlerrm);`
- Source excerpt: `r('Kreditde sehv: ' || m.Sube_Kod || '-' || m.Musteri_No || '-' || m.Kredi_Hesap_No || Chr(10) || Sqlerrm); End;`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.do_non_cash_loan_close(...);
```

**Technical Notes**

- **Verified from Source:** 116 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="change-account-status"></a>
### change_account_status

**Type:** PROCEDURE  
**Source:** specification line 480; implementation begins at body line 9051.

**Purpose**

Implements **change_account_status** for the accounts, guarantees and closure domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `CS_ACCOUNT`, `KRD_TEKLIF_DETAY`
2. **Invoked external or qualified routines (static call references):** `GLBL_HESAP.HESAPNO_AC`, `GLBL_HESAP.HESAPNO_KAPA`, `LOAN_CATEGORY_API.CHANGE_OV_STATUS`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `when no_data_found then`
   - `when others then`
   - `if l_status = 'O' then`
   - `elsif l_status = 'C' then`
   - `if l_info.kredit_khat = 'OV' then`
   - `when NO_DATA_FOUND then`
   - `when TOO_MANY_ROWS then`
   - `when OTHERS then`
   - `if l_status in ('OVER', 'OVER60') and m.main_amount != 0 then`
   - `if l_status = 'OVER60' and m.int_amount != 0 then`

**Business Rules**

Verified from source:
- Conditional expression: `when no_data_found then`
- Conditional expression: `when others then`
- Conditional expression: `if l_status = 'O' then`
- Conditional expression: `elsif l_status = 'C' then`
- Conditional expression: `if l_info.kredit_khat = 'OV' then`
- Conditional expression: `when NO_DATA_FOUND then`
- Conditional expression: `when TOO_MANY_ROWS then`
- Conditional expression: `when OTHERS then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
procedure change_account_status(p_doc_no in varchar2,
                                  p_status in varchar2);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_doc_no` | `varchar2` | IN | — | Input for `change_account_status` processing; semantics require caller/domain confirmation. |
| `p_status` | `varchar2` | IN | — | Input for `change_account_status` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `CS_ACCOUNT`, `KRD_TEKLIF_DETAY` |

Qualified procedure/function references: `GLBL_HESAP.HESAPNO_AC`, `GLBL_HESAP.HESAPNO_KAPA`, `LOAN_CATEGORY_API.CHANGE_OV_STATUS`.

**Error Handling**

- Source excerpt: `when no_data_found then r(p_text => 'Loan with doc_no: ' || p_doc_no || ' not found!'); when others then`
- Source excerpt: `r(p_text => 'Loan with doc_no: ' || p_doc_no || ' not found!'); when others then r(p_text => 'Error encountered in search of loan: ' || p_doc_no);`
- Source excerpt: `when others then r(p_text => 'Error encountered in search of loan: ' || p_doc_no); end;`
- Source excerpt: `r(p_text => 'Error encountered in search of loan: ' || p_doc_no); end; `
- Source excerpt: `r(p_text => 'Only followings p_status are accepted O-open, C-close!'); end if; end loop;`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.change_account_status(...);
```

**Technical Notes**

- **Verified from Source:** 533 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

## Payments and balances

<a id="get-amount-by-range"></a>
### get_amount_by_range

**Type:** FUNCTION  
**Source:** specification line 110; implementation begins at body line 1351.

**Purpose**

Implements **get_amount_by_range** for the payments and balances domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `LOAN_AMOUNT_RANGE_INFO`
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `when no_data_found then`
   - `when too_many_rows then`
   - `when others then`

**Business Rules**

Verified from source:
- Conditional expression: `when no_data_found then`
- Conditional expression: `when too_many_rows then`
- Conditional expression: `when others then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
function get_amount_by_range(p_oper_type    in varchar2,
                               p_acc_type     in varchar2,
                               p_tranche_type in varchar2 default null,
                               p_amount       in number) return number;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_oper_type` | `varchar2` | IN | — | Input for `get_amount_by_range` processing; semantics require caller/domain confirmation. |
| `p_acc_type` | `varchar2` | IN | — | Input for `get_amount_by_range` processing; semantics require caller/domain confirmation. |
| `p_tranche_type` | `varchar2` | IN | `null` | Input for `get_amount_by_range` processing; semantics require caller/domain confirmation. |
| `p_amount` | `number` | IN | — | Input for `get_amount_by_range` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `number`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `LOAN_AMOUNT_RANGE_INFO` |

**Error Handling**

- Source excerpt: `when no_data_found then r(p_text => 'No data found in loan_amount_range_info table!'); when too_many_rows then`
- Source excerpt: `r(p_text => 'No data found in loan_amount_range_info table!'); when too_many_rows then r(p_text => 'Too many rows found in loan_amount_range_info table!');`
- Source excerpt: `when too_many_rows then r(p_text => 'Too many rows found in loan_amount_range_info table!'); when others then`
- Source excerpt: `r(p_text => 'Too many rows found in loan_amount_range_info table!'); when others then r(p_text => 'Error encountered in loan_amount_range_info table!');`
- Source excerpt: `when others then r(p_text => 'Error encountered in loan_amount_range_info table!'); end;`
- Source excerpt: `r(p_text => 'Error encountered in loan_amount_range_info table!'); end; `
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_amount_by_range(...);
```

**Technical Notes**

- **Verified from Source:** 24 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-loan-amount"></a>
### get_loan_amount

**Type:** FUNCTION  
**Source:** specification line 170; implementation begins at body line 2177.

**Purpose**

Implements **get_loan_amount** for the payments and balances domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `CS_ACCOUNT`, `IN_LIST`
2. **Invoked external or qualified routines (static call references):** `LOAN_API.GET_PLAN_PAYMENT_AMOUNT`, `O.PARAM_ID`, `O.TYPE_ID`, `P.ACC_TYPE`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if l_amount_type not in ('TOTAL', 'DEBT', 'DUE') then`
   - `when p.acc_type is null or`
   - `when l_amount_type in ('TOTAL', 'DEBT') then`
   - `when l_amount_type in ('DUE') then`
   - `when o.allocation_type = 'BY_BALANCE' then`
   - `when o.allocation_type = 'BY_SCHEDULE' then`
   - `if m.acc_type is null then`

**Business Rules**

Verified from source:
- Conditional expression: `if l_amount_type not in ('TOTAL', 'DEBT', 'DUE') then`
- Conditional expression: `when p.acc_type is null or`
- Conditional expression: `when l_amount_type in ('TOTAL', 'DEBT') then`
- Conditional expression: `when l_amount_type in ('DUE') then`
- Conditional expression: `when o.allocation_type = 'BY_BALANCE' then`
- Conditional expression: `when o.allocation_type = 'BY_SCHEDULE' then`
- Conditional expression: `if m.acc_type is null then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
function get_loan_amount(p_doc_no      in varchar2,
                           p_amount_type in varchar2,
                           p_date        in date default glbl.getsysdate,
                           p_oper_type   in varchar2 default null)
    return number;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_doc_no` | `varchar2` | IN | — | Input for `get_loan_amount` processing; semantics require caller/domain confirmation. |
| `p_amount_type` | `varchar2` | IN | — | Input for `get_loan_amount` processing; semantics require caller/domain confirmation. |
| `p_date` | `date` | IN | `glbl.getsysdate` | Input for `get_loan_amount` processing; semantics require caller/domain confirmation. |
| `p_oper_type` | `varchar2` | IN | `null` | Input for `get_loan_amount` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `number`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `CS_ACCOUNT`, `IN_LIST` |

Qualified procedure/function references: `LOAN_API.GET_PLAN_PAYMENT_AMOUNT`, `O.PARAM_ID`, `O.TYPE_ID`, `P.ACC_TYPE`.

**Error Handling**

- Source excerpt: `r(p_text => 'p_amount_type should be TOTAL - All balances (Main, Int, Lim, etc.) , DEBT - The debt the customer can pay (Main, Int, etc.) DUE - Today payment amount (according to the schedule)');`
- Source excerpt: `r(p_text => '[' || p_doc_no || '] acc_type[' || nvl(m.acc_type, m.cs_acc_type) || '] in loan_acc_types_pr or param_id in Krd_Pym_Order is null!');`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_loan_amount(...);
```

**Technical Notes**

- **Verified from Source:** 77 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="generate-allocated-payment-list"></a>
### generate_allocated_payment_list

**Type:** PROCEDURE  
**Source:** specification line 392; implementation begins at body line 6388.

**Purpose**

Implements **generate_allocated_payment_list** for the payments and balances domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `CS_ACCOUNT`, `IN_LIST`
2. **Invoked external or qualified routines (static call references):** `LOAN_API.GET_PLAN_PAYMENT_AMOUNT`, `LOAN_API.G_LOAN_ACCOUNTS_REC_TYPE`, `LOAN_API.G_LOAN_ACCOUNTS_TAB`, `O.PARAM_ID`, `O.TYPE_ID`, `P.ACC_TYPE`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if l_pym_amount >= 0 then`
   - `when nvl(p.is_payable, 'Y') = 'Y' and`
   - `if m.acc_type is null then`
   - `if m.pymt_branch_no is null or m.pymt_customer_no is null or`
   - `if l_loan_accounts(j).allocation_type = 'BY_SCHEDULE' and i = 1 then`
   - `if l_balance > 0 then`
   - `if l_pym_amount <= l_balance then`
   - `if nvl(l_assigned_pym, 0) > 0 then`
   - `if l_loan_accounts(j).pymt_amount > l_loan_accounts(j).balance then`
   - `if l_loan_accounts(j).acc_type in ('MAIN', 'NPL_MAIN') then`

**Business Rules**

Verified from source:
- Conditional expression: `if l_pym_amount >= 0 then`
- Conditional expression: `when nvl(p.is_payable, 'Y') = 'Y' and`
- Conditional expression: `if m.acc_type is null then`
- Conditional expression: `if m.pymt_branch_no is null or m.pymt_customer_no is null or`
- Conditional expression: `if l_loan_accounts(j).allocation_type = 'BY_SCHEDULE' and i = 1 then`
- Conditional expression: `if l_balance > 0 then`
- Conditional expression: `if l_pym_amount <= l_balance then`
- Conditional expression: `if nvl(l_assigned_pym, 0) > 0 then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
procedure generate_allocated_payment_list(p_doc_no                in varchar2,
                                            p_oper_type             in varchar2,
                                            p_pym_amount            in number,
                                            p_has_schedule_upd_type out varchar2,
                                            p_payment_list          out loan_api.g_loan_accounts_tab);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_doc_no` | `varchar2` | IN | — | Input for `generate_allocated_payment_list` processing; semantics require caller/domain confirmation. |
| `p_oper_type` | `varchar2` | IN | — | Input for `generate_allocated_payment_list` processing; semantics require caller/domain confirmation. |
| `p_pym_amount` | `number` | IN | — | Input for `generate_allocated_payment_list` processing; semantics require caller/domain confirmation. |
| `p_has_schedule_upd_type` | `varchar2` | OUT | — | Output produced by the method. |
| `p_payment_list` | `loan_api.g_loan_accounts_tab` | OUT | — | Output produced by the method. |

**Return Value / Outputs**

OUT/IN OUT parameters: `p_has_schedule_upd_type`, `p_payment_list`.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `CS_ACCOUNT`, `IN_LIST` |

Qualified procedure/function references: `LOAN_API.GET_PLAN_PAYMENT_AMOUNT`, `LOAN_API.G_LOAN_ACCOUNTS_REC_TYPE`, `LOAN_API.G_LOAN_ACCOUNTS_TAB`, `O.PARAM_ID`, `O.TYPE_ID`, `P.ACC_TYPE`.

**Error Handling**

- Source excerpt: `r(p_text => '[' || p_doc_no || '] acc_type[' || m.cs_acc_type || '] in loan_acc_types_pr or param_id in Krd_Pym_Order is null!'); end if;`
- Source excerpt: `r(p_text => 'Payment branch or customer or account is null Pymt_branch_no: ' || m.pymt_branch_no || ', Pymt_customer_no: ' || m.pymt_customer_no || ', Pymt_account_no: ' ||`
- Source excerpt: `r(p_text => 'Payment amount cant be more than balance amount! Please check amount of acc_type: ' || l_loan_accounts(j).acc_type || ' in payment plan and balance of account ' || l_loan_accounts(j).branch_no || '-' || l_loan_accounts(j).`
- Source excerpt: `r(p_text => 'Payment amount cant be negative!'); end if; p_has_schedule_upd_type := l_has_schedule_upd_type;`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.generate_allocated_payment_list(...);
```

**Technical Notes**

- **Verified from Source:** 151 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="add-payment-details"></a>
### add_payment_details

**Type:** PROCEDURE  
**Source:** specification line 398; implementation begins at body line 6538.

**Purpose**

Implements **add_payment_details** for the payments and balances domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `CS_ACCOUNT`
2. **Invoked external or qualified routines (static call references):** `LOAN_API.GET_PLAN_PAYMENT_AMOUNT`, `LOAN_API.G_LOAN_ACCOUNTS_TAB`, `O.PARAM_ID`, `O.TYPE_ID`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if p_payment_list.count > 0 then`
   - `when others then`
   - `if l_loan_accounts_rec.allocation_type is null then`
   - `if l_loan_accounts_rec.pymt_amount <= 0 then`
   - `if l_loan_accounts_rec.pymt_amount > l_loan_accounts_rec.balance then`
   - `if l_loan_accounts_rec.pymt_branch_no is null or`
   - `if l_loan_accounts_rec.acc_type in ('MAIN', 'NPL_MAIN') and`

**Business Rules**

Verified from source:
- Conditional expression: `if p_payment_list.count > 0 then`
- Conditional expression: `when others then`
- Conditional expression: `if l_loan_accounts_rec.allocation_type is null then`
- Conditional expression: `if l_loan_accounts_rec.pymt_amount <= 0 then`
- Conditional expression: `if l_loan_accounts_rec.pymt_amount > l_loan_accounts_rec.balance then`
- Conditional expression: `if l_loan_accounts_rec.pymt_branch_no is null or`
- Conditional expression: `if l_loan_accounts_rec.acc_type in ('MAIN', 'NPL_MAIN') and`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
procedure add_payment_details(p_doc_no                in varchar2,
                                p_has_schedule_upd_type out varchar2,
                                p_payment_list          in out loan_api.g_loan_accounts_tab);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_doc_no` | `varchar2` | IN | — | Input for `add_payment_details` processing; semantics require caller/domain confirmation. |
| `p_has_schedule_upd_type` | `varchar2` | OUT | — | Output produced by the method. |
| `p_payment_list` | `loan_api.g_loan_accounts_tab` | IN OUT | — | Input/output parameter; method may modify the supplied value. |

**Return Value / Outputs**

OUT/IN OUT parameters: `p_has_schedule_upd_type`, `p_payment_list`.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `CS_ACCOUNT` |

Qualified procedure/function references: `LOAN_API.GET_PLAN_PAYMENT_AMOUNT`, `LOAN_API.G_LOAN_ACCOUNTS_TAB`, `O.PARAM_ID`, `O.TYPE_ID`.

**Error Handling**

- Source excerpt: `when others then r(p_text => 'Can not find Acc_type : {' || p_payment_list(j).acc_type || ':' || p_payment_list(j).pymt_amount || '} in payment list . Check [cs_acconunt] - {' ||`
- Source excerpt: `r(p_text => 'Can not find Acc_type : {' || p_payment_list(j).acc_type || ':' || p_payment_list(j).pymt_amount || '} in payment list . Check [cs_acconunt] - {' || sqlerrm || '}');`
- Source excerpt: `r(p_text => 'Acc_type: ' || p_payment_list(j).acc_type || ', not declared in [krd_pym_order]! '); end if;`
- Source excerpt: `r(p_text => 'Acc_type: ' || p_payment_list(j).acc_type || ', Payment amount:(' || l_loan_accounts_rec.pymt_amount ||`
- Source excerpt: `r(p_text => 'Acc_type: ' || p_payment_list(j).acc_type || ' Payment amount(' || l_loan_accounts_rec.pymt_amount || ') > balance amount(' || l_loan_accounts_rec.balance ||`
- Source excerpt: `r(p_text => 'Payment branch or customer or account is null Pymt_branch_no: ' || l_loan_accounts_rec.pymt_branch_no || ', Pymt_customer_no: ' ||`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.add_payment_details(...);
```

**Technical Notes**

- **Verified from Source:** 107 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="do-auto-payment"></a>
### do_Auto_Payment

**Type:** PROCEDURE  
**Source:** specification line 408; implementation begins at body line 6644.

**Purpose**

Implements **do_Auto_Payment** for the payments and balances domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `EOD_PROGRAMS_EXCEPTION`, `IN_LIST`, `KRD_TEKLIF_DETAY`, `LOAN_PAYMENT_PLAN`
2. **Invoked external or qualified routines (static call references):** `APEX_KRD2204_0_API_P.INS_KRD2204_0`, `APEX_KRD2204_2_API_P.INS_KRD2204_2`, `APEX_KRD2204_7_API_P.INS_KRD2204_7`, `GLBL_BAKIYE.REAL_BALANCE`, `GLBL_CCY.GET_CUR_RATE`, `GNI_UTILITY.DELETE_BATCH_ERROR`, `GNI_UTILITY.HAS_BATCH_ERROR`, `GNI_UTILITY.LOG_BATCH_ERROR`, `KRD2204_0_API.JUSTDOIT`, `KRD2204_0_API.UPDATE_PAYMENT_PLAN`, `LOAN_API.GENERATE_ALLOCATED_PAYMENT_LIST`, `LOAN_API.GET_LOAN_AMOUNT`, `LOAN_API.GET_OVD_DATE`, `LOAN_API.G_LOAN_ACCOUNTS_TAB`, `LOAN_TRANCHE_API.DO_TRANCHE_OPERATION`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if p_test_param is null then`
   - `elsif p_test_param = 1 and i = 1 then`
   - `elsif p_test_param = 2 and i = 2 then`
   - `when 'PAYMENT' then`
   - `when t.auto_payment_type = 2 and`
   - `when t.auto_payment_type = 2 and`
   - `if j.oper_type = 'LP_PAYMENT' then`
   - `if m.auto_payment_type = 1 or i = 1 then`
   - `elsif m.auto_payment_type = 2 then`
   - `If l_pymt_amount > 0 Then`

**Business Rules**

Verified from source:
- Conditional expression: `if p_test_param is null then`
- Conditional expression: `elsif p_test_param = 1 and i = 1 then`
- Conditional expression: `elsif p_test_param = 2 and i = 2 then`
- Conditional expression: `when 'PAYMENT' then`
- Conditional expression: `when t.auto_payment_type = 2 and`
- Conditional expression: `when t.auto_payment_type = 2 and`
- Conditional expression: `if j.oper_type = 'LP_PAYMENT' then`
- Conditional expression: `if m.auto_payment_type = 1 or i = 1 then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
Procedure do_Auto_Payment(p_min_id     number default null,
                            p_max_id     number default null,
                            p_doc_no     in varchar2 default null,
                            p_eod_sod    in varchar2 default 'E',
                            p_test_param in number default null);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_min_id` | `number` | IN | `null` | Input for `do_Auto_Payment` processing; semantics require caller/domain confirmation. |
| `p_max_id` | `number` | IN | `null` | Input for `do_Auto_Payment` processing; semantics require caller/domain confirmation. |
| `p_doc_no` | `varchar2` | IN | `null` | Input for `do_Auto_Payment` processing; semantics require caller/domain confirmation. |
| `p_eod_sod` | `varchar2` | IN | `'E'` | Input for `do_Auto_Payment` processing; semantics require caller/domain confirmation. |
| `p_test_param` | `number` | IN | `null` | Input for `do_Auto_Payment` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `EOD_PROGRAMS_EXCEPTION`, `IN_LIST`, `KRD_TEKLIF_DETAY`, `LOAN_PAYMENT_PLAN` |

Qualified procedure/function references: `APEX_KRD2204_0_API_P.INS_KRD2204_0`, `APEX_KRD2204_2_API_P.INS_KRD2204_2`, `APEX_KRD2204_7_API_P.INS_KRD2204_7`, `GLBL_BAKIYE.REAL_BALANCE`, `GLBL_CCY.GET_CUR_RATE`, `GNI_UTILITY.DELETE_BATCH_ERROR`, `GNI_UTILITY.HAS_BATCH_ERROR`, `GNI_UTILITY.LOG_BATCH_ERROR`, `KRD2204_0_API.JUSTDOIT`, `KRD2204_0_API.UPDATE_PAYMENT_PLAN`, `LOAN_API.GENERATE_ALLOCATED_PAYMENT_LIST`, `LOAN_API.GET_LOAN_AMOUNT`, `LOAN_API.GET_OVD_DATE`, `LOAN_API.G_LOAN_ACCOUNTS_TAB`, `LOAN_TRANCHE_API.DO_TRANCHE_OPERATION`.

**Error Handling**

- Source excerpt: `r(p_text => 'Auto payment type should be 1-Plan payment or 2-Off plan payment!'); end if; `
- Source excerpt: `When Others Then rollback; gni_utility.log_batch_error(p_tx_fid        => l_Tx_Fid,`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **1**; `ROLLBACK` references: **1** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.do_Auto_Payment(...);
```

**Technical Notes**

- **Verified from Source:** 288 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

## Payment schedules and dates

<a id="post-int-amount-to-plan"></a>
### post_int_amount_to_plan

**Type:** PROCEDURE  
**Source:** specification line 74; implementation begins at body line 35.

**Purpose**

Implements **post_int_amount_to_plan** for the payment schedules and dates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `LOAN_ACC_TYPES_PR`, `LOAN_PAYMENT_PLAN`, `LOAN_TRANCHE_PAYMENT_PLAN`; updates `LOAN_PAYMENT_PLAN`, `LOAN_TRANCHE_PAYMENT_PLAN`
2. **Invoked external or qualified routines (static call references):** `LOAN_TRANCHE_API.TABLE_LOG_OPERATION`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `when no_data_found then`
   - `when others then`
   - `if l_acc_type_group = 'INT' then`
   - `when others then`
   - `if l_main_sch_upd_type = 3 and l_main_pym_amount = 0 then`
   - `if p_with_tranche_info_yn = 'N' then`
   - `when l_acc_type_group = 'INT' and`
   - `elsif p_with_tranche_info_yn = 'Y' then`
   - `when l_acc_type_group = 'INT' and`
   - `if sql%rowcount = 0 then`

**Business Rules**

Verified from source:
- Conditional expression: `when no_data_found then`
- Conditional expression: `when others then`
- Conditional expression: `if l_acc_type_group = 'INT' then`
- Conditional expression: `when others then`
- Conditional expression: `if l_main_sch_upd_type = 3 and l_main_pym_amount = 0 then`
- Conditional expression: `if p_with_tranche_info_yn = 'N' then`
- Conditional expression: `when l_acc_type_group = 'INT' and`
- Conditional expression: `elsif p_with_tranche_info_yn = 'Y' then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

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

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_doc_no` | `varchar2` | IN | — | Input for `post_int_amount_to_plan` processing; semantics require caller/domain confirmation. |
| `p_tranche_no` | `number` | IN | — | Input for `post_int_amount_to_plan` processing; semantics require caller/domain confirmation. |
| `p_tx_fid` | `number` | IN | — | Input for `post_int_amount_to_plan` processing; semantics require caller/domain confirmation. |
| `p_acc_type` | `varchar2` | IN | — | Input for `post_int_amount_to_plan` processing; semantics require caller/domain confirmation. |
| `p_amount` | `number` | IN | — | Input for `post_int_amount_to_plan` processing; semantics require caller/domain confirmation. |
| `p_plan_date` | `date` | IN | — | Input for `post_int_amount_to_plan` processing; semantics require caller/domain confirmation. |
| `p_with_tranche_info_yn` | `varchar2` | IN | — | Input for `post_int_amount_to_plan` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `LOAN_ACC_TYPES_PR`, `LOAN_PAYMENT_PLAN`, `LOAN_TRANCHE_PAYMENT_PLAN` |
| UPDATE | `LOAN_PAYMENT_PLAN`, `LOAN_TRANCHE_PAYMENT_PLAN` |

Qualified procedure/function references: `LOAN_TRANCHE_API.TABLE_LOG_OPERATION`.

**Error Handling**

- Source excerpt: `when no_data_found then r(p_text => 'Account type{' || p_acc_type || '} not found, In table LOAN_ACC_TYPES_PR, only account types with has_payment_plan_yn = Y`
- Source excerpt: `r(p_text => 'Account type{' || p_acc_type || '} not found, In table LOAN_ACC_TYPES_PR, only account types with has_payment_plan_yn = Y and acc_type_group in (INT, INT_TRS, OVD_INT, PEN) can post amounts to the plan');`
- Source excerpt: `when others then r(p_text => 'Error encountered in search in acc_type{' || p_acc_type || '} in LOAN_ACC_TYPES_PR table!');`
- Source excerpt: `r(p_text => 'Error encountered in search in acc_type{' || p_acc_type || '} in LOAN_ACC_TYPES_PR table!'); end;`
- Source excerpt: `when others then r(p_text => 'Error encountered in search of main acc type with params: doc_no{' || p_doc_no || '}, tranche_no{' || p_tranche_no ||`
- Source excerpt: `r(p_text => 'Error encountered in search of main acc type with params: doc_no{' || p_doc_no || '}, tranche_no{' || p_tranche_no || '}, plan_date{' || p_plan_date ||`
- Source excerpt: `r(p_text => 'Posting amounts is not allowed for this account type{' || p_acc_type || '}'); end if;`
- Source excerpt: `r(p_text => 'p_with_tranche_info_yn shoul be Y - with tranche loans, N - for standart loans!'); end if; `
- Source excerpt: `r(p_text => 'Plan with acc_type {' || p_acc_type || '} not founc!'); end if; `
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- Direct DML detected: UPDATE.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.post_int_amount_to_plan(...);
```

**Technical Notes**

- **Verified from Source:** 145 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-overdue-grace-days"></a>
### get_overdue_grace_days

**Type:** FUNCTION  
**Source:** specification line 179; implementation begins at body line 2276.

**Purpose**

Implements **get_overdue_grace_days** for the payment schedules and dates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `PKRD_TURKOD_PR`
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `when no_data_found then`
   - `when others then`

**Business Rules**

Verified from source:
- Conditional expression: `when no_data_found then`
- Conditional expression: `when others then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
function get_overdue_grace_days(p_product_code in number,
                                  p_acc_type     in varchar2) return number;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_product_code` | `number` | IN | — | Input for `get_overdue_grace_days` processing; semantics require caller/domain confirmation. |
| `p_acc_type` | `varchar2` | IN | — | Input for `get_overdue_grace_days` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `number`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `PKRD_TURKOD_PR` |

**Error Handling**

- Source excerpt: `when no_data_found then r(p_text => 'Product code ' || p_product_code || ' not found in pkrd_turkod_pr table!');`
- Source excerpt: `r(p_text => 'Product code ' || p_product_code || ' not found in pkrd_turkod_pr table!'); when others then`
- Source excerpt: `when others then r(p_text => 'Error encountered in search of Product code ' || p_product_code || ' in pkrd_turkod_pr table!');`
- Source excerpt: `r(p_text => 'Error encountered in search of Product code ' || p_product_code || ' in pkrd_turkod_pr table!'); end;`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_overdue_grace_days(...);
```

**Technical Notes**

- **Verified from Source:** 24 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-formatted-grace-from-list"></a>
### get_formatted_grace_from_list

**Type:** FUNCTION  
**Source:** specification line 188; implementation begins at body line 2436.

**Purpose**

Implements **get_formatted_grace_from_list** for the payment schedules and dates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** No direct SQL table access identified in the method segment.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if m.next_number_ - m.number_ = 1 then`
   - `if l_number is null or l_symbol = ',' then`
   - `if l_symbol = ',' then`
   - `if not l_is_valid then`

**Business Rules**

Verified from source:
- Conditional expression: `if m.next_number_ - m.number_ = 1 then`
- Conditional expression: `if l_number is null or l_symbol = ',' then`
- Conditional expression: `if l_symbol = ',' then`
- Conditional expression: `if not l_is_valid then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
function get_formatted_grace_from_list(p_period_list in varchar2)
    return varchar2;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_period_list` | `varchar2` | IN | — | Input for `get_formatted_grace_from_list` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `varchar2`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| Direct SQL | None identified; called routines may perform data access. |

**Error Handling**

- Source excerpt: `r(p_text => q'(Defines grace periods for principal and interest payments using formats like '1-4' for consecutive months (1,2,3,4), '2,4,6' for specific months, or '1-4,6,9' for mixed ranges (1,2,3,4,6,9))');`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_formatted_grace_from_list(...);
```

**Technical Notes**

- **Verified from Source:** 41 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-grace-info"></a>
### get_grace_info

**Type:** FUNCTION  
**Source:** specification line 191; implementation begins at body line 2476.

**Purpose**

Implements **get_grace_info** for the payment schedules and dates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `LOAN_PAYMENT_PLAN`
2. **Invoked external or qualified routines (static call references):** `LOAN_API.GET_FORMATTED_GRACE_FROM_LIST`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if p_info_type not in ('HAS_GRACE', 'PERIOD', 'COUNT', 'MONTHS') then`
   - `if p_info_type = 'HAS_GRACE' then`
   - `return case when l_result is null then 'N' else 'Y' end;`
   - `elsif p_info_type in ('MONTHS') then`
   - `elsif p_info_type in ('PERIOD') then`
   - `elsif p_info_type = 'COUNT' then`

**Business Rules**

Verified from source:
- Conditional expression: `if p_info_type not in ('HAS_GRACE', 'PERIOD', 'COUNT', 'MONTHS') then`
- Conditional expression: `if p_info_type = 'HAS_GRACE' then`
- Conditional expression: `return case when l_result is null then 'N' else 'Y' end;`
- Conditional expression: `elsif p_info_type in ('MONTHS') then`
- Conditional expression: `elsif p_info_type in ('PERIOD') then`
- Conditional expression: `elsif p_info_type = 'COUNT' then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
function get_grace_info(p_Doc_No          In Varchar2,
                          p_period_end_date in date,
                          p_acc_type        In Varchar2 default 'A',
                          p_info_type       in varchar2) Return varchar2;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_Doc_No` | `Varchar2` | IN | — | Input for `get_grace_info` processing; semantics require caller/domain confirmation. |
| `p_period_end_date` | `date` | IN | — | Input for `get_grace_info` processing; semantics require caller/domain confirmation. |
| `p_acc_type` | `Varchar2` | IN | `'A'` | Input for `get_grace_info` processing; semantics require caller/domain confirmation. |
| `p_info_type` | `varchar2` | IN | — | Input for `get_grace_info` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `varchar2`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `LOAN_PAYMENT_PLAN` |

Qualified procedure/function references: `LOAN_API.GET_FORMATTED_GRACE_FROM_LIST`.

**Error Handling**

- Source excerpt: `r(p_text => 'p_info_type should be HAS_GRACE - Indicates whether a grace period applies (Y/N) PERIOD - Lists the applicable months in formats like 1-4, 2,4,6, or 1-4,6,9 COUNT - Specifies the number of grace periods allowed`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_grace_info(...);
```

**Technical Notes**

- **Verified from Source:** 48 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-commission-schedule"></a>
### get_commission_schedule

**Type:** FUNCTION  
**Source:** specification line 229; implementation begins at body line 2963.

**Purpose**

Implements **get_commission_schedule** for the payment schedules and dates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** No direct SQL table access identified in the method segment.
2. **Invoked external or qualified routines (static call references):** `GLBL_FAIZ.DAYS_BETWEEN2`, `GLBL_TARIH.ONCEKI_ISGUNU`, `GNI_MESSAGE.GET_MESSAGE`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `If p_begin_date Is Null Or p_end_date Is Null Then`
   - `If p_begin_date >= p_end_date Then`
   - `If p_amount <= 0 Then`
   - `If l_Row_Count = 0 Then`
   - `If l_Bitme_Tar > l_Son_Vade Then`
   - `Elsif l_Son_Vade = l_Bitme_Tar Then`
   - `If l_Gun_Sayi > 0 Then`
   - `Exit When l_Bitme_Tar = l_Son_Vade;`
   - `If l_Muddet > 0 Then`
   - `If i = Ode_Plan_Col.Last Then`

**Business Rules**

Verified from source:
- Conditional expression: `If p_begin_date Is Null Or p_end_date Is Null Then`
- Conditional expression: `If p_begin_date >= p_end_date Then`
- Conditional expression: `If p_amount <= 0 Then`
- Conditional expression: `If l_Row_Count = 0 Then`
- Conditional expression: `If l_Bitme_Tar > l_Son_Vade Then`
- Conditional expression: `Elsif l_Son_Vade = l_Bitme_Tar Then`
- Conditional expression: `If l_Gun_Sayi > 0 Then`
- Conditional expression: `Exit When l_Bitme_Tar = l_Son_Vade;`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
Function get_commission_schedule(p_begin_date    In Date,
                                   p_end_date      In Date,
                                   p_amount        In Number,
                                   p_int_calc_type in varchar2)
    Return Krd_Kom_Plan_Tt
    Pipelined;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_begin_date` | `Date` | IN | — | Input for `get_commission_schedule` processing; semantics require caller/domain confirmation. |
| `p_end_date` | `Date` | IN | — | Input for `get_commission_schedule` processing; semantics require caller/domain confirmation. |
| `p_amount` | `Number` | IN | — | Input for `get_commission_schedule` processing; semantics require caller/domain confirmation. |
| `p_int_calc_type` | `varchar2` | IN | — | Input for `get_commission_schedule` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `Krd_Kom_Plan_Tt`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| Direct SQL | None identified; called routines may perform data access. |

Qualified procedure/function references: `GLBL_FAIZ.DAYS_BETWEEN2`, `GLBL_TARIH.ONCEKI_ISGUNU`, `GNI_MESSAGE.GET_MESSAGE`.

**Error Handling**

- Source excerpt: `r(p_text => gni_message.get_message('GNI_SYSTEM_VERILME_BITME_TARIX', p_begin_date, p_end_date));`
- Source excerpt: `r(p_text => gni_message.get_message(l_mess_name => 'GNI_SYSTEM_KOMISSIYA_QRAFIK')); End If; If p_amount <= 0 Then`
- Source excerpt: `r(p_text => gni_message.get_message(l_mess_name => 'GNI_SYSTEM_KOMISSIYA_MEBLEG')); End If; `
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_commission_schedule(...);
```

**Technical Notes**

- **Verified from Source:** 92 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-next-plan-pym"></a>
### get_next_Plan_Pym

**Type:** FUNCTION  
**Source:** specification line 240; implementation begins at body line 3086.

**Purpose**

Implements **get_next_Plan_Pym** for the payment schedules and dates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `LOAN_PAYMENT_PLAN`
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `Select Nvl(Sum(case when a.anapara_faiz = 'A' and a.durum = 'A' then Nvl(a.Taksit_Tutar, 0) - Nvl(a.Odenen_Tutar, 0) end), 0) main_amount,`

**Business Rules**

Verified from source:
- Conditional expression: `Select Nvl(Sum(case when a.anapara_faiz = 'A' and a.durum = 'A' then Nvl(a.Taksit_Tutar, 0) - Nvl(a.Odenen_Tutar, 0) end), 0) main_amount,`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
Function get_next_Plan_Pym(p_doc_no   In Varchar2,
                             P_date     In Date,
                             p_acc_type in varchar2) Return Number;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_doc_no` | `Varchar2` | IN | — | Input for `get_next_Plan_Pym` processing; semantics require caller/domain confirmation. |
| `P_date` | `Date` | IN | — | Input for `get_next_Plan_Pym` processing; semantics require caller/domain confirmation. |
| `p_acc_type` | `varchar2` | IN | — | Input for `get_next_Plan_Pym` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `Number`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `LOAN_PAYMENT_PLAN` |

**Error Handling**

- No explicit error handler or raised application message identified within this method segment. Propagated exceptions from dependencies remain possible.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_next_Plan_Pym(...);
```

**Technical Notes**

- **Verified from Source:** 34 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-plan-payment-amount"></a>
### get_plan_payment_amount

**Type:** FUNCTION  
**Source:** specification line 249; implementation begins at body line 3142.

**Purpose**

Implements **get_plan_payment_amount** for the payment schedules and dates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `KRD_TEKLIF_DETAY`, `LOAN_PAYMENT_PLAN`
2. **Invoked external or qualified routines (static call references):** `LOAN_TRANCHE_API.GET_PLAN_PAYMENT_AMOUNT`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if l_With_Tranche_Info_Yn = 'Y' then`

**Business Rules**

Verified from source:
- Conditional expression: `if l_With_Tranche_Info_Yn = 'Y' then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
function get_plan_payment_amount(p_doc_no   in varchar2,
                                   p_date     in date default glbl.getsysdate,
                                   p_acc_type in varchar2 default null)
    return number;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_doc_no` | `varchar2` | IN | — | Input for `get_plan_payment_amount` processing; semantics require caller/domain confirmation. |
| `p_date` | `date` | IN | `glbl.getsysdate` | Input for `get_plan_payment_amount` processing; semantics require caller/domain confirmation. |
| `p_acc_type` | `varchar2` | IN | `null` | Input for `get_plan_payment_amount` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `number`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `KRD_TEKLIF_DETAY`, `LOAN_PAYMENT_PLAN` |

Qualified procedure/function references: `LOAN_TRANCHE_API.GET_PLAN_PAYMENT_AMOUNT`.

**Error Handling**

- No explicit error handler or raised application message identified within this method segment. Propagated exceptions from dependencies remain possible.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_plan_payment_amount(...);
```

**Technical Notes**

- **Verified from Source:** 34 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-plan-month-count"></a>
### get_Plan_Month_Count

**Type:** FUNCTION  
**Source:** specification line 273; implementation begins at body line 3236.

**Purpose**

Implements **get_Plan_Month_Count** for the payment schedules and dates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** No direct SQL table access identified in the method segment.
2. **Invoked external or qualified routines (static call references):** `GLBL_FAIZ.DAYS_BETWEEN2`, `LOAN_API.ADD_MONTHS_FOR_LOAN`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `If l_Muddet > 0 Then`
   - `If Glbl_Faiz.Days_Between2(Enddate   => p_End_Date,`
   - `Exit When p_End_Date = l_calc_date;`
   - `if p_work_days = 'Y' then`

**Business Rules**

Verified from source:
- Conditional expression: `If l_Muddet > 0 Then`
- Conditional expression: `If Glbl_Faiz.Days_Between2(Enddate   => p_End_Date,`
- Conditional expression: `Exit When p_End_Date = l_calc_date;`
- Conditional expression: `if p_work_days = 'Y' then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
Function get_Plan_Month_Count(p_Start_Date    In Date,
                                p_End_Date      In Date,
                                p_int_calc_type varchar2 default '30/360 AZ',
                                p_work_days     varchar2 default 'Y',
                                p_pymt_day      number default null)
    Return Number;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_Start_Date` | `Date` | IN | — | Input for `get_Plan_Month_Count` processing; semantics require caller/domain confirmation. |
| `p_End_Date` | `Date` | IN | — | Input for `get_Plan_Month_Count` processing; semantics require caller/domain confirmation. |
| `p_int_calc_type` | `varchar2` | IN | `'30/360 AZ'` | Input for `get_Plan_Month_Count` processing; semantics require caller/domain confirmation. |
| `p_work_days` | `varchar2` | IN | `'Y'` | Input for `get_Plan_Month_Count` processing; semantics require caller/domain confirmation. |
| `p_pymt_day` | `number` | IN | `null` | Input for `get_Plan_Month_Count` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `Number`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| Direct SQL | None identified; called routines may perform data access. |

Qualified procedure/function references: `GLBL_FAIZ.DAYS_BETWEEN2`, `LOAN_API.ADD_MONTHS_FOR_LOAN`.

**Error Handling**

- No explicit error handler or raised application message identified within this method segment. Propagated exceptions from dependencies remain possible.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_Plan_Month_Count(...);
```

**Technical Notes**

- **Verified from Source:** 44 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-plan-paid-month-count"></a>
### get_plan_paid_month_count

**Type:** FUNCTION  
**Source:** specification line 280; implementation begins at body line 3279.

**Purpose**

Implements **get_plan_paid_month_count** for the payment schedules and dates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** No direct SQL table access identified in the method segment.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if p_doc_no || p_term || p_date is not null then`
   - `when kd.anapara_faiz = 'A' then`
   - `when kd.durum = 'T' or`
   - `when kd.anapara_faiz = 'F' then`
   - `when kd.durum = 'T' or`
   - `if l_count = p_term then`

**Business Rules**

Verified from source:
- Conditional expression: `if p_doc_no || p_term || p_date is not null then`
- Conditional expression: `when kd.anapara_faiz = 'A' then`
- Conditional expression: `when kd.durum = 'T' or`
- Conditional expression: `when kd.anapara_faiz = 'F' then`
- Conditional expression: `when kd.durum = 'T' or`
- Conditional expression: `if l_count = p_term then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
function get_plan_paid_month_count(p_doc_no in varchar2,
                                     p_term   in number,
                                     p_date   in date) return number;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_doc_no` | `varchar2` | IN | — | Input for `get_plan_paid_month_count` processing; semantics require caller/domain confirmation. |
| `p_term` | `number` | IN | — | Input for `get_plan_paid_month_count` processing; semantics require caller/domain confirmation. |
| `p_date` | `date` | IN | — | Input for `get_plan_paid_month_count` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `number`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| Direct SQL | None identified; called routines may perform data access. |

**Error Handling**

- Source excerpt: `r('Salaaaam');  return 0;`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_plan_paid_month_count(...);
```

**Technical Notes**

- **Verified from Source:** 61 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-plan-error"></a>
### get_plan_error

**Type:** FUNCTION  
**Source:** specification line 285; implementation begins at body line 3339.

**Purpose**

Implements **get_plan_error** for the payment schedules and dates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** No direct SQL table access identified in the method segment.
2. **Invoked external or qualified routines (static call references):** `GLBL.TO_NUMBER#`, `LOAN_API.GET_GL_VALUE`.
3. **Control flow:** no prominent conditional branches were isolated by static inspection; review the implementation for full semantics.

**Business Rules**

Verified from source:
- No explicit business threshold or conditional rule could be isolated in this method segment.
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
Function get_plan_error(p_doc_no varchar2,
                          p_date   date default glbl.getsysdate)
    return varchar2;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_doc_no` | `varchar2` | IN | — | Input for `get_plan_error` processing; semantics require caller/domain confirmation. |
| `p_date` | `date` | IN | `glbl.getsysdate` | Input for `get_plan_error` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `varchar2`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| Direct SQL | None identified; called routines may perform data access. |

Qualified procedure/function references: `GLBL.TO_NUMBER#`, `LOAN_API.GET_GL_VALUE`.

**Error Handling**

- No explicit error handler or raised application message identified within this method segment. Propagated exceptions from dependencies remain possible.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_plan_error(...);
```

**Technical Notes**

- **Verified from Source:** 28 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-annuity-amount"></a>
### get_Annuity_Amount

**Type:** FUNCTION  
**Source:** specification line 290; implementation begins at body line 3923.

**Purpose**

Implements **get_Annuity_Amount** for the payment schedules and dates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `LOAN_PAYMENT_PLAN`
3. **Control flow:** no prominent conditional branches were isolated by static inspection; review the implementation for full semantics.

**Business Rules**

Verified from source:
- No explicit business threshold or conditional rule could be isolated in this method segment.
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
Function get_Annuity_Amount(p_Doc_No      In Varchar2,
                              p_return_type In varchar2 default 'NO_ZERO')
    Return Number;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_Doc_No` | `Varchar2` | IN | — | Input for `get_Annuity_Amount` processing; semantics require caller/domain confirmation. |
| `p_return_type` | `varchar2` | IN | `'NO_ZERO'` | Input for `get_Annuity_Amount` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `Number`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `LOAN_PAYMENT_PLAN` |

**Error Handling**

- No explicit error handler or raised application message identified within this method segment. Propagated exceptions from dependencies remain possible.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_Annuity_Amount(...);
```

**Technical Notes**

- **Verified from Source:** 30 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-pym-startdate"></a>
### get_Pym_Startdate

**Type:** FUNCTION  
**Source:** specification line 295; implementation begins at body line 3952.

**Purpose**

Implements **get_Pym_Startdate** for the payment schedules and dates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `LOAN_PAYMENT_PLAN`
2. **Invoked external or qualified routines (static call references):** `GLBL_FAIZ.DAYS_BETWEEN2`, `GLBL_TARIH.ONCEKI_ISGUNU`, `GNI_MESSAGE.GET_MESSAGE`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `when l_Date < l_sysdate then`
   - `If p_pymt_date Is Null Then`
   - `if l_next_first_pymt_Date is not null then`
   - `If Glbl_Faiz.Days_Between2(Enddate   => l_Plan_End_Date,`
   - `if l_next_first_pymt_Date is null or`
   - `if l_Plan_End_Date = l_Plan_Min_Date or l_Plan_Min_Date > l_date then`
   - `If l_day_of_start_date < l_day_of_plan_date Then`
   - `If l_Plan_Min_Date = l_Plan_End_Date Then`
   - `if p_pymt_date < l_date then`
   - `When Others Then`

**Business Rules**

Verified from source:
- Conditional expression: `when l_Date < l_sysdate then`
- Conditional expression: `If p_pymt_date Is Null Then`
- Conditional expression: `if l_next_first_pymt_Date is not null then`
- Conditional expression: `If Glbl_Faiz.Days_Between2(Enddate   => l_Plan_End_Date,`
- Conditional expression: `if l_next_first_pymt_Date is null or`
- Conditional expression: `if l_Plan_End_Date = l_Plan_Min_Date or l_Plan_Min_Date > l_date then`
- Conditional expression: `If l_day_of_start_date < l_day_of_plan_date Then`
- Conditional expression: `If l_Plan_Min_Date = l_Plan_End_Date Then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

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

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_Doc_No` | `Varchar2` | IN | — | Input for `get_Pym_Startdate` processing; semantics require caller/domain confirmation. |
| `p_pymt_date` | `Date` | IN | — | Input for `get_Pym_Startdate` processing; semantics require caller/domain confirmation. |
| `p_pymt_day` | `Number` | IN | — | Input for `get_Pym_Startdate` processing; semantics require caller/domain confirmation. |
| `p_pymt_period` | `Number` | IN | — | Input for `get_Pym_Startdate` processing; semantics require caller/domain confirmation. |
| `p_acc_type` | `varchar2` | IN | — | Input for `get_Pym_Startdate` processing; semantics require caller/domain confirmation. |
| `p_loan_end_Date` | `date` | IN | — | Input for `get_Pym_Startdate` processing; semantics require caller/domain confirmation. |
| `p_check_is_closed` | `varchar2` | IN | `'Y'` | Input for `get_Pym_Startdate` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `Date`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `LOAN_PAYMENT_PLAN` |

Qualified procedure/function references: `GLBL_FAIZ.DAYS_BETWEEN2`, `GLBL_TARIH.ONCEKI_ISGUNU`, `GNI_MESSAGE.GET_MESSAGE`.

**Error Handling**

- Source excerpt: `r(p_text => gni_message.get_message('GNI_SYSTEM_GET_PYM_STARTDATE_NULL', p_Doc_No)); End If;`
- Source excerpt: `When Others Then l_Pym_Startdate := Last_Day(l_Plan_Min_Date); End;`
- Source excerpt: `r(p_text => gni_message.get_message('GNI_SYSTEM_GET_PYM_STARTDATE_SYSDATE', p_Doc_No)); End If;`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_Pym_Startdate(...);
```

**Technical Notes**

- **Verified from Source:** 109 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="is-payment-date"></a>
### is_Payment_Date

**Type:** FUNCTION  
**Source:** specification line 309; implementation begins at body line 4410.

**Purpose**

Implements **is_Payment_Date** for the payment schedules and dates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `LOAN_PAYMENT_PLAN`
2. **Invoked external or qualified routines (static call references):** `GLBL_TARIH.ONCEKI_ISGUNU`.
3. **Control flow:** no prominent conditional branches were isolated by static inspection; review the implementation for full semantics.

**Business Rules**

Verified from source:
- No explicit business threshold or conditional rule could be isolated in this method segment.
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
Function is_Payment_Date(p_Document_No In Varchar2, p_Date Date)
    Return Varchar2;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_Document_No` | `Varchar2` | IN | — | Input for `is_Payment_Date` processing; semantics require caller/domain confirmation. |
| `p_Date` | `Date` | IN | — | Input for `is_Payment_Date` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `Varchar2`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `LOAN_PAYMENT_PLAN` |

Qualified procedure/function references: `GLBL_TARIH.ONCEKI_ISGUNU`.

**Error Handling**

- No explicit error handler or raised application message identified within this method segment. Propagated exceptions from dependencies remain possible.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.is_Payment_Date(...);
```

**Technical Notes**

- **Verified from Source:** 14 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="recalculate-int-payment-plan"></a>
### recalculate_int_payment_plan

**Type:** PROCEDURE  
**Source:** specification line 335; implementation begins at body line 5181.

**Purpose**

Implements **recalculate_int_payment_plan** for the payment schedules and dates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `LOAN_PAYMENT_PLAN`; updates `LOAN_PAYMENT_PLAN`
2. **Invoked external or qualified routines (static call references):** `GLBL_FAIZ.DAY_COUNT_BASIS_NEW`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if p_schedule_update_type not in (3, 4) or length(p_acc_type) = -1 then`
   - `if p_schedule_update_type = 3 then`
   - `if m.plan_payment = 0 then`
   - `elsif m.plan_payment != 0 then`

**Business Rules**

Verified from source:
- Conditional expression: `if p_schedule_update_type not in (3, 4) or length(p_acc_type) = -1 then`
- Conditional expression: `if p_schedule_update_type = 3 then`
- Conditional expression: `if m.plan_payment = 0 then`
- Conditional expression: `elsif m.plan_payment != 0 then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
procedure recalculate_int_payment_plan(p_doc_no               in varchar2,
                                         p_acc_type             in varchar2,
                                         p_main_amount          in number,
                                         p_INT_RATIO            in number,
                                         p_int_calc_type        in varchar2,
                                         p_schedule_update_type in number);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_doc_no` | `varchar2` | IN | — | Input for `recalculate_int_payment_plan` processing; semantics require caller/domain confirmation. |
| `p_acc_type` | `varchar2` | IN | — | Input for `recalculate_int_payment_plan` processing; semantics require caller/domain confirmation. |
| `p_main_amount` | `number` | IN | — | Input for `recalculate_int_payment_plan` processing; semantics require caller/domain confirmation. |
| `p_INT_RATIO` | `number` | IN | — | Input for `recalculate_int_payment_plan` processing; semantics require caller/domain confirmation. |
| `p_int_calc_type` | `varchar2` | IN | — | Input for `recalculate_int_payment_plan` processing; semantics require caller/domain confirmation. |
| `p_schedule_update_type` | `number` | IN | — | Input for `recalculate_int_payment_plan` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `LOAN_PAYMENT_PLAN` |
| UPDATE | `LOAN_PAYMENT_PLAN` |

Qualified procedure/function references: `GLBL_FAIZ.DAY_COUNT_BASIS_NEW`.

**Error Handling**

- Source excerpt: `r(p_text => 'p_schedule_update_type should be 3 or 4!'); end if; for m in (select k.fid,`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- Direct DML detected: UPDATE.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.recalculate_int_payment_plan(...);
```

**Technical Notes**

- **Verified from Source:** 62 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="do-plan-control"></a>
### do_plan_control

**Type:** PROCEDURE  
**Source:** specification line 359; implementation begins at body line 5242.

**Purpose**

Implements **do_plan_control** for the payment schedules and dates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `LOAN_EOD_CONTROL_EXP`
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if l_count > 0 then`
   - `if l_err_desc is not null then`

**Business Rules**

Verified from source:
- Conditional expression: `if l_count > 0 then`
- Conditional expression: `if l_err_desc is not null then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
procedure do_plan_control(p_document_no in varchar2,
                            p_date        date default glbl.getsysdate);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_document_no` | `varchar2` | IN | — | Input for `do_plan_control` processing; semantics require caller/domain confirmation. |
| `p_date` | `date` | IN | `glbl.getsysdate` | Input for `do_plan_control` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `LOAN_EOD_CONTROL_EXP` |

**Error Handling**

- Source excerpt: `r(l_err_desc); end if; end;`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.do_plan_control(...);
```

**Technical Notes**

- **Verified from Source:** 20 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="do-schedule-allignment"></a>
### do_schedule_allignment

**Type:** PROCEDURE  
**Source:** specification line 464; implementation begins at body line 8744.

**Purpose**

Implements **do_schedule_allignment** for the payment schedules and dates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `LOAN_PAYMENT_PLAN`; updates `LOAN_PAYMENT_PLAN`
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `If p_payment_amount > 0 Then`
   - `If l_payment_amount >= Rg.Payment_Amount - Nvl(Rg.Paid_Amount, 0) Then`
   - `Exit When l_payment_amount = 0;`
   - `Elsif p_payment_amount < 0 Then`

**Business Rules**

Verified from source:
- Conditional expression: `If p_payment_amount > 0 Then`
- Conditional expression: `If l_payment_amount >= Rg.Payment_Amount - Nvl(Rg.Paid_Amount, 0) Then`
- Conditional expression: `Exit When l_payment_amount = 0;`
- Conditional expression: `Elsif p_payment_amount < 0 Then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
Procedure do_schedule_allignment(p_doc_no         In Varchar2,
                                   p_payment_amount In Number,
                                   p_acc_type       In Varchar2,
                                   p_date           In Date default glbl.getsysdate);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_doc_no` | `Varchar2` | IN | — | Input for `do_schedule_allignment` processing; semantics require caller/domain confirmation. |
| `p_payment_amount` | `Number` | IN | — | Input for `do_schedule_allignment` processing; semantics require caller/domain confirmation. |
| `p_acc_type` | `Varchar2` | IN | — | Input for `do_schedule_allignment` processing; semantics require caller/domain confirmation. |
| `p_date` | `Date` | IN | `glbl.getsysdate` | Input for `do_schedule_allignment` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `LOAN_PAYMENT_PLAN` |
| UPDATE | `LOAN_PAYMENT_PLAN` |

**Error Handling**

- Source excerpt: `r('at [do_schedule_allignment] parametr [p_payment_amount] less than [0]'); End If; `
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- Direct DML detected: UPDATE.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.do_schedule_allignment(...);
```

**Technical Notes**

- **Verified from Source:** 51 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="do-com-schedule-allignment"></a>
### do_com_schedule_allignment

**Type:** PROCEDURE  
**Source:** specification line 470; implementation begins at body line 8794.

**Purpose**

Implements **do_com_schedule_allignment** for the payment schedules and dates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `KRD_KOM_PLAN_DETAY`, `KRD_TESIS`; updates `KRD_KOM_PLAN_DETAY`
2. **Invoked external or qualified routines (static call references):** `GLOG.ASSERT#`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `When No_Data_Found Then`
   - `If p_amount > 0 Then`
   - `If p_mig_status = 1 Then`
   - `If p_option_code = 'T' Then`
   - `If d_Odenen_Risk >= Rg.Taksit_Tutar - Nvl(Rg.Odenen_Tutar, 0) Then`
   - `Exit When d_Odenen_Risk = 0;`
   - `Elsif p_amount < 0 Then`
   - `If p_option_code In ('T', 'K') Then`
   - `If d_Odenen_Risk >= Nvl(r.Odenen_Tutar, 0) Then`
   - `Exit When d_Odenen_Risk = 0;`

**Business Rules**

Verified from source:
- Conditional expression: `When No_Data_Found Then`
- Conditional expression: `If p_amount > 0 Then`
- Conditional expression: `If p_mig_status = 1 Then`
- Conditional expression: `If p_option_code = 'T' Then`
- Conditional expression: `If d_Odenen_Risk >= Rg.Taksit_Tutar - Nvl(Rg.Odenen_Tutar, 0) Then`
- Conditional expression: `Exit When d_Odenen_Risk = 0;`
- Conditional expression: `Elsif p_amount < 0 Then`
- Conditional expression: `If p_option_code In ('T', 'K') Then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
Procedure do_com_schedule_allignment(p_doc_no      In Varchar2,
                                       p_option_code In Varchar2,
                                       p_amount      In Number,
                                       p_plan_type   In Varchar2,
                                       p_mig_status  In Number Default 0);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_doc_no` | `Varchar2` | IN | — | Input for `do_com_schedule_allignment` processing; semantics require caller/domain confirmation. |
| `p_option_code` | `Varchar2` | IN | — | Input for `do_com_schedule_allignment` processing; semantics require caller/domain confirmation. |
| `p_amount` | `Number` | IN | — | Input for `do_com_schedule_allignment` processing; semantics require caller/domain confirmation. |
| `p_plan_type` | `Varchar2` | IN | — | Input for `do_com_schedule_allignment` processing; semantics require caller/domain confirmation. |
| `p_mig_status` | `Number` | IN | `0` | Input for `do_com_schedule_allignment` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `KRD_KOM_PLAN_DETAY`, `KRD_TESIS` |
| UPDATE | `KRD_KOM_PLAN_DETAY` |

Qualified procedure/function references: `GLOG.ASSERT#`.

**Error Handling**

- Source excerpt: `When No_Data_Found Then Glog.Assert#(False, g_Mesg('KREDI_HESAPNO_EKNO', p_doc_no),`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- Direct DML detected: UPDATE.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.do_com_schedule_allignment(...);
```

**Technical Notes**

- **Verified from Source:** 121 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-schedule-from-memo"></a>
### get_schedule_from_memo

**Type:** FUNCTION  
**Source:** specification line 524; implementation begins at body line 9694.

**Purpose**

Implements **get_schedule_from_memo** for the payment schedules and dates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `KRD_SCOR_ODEME_PLAN`
2. **Invoked external or qualified routines (static call references):** `GLBL_FAIZ.DAY_COUNT_BASIS_NEW`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `when start_date then`

**Business Rules**

Verified from source:
- Conditional expression: `when start_date then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
function get_schedule_from_memo(p_memorandum_id varchar2,
                                  p_int_ratio     number,
                                  p_int_calc_type varchar2,
                                  p_int_amount    number) return SCHEDULE_TT
    pipelined;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_memorandum_id` | `varchar2` | IN | — | Input for `get_schedule_from_memo` processing; semantics require caller/domain confirmation. |
| `p_int_ratio` | `number` | IN | — | Input for `get_schedule_from_memo` processing; semantics require caller/domain confirmation. |
| `p_int_calc_type` | `varchar2` | IN | — | Input for `get_schedule_from_memo` processing; semantics require caller/domain confirmation. |
| `p_int_amount` | `number` | IN | — | Input for `get_schedule_from_memo` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `SCHEDULE_TT`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `KRD_SCOR_ODEME_PLAN` |

Qualified procedure/function references: `GLBL_FAIZ.DAY_COUNT_BASIS_NEW`.

**Error Handling**

- No explicit error handler or raised application message identified within this method segment. Propagated exceptions from dependencies remain possible.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_schedule_from_memo(...);
```

**Technical Notes**

- **Verified from Source:** 44 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-standart-schedule"></a>
### get_standart_schedule

**Type:** FUNCTION  
**Source:** specification line 530; implementation begins at body line 9806.

**Purpose**

Implements **get_standart_schedule** for the payment schedules and dates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** No direct SQL table access identified in the method segment.
3. **Control flow:** no prominent conditional branches were isolated by static inspection; review the implementation for full semantics.

**Business Rules**

Verified from source:
- No explicit business threshold or conditional rule could be isolated in this method segment.
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

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

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_begin_date` | `date` | IN | `glbl.getsysdate` | Input for `get_standart_schedule` processing; semantics require caller/domain confirmation. |
| `p_main_pymt_date` | `date` | IN | — | Input for `get_standart_schedule` processing; semantics require caller/domain confirmation. |
| `p_int_pymt_date` | `date` | IN | — | Input for `get_standart_schedule` processing; semantics require caller/domain confirmation. |
| `p_pymt_day` | `number` | IN | `null` | Input for `get_standart_schedule` processing; semantics require caller/domain confirmation. |
| `p_end_date` | `date` | IN | — | Input for `get_standart_schedule` processing; semantics require caller/domain confirmation. |
| `p_offer_amount` | `number` | IN | — | Input for `get_standart_schedule` processing; semantics require caller/domain confirmation. |
| `p_ovd_main_amount` | `number` | IN | `0` | Input for `get_standart_schedule` processing; semantics require caller/domain confirmation. |
| `p_int_calc_type` | `varchar2` | IN | — | Input for `get_standart_schedule` processing; semantics require caller/domain confirmation. |
| `p_main_grace_period` | `varchar2` | IN | `null` | Input for `get_standart_schedule` processing; semantics require caller/domain confirmation. |
| `p_int_grace_period` | `varchar2` | IN | `null` | Input for `get_standart_schedule` processing; semantics require caller/domain confirmation. |
| `p_remain_int_amount` | `number` | IN | `0` | Input for `get_standart_schedule` processing; semantics require caller/domain confirmation. |
| `p_min_main_pay_amount` | `number` | IN | `null` | Input for `get_standart_schedule` processing; semantics require caller/domain confirmation. |
| `p_calc_int_in_grace` | `varchar2` | IN | `'Y'` | Input for `get_standart_schedule` processing; semantics require caller/domain confirmation. |
| `p_work_days` | `varchar2` | IN | `'Y'` | Input for `get_standart_schedule` processing; semantics require caller/domain confirmation. |
| `p_loan_flow_rate_tab` | `LOAN_FLOW_RATE_TAB` | IN | `null` | Input for `get_standart_schedule` processing; semantics require caller/domain confirmation. |
| `p_loan_stop_rate_tab` | `LOAN_STOP_RATE_TAB` | IN | `null` | Input for `get_standart_schedule` processing; semantics require caller/domain confirmation. |
| `p_special_dates` | `loan_special_dates_tab` | IN | `null` | Input for `get_standart_schedule` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `SCHEDULE_TT`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| Direct SQL | None identified; called routines may perform data access. |

**Error Handling**

- No explicit error handler or raised application message identified within this method segment. Propagated exceptions from dependencies remain possible.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_standart_schedule(...);
```

**Technical Notes**

- **Verified from Source:** 64 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-annuity-schedule"></a>
### get_annuity_schedule

**Type:** FUNCTION  
**Source:** specification line 551; implementation begins at body line 10190.

**Purpose**

Implements **get_annuity_schedule** for the payment schedules and dates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** No direct SQL table access identified in the method segment.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if p_loan_flow_rate_tab.count > 1 or p_loan_flow_rate_tab(1).main_pymt_period > 1 or p_loan_flow_rate_tab(1).int_pymt_period > 1 or`
   - `elsif p_loan_stop_rate_tab is not null then`
   - `if p_loan_stop_rate_tab.count > 0 then`
   - `if p_is_mortgage = 'Y' then`

**Business Rules**

Verified from source:
- Conditional expression: `if p_loan_flow_rate_tab.count > 1 or p_loan_flow_rate_tab(1).main_pymt_period > 1 or p_loan_flow_rate_tab(1).int_pymt_period > 1 or`
- Conditional expression: `elsif p_loan_stop_rate_tab is not null then`
- Conditional expression: `if p_loan_stop_rate_tab.count > 0 then`
- Conditional expression: `if p_is_mortgage = 'Y' then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

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

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_begin_date` | `date` | IN | — | Input for `get_annuity_schedule` processing; semantics require caller/domain confirmation. |
| `p_main_pymt_date` | `date` | IN | — | Input for `get_annuity_schedule` processing; semantics require caller/domain confirmation. |
| `p_int_pymt_date` | `date` | IN | — | Input for `get_annuity_schedule` processing; semantics require caller/domain confirmation. |
| `p_pymt_day` | `number` | IN | `null` | Input for `get_annuity_schedule` processing; semantics require caller/domain confirmation. |
| `p_end_date` | `date` | IN | — | Input for `get_annuity_schedule` processing; semantics require caller/domain confirmation. |
| `p_offer_amount` | `number` | IN | — | Input for `get_annuity_schedule` processing; semantics require caller/domain confirmation. |
| `p_ovd_main_amount` | `number` | IN | `0` | Input for `get_annuity_schedule` processing; semantics require caller/domain confirmation. |
| `p_int_calc_type` | `varchar2` | IN | — | Input for `get_annuity_schedule` processing; semantics require caller/domain confirmation. |
| `p_main_grace_period` | `varchar2` | IN | `null` | Input for `get_annuity_schedule` processing; semantics require caller/domain confirmation. |
| `p_int_grace_period` | `varchar2` | IN | `null` | Input for `get_annuity_schedule` processing; semantics require caller/domain confirmation. |
| `p_annuity_amount` | `number` | IN | `null` | Input for `get_annuity_schedule` processing; semantics require caller/domain confirmation. |
| `p_max_annuity_amount` | `number` | IN | `null` | Input for `get_annuity_schedule` processing; semantics require caller/domain confirmation. |
| `p_remain_int_amount` | `number` | IN | `0` | Input for `get_annuity_schedule` processing; semantics require caller/domain confirmation. |
| `p_work_days` | `varchar2` | IN | `'Y'` | Input for `get_annuity_schedule` processing; semantics require caller/domain confirmation. |
| `p_own_annuity` | `varchar2` | IN | `'N'` | Input for `get_annuity_schedule` processing; semantics require caller/domain confirmation. |
| `p_calc_int_in_grace` | `varchar2` | IN | `'Y'` | Input for `get_annuity_schedule` processing; semantics require caller/domain confirmation. |
| `p_is_mortgage` | `varchar2` | IN | `'N'` | Input for `get_annuity_schedule` processing; semantics require caller/domain confirmation. |
| `p_max_iteration` | `number` | IN | `null` | Input for `get_annuity_schedule` processing; semantics require caller/domain confirmation. |
| `p_rest_main_pay_amount` | `number` | IN | `null` | Input for `get_annuity_schedule` processing; semantics require caller/domain confirmation. |
| `p_rest_main_pay_months` | `number` | IN | `null` | Input for `get_annuity_schedule` processing; semantics require caller/domain confirmation. |
| `p_loan_flow_rate_tab` | `LOAN_FLOW_RATE_TAB` | IN | `null` | Input for `get_annuity_schedule` processing; semantics require caller/domain confirmation. |
| `p_loan_stop_rate_tab` | `LOAN_STOP_RATE_TAB` | IN | `null` | Input for `get_annuity_schedule` processing; semantics require caller/domain confirmation. |
| `p_special_dates` | `loan_special_dates_tab` | IN | `null` | Input for `get_annuity_schedule` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `SCHEDULE_TT`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| Direct SQL | None identified; called routines may perform data access. |

**Error Handling**

- No explicit error handler or raised application message identified within this method segment. Propagated exceptions from dependencies remain possible.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_annuity_schedule(...);
```

**Technical Notes**

- **Verified from Source:** 139 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-special-schedule"></a>
### get_special_schedule

**Type:** PROCEDURE  
**Source:** specification line 583; implementation begins at body line 10837.

**Purpose**

Implements **get_special_schedule** for the payment schedules and dates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `ODEME_PLAN_TMP2`; updates `ODEME_PLAN_TMP2`
2. **Invoked external or qualified routines (static call references):** `GLBL_FAIZ.DAY_COUNT_BASIS_NEW`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `When Nvl(o.Anapara_Org, 0) + coalesce(o.Cemi_Org, 0) = 0 Then`
   - `If l_annuity_amount Is Null Then`
   - `When Others Then`
   - `If t.Anapara_Ode_Tar <> l_date Then`
   - `if t.rn = 1 and nvl(p_remain_int_amount, 0) > 0 then`
   - `if t.is_int_grace_payment = 'X' then`
   - `elsif t.is_int_grace_payment = 'Y' then`
   - `if p_calc_int_int_grace = 'N' then`
   - `If Nvl(t.Anapara_Org, 0) = 0 Or Nvl(t.Cemi_Org, 0) <> 0 Then`
   - `if t.is_main_grace_payment in ('X', 'Y') then`

**Business Rules**

Verified from source:
- Conditional expression: `When Nvl(o.Anapara_Org, 0) + coalesce(o.Cemi_Org, 0) = 0 Then`
- Conditional expression: `If l_annuity_amount Is Null Then`
- Conditional expression: `When Others Then`
- Conditional expression: `If t.Anapara_Ode_Tar <> l_date Then`
- Conditional expression: `if t.rn = 1 and nvl(p_remain_int_amount, 0) > 0 then`
- Conditional expression: `if t.is_int_grace_payment = 'X' then`
- Conditional expression: `elsif t.is_int_grace_payment = 'Y' then`
- Conditional expression: `if p_calc_int_int_grace = 'N' then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

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

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_doc_no` | `Varchar2` | IN | — | Input for `get_special_schedule` processing; semantics require caller/domain confirmation. |
| `p_begin_date` | `Date` | IN | `Glbl.Getsysdate` | Input for `get_special_schedule` processing; semantics require caller/domain confirmation. |
| `p_offer_amount` | `Number` | IN | — | Input for `get_special_schedule` processing; semantics require caller/domain confirmation. |
| `p_int_ratio` | `Number` | IN | — | Input for `get_special_schedule` processing; semantics require caller/domain confirmation. |
| `p_int_calc_type` | `varchar2` | IN | — | Input for `get_special_schedule` processing; semantics require caller/domain confirmation. |
| `p_calc_int_int_grace` | `varchar2` | IN | — | Input for `get_special_schedule` processing; semantics require caller/domain confirmation. |
| `p_annuity_amount` | `Number` | IN | `Null` | Input for `get_special_schedule` processing; semantics require caller/domain confirmation. |
| `p_remain_int_amount` | `number` | IN | `0` | Input for `get_special_schedule` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `ODEME_PLAN_TMP2` |
| UPDATE | `ODEME_PLAN_TMP2` |

Qualified procedure/function references: `GLBL_FAIZ.DAY_COUNT_BASIS_NEW`.

**Error Handling**

- Source excerpt: `When Others Then l_annuity_amount := l_remain_amount * (1 + p_int_ratio) / l_main_pay_months;`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- Direct DML detected: UPDATE.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_special_schedule(...);
```

**Technical Notes**

- **Verified from Source:** 157 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-created-schedule"></a>
### get_created_schedule

**Type:** PROCEDURE  
**Source:** specification line 592; implementation begins at body line 10993.

**Purpose**

Implements **get_created_schedule** for the payment schedules and dates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `CREATE_SCHEDULE_PARAMETRS`
2. **Invoked external or qualified routines (static call references):** `APEX_JSON.GET_COUNT`, `APEX_JSON.GET_DATE`, `APEX_JSON.GET_NUMBER`, `APEX_JSON.PARSE`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `WHEN NO_DATA_FOUND THEN`
   - `IF l_cschep.loan_flow_rate_tab IS NOT NULL THEN`
   - `IF l_cschep.loan_stop_rate_tab IS NOT NULL THEN`

**Business Rules**

Verified from source:
- Conditional expression: `WHEN NO_DATA_FOUND THEN`
- Conditional expression: `IF l_cschep.loan_flow_rate_tab IS NOT NULL THEN`
- Conditional expression: `IF l_cschep.loan_stop_rate_tab IS NOT NULL THEN`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
Procedure get_created_schedule(p_fid number);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_fid` | `number` | IN | — | Input for `get_created_schedule` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `CREATE_SCHEDULE_PARAMETRS` |

Qualified procedure/function references: `APEX_JSON.GET_COUNT`, `APEX_JSON.GET_DATE`, `APEX_JSON.GET_NUMBER`, `APEX_JSON.PARSE`.

**Error Handling**

- Source excerpt: `WHEN NO_DATA_FOUND THEN R('No record found for fid = ' || p_fid); end;`
- Source excerpt: `R('No record found for fid = ' || p_fid); end; `
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_created_schedule(...);
```

**Technical Notes**

- **Verified from Source:** 88 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="create-schedule"></a>
### create_schedule

**Type:** PROCEDURE  
**Source:** specification line 595; implementation begins at body line 11080.

**Purpose**

Implements **create_schedule** for the payment schedules and dates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** No direct SQL table access identified in the method segment.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `when nvl(p_annuity_amount, 0) > 0 then`
   - `when nvl(p_max_annuity_amount, 0) > 0 then`

**Business Rules**

Verified from source:
- Conditional expression: `when nvl(p_annuity_amount, 0) > 0 then`
- Conditional expression: `when nvl(p_max_annuity_amount, 0) > 0 then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

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

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_schedule_no` | `number` | IN | — | Input for `create_schedule` processing; semantics require caller/domain confirmation. |
| `p_coll_name` | `varchar2` | IN | `null` | Input for `create_schedule` processing; semantics require caller/domain confirmation. |
| `p_fk_id` | `number` | IN | `null` | Input for `create_schedule` processing; semantics require caller/domain confirmation. |
| `p_doc_no` | `varchar2` | IN | `'XXX'` | Input for `create_schedule` processing; semantics require caller/domain confirmation. |
| `p_memorandum_id` | `varchar2` | IN | `null` | Input for `create_schedule` processing; semantics require caller/domain confirmation. |
| `p_customer_no` | `number` | IN | `null` | Input for `create_schedule` processing; semantics require caller/domain confirmation. |
| `p_tx_fid` | `number` | IN | `null` | Input for `create_schedule` processing; semantics require caller/domain confirmation. |
| `p_begin_date` | `date` | IN | `glbl.getsysdate` | Input for `create_schedule` processing; semantics require caller/domain confirmation. |
| `p_last_int_Calc_Date` | `date` | IN | `glbl.getsysdate - 1` | Input for `create_schedule` processing; semantics require caller/domain confirmation. |
| `p_main_pymt_date` | `date` | IN | — | Input for `create_schedule` processing; semantics require caller/domain confirmation. |
| `p_int_pymt_date` | `date` | IN | — | Input for `create_schedule` processing; semantics require caller/domain confirmation. |
| `p_pymt_day` | `number` | IN | `null` | Input for `create_schedule` processing; semantics require caller/domain confirmation. |
| `p_end_date` | `date` | IN | — | Input for `create_schedule` processing; semantics require caller/domain confirmation. |
| `p_offer_amount` | `number` | IN | — | Input for `create_schedule` processing; semantics require caller/domain confirmation. |
| `p_ovd_main_amount` | `number` | IN | `0` | Input for `create_schedule` processing; semantics require caller/domain confirmation. |
| `p_int_ratio` | `number` | IN | — | Input for `create_schedule` processing; semantics require caller/domain confirmation. |
| `p_int_calc_type` | `varchar2` | IN | — | Input for `create_schedule` processing; semantics require caller/domain confirmation. |
| `p_annuity_amount` | `number` | IN | `null` | Input for `create_schedule` processing; semantics require caller/domain confirmation. |
| `p_max_annuity_amount` | `number` | IN | `null` | Input for `create_schedule` processing; semantics require caller/domain confirmation. |
| `p_min_main_pay_amount` | `number` | IN | `null` | Input for `create_schedule` processing; semantics require caller/domain confirmation. |
| `p_remain_int_amount` | `number` | IN | `0` | Input for `create_schedule` processing; semantics require caller/domain confirmation. |
| `p_main_grace_period` | `varchar2` | IN | `null` | Input for `create_schedule` processing; semantics require caller/domain confirmation. |
| `p_int_grace_period` | `varchar2` | IN | `null` | Input for `create_schedule` processing; semantics require caller/domain confirmation. |
| `p_main_pymt_period` | `number` | IN | `1` | Input for `create_schedule` processing; semantics require caller/domain confirmation. |
| `p_int_pymt_period` | `number` | IN | `1` | Input for `create_schedule` processing; semantics require caller/domain confirmation. |
| `p_product_code` | `number` | IN | `null` | Input for `create_schedule` processing; semantics require caller/domain confirmation. |
| `p_same_annuity` | `varchar2` | IN | `'N'` | Input for `create_schedule` processing; semantics require caller/domain confirmation. |
| `p_calc_int_in_grace` | `varchar2` | IN | `'Y'` | Input for `create_schedule` processing; semantics require caller/domain confirmation. |
| `p_return_type` | `varchar2` | IN | `'NO_ZERO'` | Input for `create_schedule` processing; semantics require caller/domain confirmation. |
| `p_rest_main_pay_amount` | `number` | IN | `null` | Input for `create_schedule` processing; semantics require caller/domain confirmation. |
| `p_rest_main_pay_months` | `number` | IN | `null` | Input for `create_schedule` processing; semantics require caller/domain confirmation. |
| `p_loan_flow_rate_tab` | `LOAN_FLOW_RATE_TAB` | IN | `null` | Input for `create_schedule` processing; semantics require caller/domain confirmation. |
| `p_loan_stop_rate_tab` | `LOAN_STOP_RATE_TAB` | IN | `null` | Input for `create_schedule` processing; semantics require caller/domain confirmation. |
| `p_special_dates` | `loan_special_dates_tab` | IN | `null` | Input for `create_schedule` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| Direct SQL | None identified; called routines may perform data access. |

**Error Handling**

- No explicit error handler or raised application message identified within this method segment. Propagated exceptions from dependencies remain possible.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.create_schedule(...);
```

**Technical Notes**

- **Verified from Source:** 90 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="update-payment-plan"></a>
### UPDATE_PAYMENT_PLAN

**Type:** PROCEDURE  
**Source:** specification line 642; implementation begins at body line 12375.

**Purpose**

Implements **UPDATE_PAYMENT_PLAN** for the payment schedules and dates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `GAIA.KRD_TEKLIF_DETAY`, `IBS.ONLINE_CRD_BLOCK`, `LOAN_TEMPORARY_PAYMENT_PLAN`, `ODEME_PLAN_TMP`; inserts into `LOAN_PAYMENT_PLAN`, `LOAN_TEMPORARY_PAYMENT_PLAN`; updates `GAIA.KRD_TEKLIF_DETAY`, `GAIA.KRD_TESIS`, `IBS.ONLINE_CRD_BLOCK`, `PAYMENT`
2. **Invoked external or qualified routines (static call references):** `API_CALENDAR.GET_WORK_DAY`, `GAIA.R`, `LOAN_API.ADD_MONTHS_FOR_LOAN`, `LOAN_API.CREATE_LOAN_HISTORY`, `LOAN_API.CREATE_SCHEDULE`, `LOAN_API.FINALIZE_ADDTIONAL_PROCESS`, `LOAN_API.GET_ACC_TYPE_BY_STATUS`, `LOAN_API.GET_PLAN_ERROR`, `LOAN_API.TABLE_LOG_OPERATION`, `TRN_BROKER.REGISTER_EOD`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `IF L_KREDIT_KHAT ='KR' THEN`
   - `/*case when  TO_CHAR(gaia.loan_api.Add_Months_for_loan(l_begin_date+1,59) ,'DY', 'NLS_DATE_LANGUAGE=ENGLISH')='SUN'`
   - `ibs.api_calendar.get_work_day(case when TO_CHAR(gaia.loan_api.add_months_for_loan(l_begin_date+1,`
   - `if g_ktd.with_tranche_info_yn = 'Y' then`
   - `r('This operation cannot be initialized when [with_tranche_info_yn] = ''Y''');`
   - `l_end_date:=ibs.api_calendar.get_work_day(case when TO_CHAR(gaia.loan_api.add_months_for_loan(l_begin_date+1,`
   - `if l_err_desc is not null then`
   - `when others then`

**Business Rules**

Verified from source:
- Conditional expression: `IF L_KREDIT_KHAT ='KR' THEN`
- Conditional expression: `/*case when  TO_CHAR(gaia.loan_api.Add_Months_for_loan(l_begin_date+1,59) ,'DY', 'NLS_DATE_LANGUAGE=ENGLISH')='SUN'`
- Conditional expression: `ibs.api_calendar.get_work_day(case when TO_CHAR(gaia.loan_api.add_months_for_loan(l_begin_date+1,`
- Conditional expression: `if g_ktd.with_tranche_info_yn = 'Y' then`
- Conditional expression: `r('This operation cannot be initialized when [with_tranche_info_yn] = ''Y''');`
- Conditional expression: `l_end_date:=ibs.api_calendar.get_work_day(case when TO_CHAR(gaia.loan_api.add_months_for_loan(l_begin_date+1,`
- Conditional expression: `if l_err_desc is not null then`
- Conditional expression: `when others then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
PROCEDURE UPDATE_PAYMENT_PLAN(
                              P_DOC_NO             varchar2);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `P_DOC_NO` | `varchar2` | IN | — | Input for `UPDATE_PAYMENT_PLAN` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `GAIA.KRD_TEKLIF_DETAY`, `IBS.ONLINE_CRD_BLOCK`, `LOAN_TEMPORARY_PAYMENT_PLAN`, `ODEME_PLAN_TMP` |
| INSERT | `LOAN_PAYMENT_PLAN`, `LOAN_TEMPORARY_PAYMENT_PLAN` |
| UPDATE | `GAIA.KRD_TEKLIF_DETAY`, `GAIA.KRD_TESIS`, `IBS.ONLINE_CRD_BLOCK`, `PAYMENT` |

Qualified procedure/function references: `API_CALENDAR.GET_WORK_DAY`, `GAIA.R`, `LOAN_API.ADD_MONTHS_FOR_LOAN`, `LOAN_API.CREATE_LOAN_HISTORY`, `LOAN_API.CREATE_SCHEDULE`, `LOAN_API.FINALIZE_ADDTIONAL_PROCESS`, `LOAN_API.GET_ACC_TYPE_BY_STATUS`, `LOAN_API.GET_PLAN_ERROR`, `LOAN_API.TABLE_LOG_OPERATION`, `TRN_BROKER.REGISTER_EOD`.

**Error Handling**

- Source excerpt: `r('This operation cannot be initialized when [with_tranche_info_yn] = ''Y'''); end if; `
- Source excerpt: `gaia.r(l_err_desc); end if; `
- Source excerpt: `when others then  r('Update payment plan block -> ' || sqlerrm || ' - ' || dbms_utility.format_error_backtrace);`
- Source excerpt: `r('Update payment plan block -> ' || sqlerrm || ' - ' || dbms_utility.format_error_backtrace); END;--Nicat `
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- Direct DML detected: INSERT, UPDATE.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.UPDATE_PAYMENT_PLAN(...);
```

**Technical Notes**

- **Verified from Source:** 212 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

## Interest, penalties and rates

<a id="get-amount-for-pen-calc-1"></a>
### get_amount_for_pen_calc — overload 1

**Type:** FUNCTION  
**Source:** specification line 87; implementation begins at body line 332.

**Purpose**

Implements **get_amount_for_pen_calc** for the interest, penalties and rates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `KRD_GUARANTEE_MAIN`, `LOAN_ACC_TYPES_PR`, `LOAN_PAYMENT_PLAN`
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if p_is_pen_calc_on_int = 'Y' then`
   - `if l_ovd_int_amount < 0 or p_ovd_balance < 0 then`
   - `if p_is_exclude_coll_amount = 'Y' then`
   - `if (p_is_pen_calc_on_int = 'Y' or p_date >= p_loan_end_date) and`
   - `if l_plan_type not in ('MAIN', 'INT') then`
   - `when w.acc_type_group in`
   - `when w.acc_type_group in`
   - `when l_plan_type = 'MAIN' then`
   - `when l_plan_type = 'INT' then`
   - `when l_plan_type = 'MAIN' then`

**Business Rules**

Verified from source:
- Conditional expression: `if p_is_pen_calc_on_int = 'Y' then`
- Conditional expression: `if l_ovd_int_amount < 0 or p_ovd_balance < 0 then`
- Conditional expression: `if p_is_exclude_coll_amount = 'Y' then`
- Conditional expression: `if (p_is_pen_calc_on_int = 'Y' or p_date >= p_loan_end_date) and`
- Conditional expression: `if l_plan_type not in ('MAIN', 'INT') then`
- Conditional expression: `when w.acc_type_group in`
- Conditional expression: `when w.acc_type_group in`
- Conditional expression: `when l_plan_type = 'MAIN' then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

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

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_date` | `date` | IN | — | Input for `get_amount_for_pen_calc` processing; semantics require caller/domain confirmation. |
| `p_doc_no` | `varchar2` | IN | — | Input for `get_amount_for_pen_calc` processing; semantics require caller/domain confirmation. |
| `p_ovd_balance` | `number` | IN | — | Input for `get_amount_for_pen_calc` processing; semantics require caller/domain confirmation. |
| `p_is_pen_calc_on_int` | `varchar2` | IN | — | Input for `get_amount_for_pen_calc` processing; semantics require caller/domain confirmation. |
| `p_is_exclude_coll_amount` | `varchar2` | IN | — | Input for `get_amount_for_pen_calc` processing; semantics require caller/domain confirmation. |
| `p_overdue_min_amount_main` | `number` | IN | — | Input for `get_amount_for_pen_calc` processing; semantics require caller/domain confirmation. |
| `p_loan_end_date` | `date` | IN | — | Input for `get_amount_for_pen_calc` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `number`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `KRD_GUARANTEE_MAIN`, `LOAN_ACC_TYPES_PR`, `LOAN_PAYMENT_PLAN` |

**Error Handling**

- Source excerpt: `r(p_text => 'Overdue int in plan or ovd_balance amount for penalty calculation is negative!'); end if; `
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_amount_for_pen_calc(...);
```

**Technical Notes**

- **Verified from Source:** 305 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-interest-calc-info"></a>
### get_interest_calc_info

**Type:** PROCEDURE  
**Source:** specification line 115; implementation begins at body line 1374.

**Purpose**

Implements **get_interest_calc_info** for the interest, penalties and rates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `LOAN_INT_CALC_TYPES_PR`
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if p_pymt_day is null then`
   - `if p_trn_date > l_last_calc_date then`
   - `when others then`
   - `when 'ACT' then`
   - `if l_i.month_day_count = '30' then`
   - `if to_char(l_last_calc_date, 'DD') = l_i.month_day_count then`
   - `if p_trn_date + 1 = last_day(p_trn_date) then`
   - `elsif p_trn_date = last_day(p_trn_date) then`
   - `elsif p_trn_date < l_last_calc_date then`

**Business Rules**

Verified from source:
- Conditional expression: `if p_pymt_day is null then`
- Conditional expression: `if p_trn_date > l_last_calc_date then`
- Conditional expression: `when others then`
- Conditional expression: `when 'ACT' then`
- Conditional expression: `if l_i.month_day_count = '30' then`
- Conditional expression: `if to_char(l_last_calc_date, 'DD') = l_i.month_day_count then`
- Conditional expression: `if p_trn_date + 1 = last_day(p_trn_date) then`
- Conditional expression: `elsif p_trn_date = last_day(p_trn_date) then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

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

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_last_calc_date` | `date` | IN | — | Input for `get_interest_calc_info` processing; semantics require caller/domain confirmation. |
| `p_pymt_day` | `number` | IN | — | Input for `get_interest_calc_info` processing; semantics require caller/domain confirmation. |
| `p_trn_date` | `date` | IN | — | Input for `get_interest_calc_info` processing; semantics require caller/domain confirmation. |
| `p_int_calc_type` | `varchar2` | IN | — | Input for `get_interest_calc_info` processing; semantics require caller/domain confirmation. |
| `p_rate_type` | `varchar2` | IN | — | Input for `get_interest_calc_info` processing; semantics require caller/domain confirmation. |
| `p_int_rate_periodicity` | `varchar2` | IN | — | Input for `get_interest_calc_info` processing; semantics require caller/domain confirmation. |
| `p_calc_day_count` | `number` | OUT | — | Output produced by the method. |
| `p_year_day_count` | `number` | OUT | — | Output produced by the method. |

**Return Value / Outputs**

OUT/IN OUT parameters: `p_calc_day_count`, `p_year_day_count`.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `LOAN_INT_CALC_TYPES_PR` |

**Error Handling**

- Source excerpt: `r(p_text => 'Payment day cant be null, please check!'); end if; if p_trn_date > l_last_calc_date then`
- Source excerpt: `when others then r(p_text => 'error encountered in search of interest calculation type: ' || p_int_calc_type);`
- Source excerpt: `r(p_text => 'error encountered in search of interest calculation type: ' || p_int_calc_type); end;`
- Source excerpt: `r(p_text => 'Transaction date cant be less than last calculation date!'); end if; `
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_interest_calc_info(...);
```

**Technical Notes**

- **Verified from Source:** 79 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-interest-calc-dates"></a>
### get_interest_calc_dates

**Type:** FUNCTION  
**Source:** specification line 124; implementation begins at body line 1452.

**Purpose**

Implements **get_interest_calc_dates** for the interest, penalties and rates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** No direct SQL table access identified in the method segment.
2. **Invoked external or qualified routines (static call references):** `GLBL_TARIH.AYBASI`, `GLBL_TARIH.SONRAKI_ISGUNU`, `LOAN_API.G_DATE_TAB_TYPE`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if l_int_calc_at not in ('EOD', 'SOD') then`
   - `if l_eod_sod not in ('E', 'S') then`
   - `if l_int_calc_at = 'EOD' then`
   - `if l_eod_sod = 'S' and GLBL_TARIH.AYBASI(l_sysdate) = l_sysdate AND`
   - `elsif l_int_calc_at = 'SOD' then`
   - `if GLBL_TARIH.AYBASI(l_sysdate) = l_sysdate AND`
   - `exit when l_last_calc_access_date >= l_first_date;`
   - `exit when l_first_date >= l_last_date;`

**Business Rules**

Verified from source:
- Conditional expression: `if l_int_calc_at not in ('EOD', 'SOD') then`
- Conditional expression: `if l_eod_sod not in ('E', 'S') then`
- Conditional expression: `if l_int_calc_at = 'EOD' then`
- Conditional expression: `if l_eod_sod = 'S' and GLBL_TARIH.AYBASI(l_sysdate) = l_sysdate AND`
- Conditional expression: `elsif l_int_calc_at = 'SOD' then`
- Conditional expression: `if GLBL_TARIH.AYBASI(l_sysdate) = l_sysdate AND`
- Conditional expression: `exit when l_last_calc_access_date >= l_first_date;`
- Conditional expression: `exit when l_first_date >= l_last_date;`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
function get_interest_calc_dates(p_last_calc_access_date in date,
                                   p_eod_sod               in varchar2,
                                   p_int_calc_at           in varchar2)
    return loan_api.g_date_tab_type;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_last_calc_access_date` | `date` | IN | — | Input for `get_interest_calc_dates` processing; semantics require caller/domain confirmation. |
| `p_eod_sod` | `varchar2` | IN | — | Input for `get_interest_calc_dates` processing; semantics require caller/domain confirmation. |
| `p_int_calc_at` | `varchar2` | IN | — | Input for `get_interest_calc_dates` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `loan_api.g_date_tab_type`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| Direct SQL | None identified; called routines may perform data access. |

Qualified procedure/function references: `GLBL_TARIH.AYBASI`, `GLBL_TARIH.SONRAKI_ISGUNU`, `LOAN_API.G_DATE_TAB_TYPE`.

**Error Handling**

- Source excerpt: `r(p_text => 'p_int_calc_at param should be EOD or SOD!!'); end if; `
- Source excerpt: `r(p_text => 'P_EOD_SOD param should be E - EOD or S - SOD!!'); end if; -- int calculation in eod`
- Source excerpt: `r(p_text => 'Interest calculation should be done at EOD or SOD!!'); end if; `
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_interest_calc_dates(...);
```

**Technical Notes**

- **Verified from Source:** 65 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-interest-calc-dates-ex"></a>
### get_interest_calc_dates_ex

**Type:** FUNCTION  
**Source:** specification line 129; implementation begins at body line 1516.

**Purpose**

Implements **get_interest_calc_dates_ex** for the interest, penalties and rates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** No direct SQL table access identified in the method segment.
2. **Invoked external or qualified routines (static call references):** `GLBL_TARIH.AYBASI`, `GLBL_TARIH.SONRAKI_ISGUNU`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if l_int_calc_at not in ('EOD', 'SOD') then`
   - `if l_eod_sod not in ('E', 'S') then`
   - `if l_int_calc_at = 'EOD' then`
   - `if l_eod_sod = 'S' and GLBL_TARIH.AYBASI(l_sysdate) = l_sysdate AND`
   - `elsif l_int_calc_at = 'SOD' then`
   - `if GLBL_TARIH.AYBASI(l_sysdate) = l_sysdate AND`
   - `exit when l_first_date >= l_last_date;`

**Business Rules**

Verified from source:
- Conditional expression: `if l_int_calc_at not in ('EOD', 'SOD') then`
- Conditional expression: `if l_eod_sod not in ('E', 'S') then`
- Conditional expression: `if l_int_calc_at = 'EOD' then`
- Conditional expression: `if l_eod_sod = 'S' and GLBL_TARIH.AYBASI(l_sysdate) = l_sysdate AND`
- Conditional expression: `elsif l_int_calc_at = 'SOD' then`
- Conditional expression: `if GLBL_TARIH.AYBASI(l_sysdate) = l_sysdate AND`
- Conditional expression: `exit when l_first_date >= l_last_date;`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
function get_interest_calc_dates_ex(p_date        in date,
                                      p_eod_sod     in varchar2,
                                      p_int_calc_at in varchar2)
    return g_date_tab_type;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_date` | `date` | IN | — | Input for `get_interest_calc_dates_ex` processing; semantics require caller/domain confirmation. |
| `p_eod_sod` | `varchar2` | IN | — | Input for `get_interest_calc_dates_ex` processing; semantics require caller/domain confirmation. |
| `p_int_calc_at` | `varchar2` | IN | — | Input for `get_interest_calc_dates_ex` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `g_date_tab_type`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| Direct SQL | None identified; called routines may perform data access. |

Qualified procedure/function references: `GLBL_TARIH.AYBASI`, `GLBL_TARIH.SONRAKI_ISGUNU`.

**Error Handling**

- Source excerpt: `r(p_text => 'p_int_calc_at param should be EOD or SOD!!'); end if; `
- Source excerpt: `r(p_text => 'P_EOD_SOD param should be E - EOD or S - SOD!!'); end if; -- int calculation in eod`
- Source excerpt: `r(p_text => 'Interest calculation should be done at EOD or SOD!!'); end if; loop`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_interest_calc_dates_ex(...);
```

**Technical Notes**

- **Verified from Source:** 55 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="do-delete-operation"></a>
### do_delete_operation

**Type:** PROCEDURE  
**Source:** specification line 166; implementation begins at body line 2109.

**Purpose**

Implements **do_delete_operation** for the interest, penalties and rates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `GL_JOURNAL_LINES`, `LOAN_OPERATION_HISTORY`; updates `GLBL_TRANSACTION`
2. **Invoked external or qualified routines (static call references):** `KRD_EOD.TERS_FIS_KES`, `LOAN_API.CREATE_LOAN_HISTORY`, `LOAN_API.DO_PLAN_CONTROL`, `LOAN_API.REVERSE_UPDATE`, `LOAN_TRANCHE_API.DO_DELETE_OPERATION`, `MM_ACCOUNTING#.FIS_SIL`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `when others then`
   - `if l_oper_type not in ('COURT_DECISION') then`
   - `if l_count > 0 then`
   - `if l_trn_date = l_date then`
   - `if l_oper_type != 'OVD_AMOUNT_CORRECTION' and p_plan_control = 'Y' then`

**Business Rules**

Verified from source:
- Conditional expression: `when others then`
- Conditional expression: `if l_oper_type not in ('COURT_DECISION') then`
- Conditional expression: `if l_count > 0 then`
- Conditional expression: `if l_trn_date = l_date then`
- Conditional expression: `if l_oper_type != 'OVD_AMOUNT_CORRECTION' and p_plan_control = 'Y' then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
procedure do_delete_operation(p_tx_fid       number,
                                p_date_control varchar2 default 'Y',
                                p_plan_control varchar2 default 'Y');
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_tx_fid` | `number` | IN | — | Input for `do_delete_operation` processing; semantics require caller/domain confirmation. |
| `p_date_control` | `varchar2` | IN | `'Y'` | Input for `do_delete_operation` processing; semantics require caller/domain confirmation. |
| `p_plan_control` | `varchar2` | IN | `'Y'` | Input for `do_delete_operation` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `GL_JOURNAL_LINES`, `LOAN_OPERATION_HISTORY` |
| UPDATE | `GLBL_TRANSACTION` |

Qualified procedure/function references: `KRD_EOD.TERS_FIS_KES`, `LOAN_API.CREATE_LOAN_HISTORY`, `LOAN_API.DO_PLAN_CONTROL`, `LOAN_API.REVERSE_UPDATE`, `LOAN_TRANCHE_API.DO_DELETE_OPERATION`, `MM_ACCOUNTING#.FIS_SIL`.

**Error Handling**

- Source excerpt: `when others then r('Can not get additional info in [loan_operation_history] with tx fid [' || p_Tx_fid || '] {l_date: ' || l_date || '}');`
- Source excerpt: `r('Can not get additional info in [loan_operation_history] with tx fid [' || p_Tx_fid || '] {l_date: ' || l_date || '}'); end;`
- Source excerpt: `r('Not declared delete operation [' || p_tx_fid || ']'); end if; `
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- Direct DML detected: UPDATE.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.do_delete_operation(...);
```

**Technical Notes**

- **Verified from Source:** 69 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-basis-year-days-cnt"></a>
### get_basis_year_days_cnt

**Type:** FUNCTION  
**Source:** specification line 196; implementation begins at body line 2523.

**Purpose**

Implements **get_basis_year_days_cnt** for the interest, penalties and rates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `LOAN_INT_CALC_TYPES_PR`
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `when others then`
   - `when 'ACT' then`

**Business Rules**

Verified from source:
- Conditional expression: `when others then`
- Conditional expression: `when 'ACT' then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
function get_basis_year_days_cnt(p_int_calc_type in varchar2,
                                   p_date          in date) return number;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_int_calc_type` | `varchar2` | IN | — | Input for `get_basis_year_days_cnt` processing; semantics require caller/domain confirmation. |
| `p_date` | `date` | IN | — | Input for `get_basis_year_days_cnt` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `number`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `LOAN_INT_CALC_TYPES_PR` |

**Error Handling**

- Source excerpt: `when others then r(p_text => 'Error encountered in search of int calc type ' || p_int_calc_type || ' in loan_int_calc_types_pr table!');`
- Source excerpt: `r(p_text => 'Error encountered in search of int calc type ' || p_int_calc_type || ' in loan_int_calc_types_pr table!'); end;`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_basis_year_days_cnt(...);
```

**Technical Notes**

- **Verified from Source:** 29 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="loan-int-diff-operation"></a>
### loan_int_diff_operation

**Type:** PROCEDURE  
**Source:** specification line 201; implementation begins at body line 2573.

**Purpose**

Implements **loan_int_diff_operation** for the interest, penalties and rates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `LOAN_INT_CALCULATION_DIFF_HISTORY`; inserts into `LOAN_INT_CALCULATION_DIFF_HISTORY`; updates `LOAN_INT_CALCULATION_DIFF_HISTORY`; deletes from `LOAN_INT_CALCULATION_DIFF_HISTORY`
2. **Invoked external or qualified routines (static call references):** `GLBL.TO_NUMBER#`, `LOAN_API.GET_GL_VALUE`, `LOAN_API.LOAN_INT_DIFF_OPERATION`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if p_tx_fid is null or p_doc_no is null or p_acc_type is null or`
   - `if p_trn_type = 'INS' then`
   - `if trunc(l_sum_residual_amount + l_residual_amount, 2) > 0 or`
   - `if p_payment_date is not null then`
   - `if p_source_acc_type in ('MAIN', 'NPL_MAIN') and`
   - `if abs(l_diff_amount) between l_min_diff_Amount and`
   - `if p_original_amount < 0 or l_residual_amount < 0 or`
   - `if nvl(p_original_amount, 0) + nvl(l_residual_amount, 0) +`
   - `case when p_payment_date is not null then 1 else null end,`
   - `elsif p_trn_type = 'OPEN' then`

**Business Rules**

Verified from source:
- Conditional expression: `if p_tx_fid is null or p_doc_no is null or p_acc_type is null or`
- Conditional expression: `if p_trn_type = 'INS' then`
- Conditional expression: `if trunc(l_sum_residual_amount + l_residual_amount, 2) > 0 or`
- Conditional expression: `if p_payment_date is not null then`
- Conditional expression: `if p_source_acc_type in ('MAIN', 'NPL_MAIN') and`
- Conditional expression: `if abs(l_diff_amount) between l_min_diff_Amount and`
- Conditional expression: `if p_original_amount < 0 or l_residual_amount < 0 or`
- Conditional expression: `if nvl(p_original_amount, 0) + nvl(l_residual_amount, 0) +`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

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

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_trn_date` | `date` | IN | — | Input for `loan_int_diff_operation` processing; semantics require caller/domain confirmation. |
| `p_oper_type` | `varchar2` | IN | — | Input for `loan_int_diff_operation` processing; semantics require caller/domain confirmation. |
| `p_trn_type` | `varchar2` | IN | — | Input for `loan_int_diff_operation` processing; semantics require caller/domain confirmation. |
| `p_doc_no` | `varchar2` | IN | — | Input for `loan_int_diff_operation` processing; semantics require caller/domain confirmation. |
| `p_acc_type` | `varchar2` | IN | — | Input for `loan_int_diff_operation` processing; semantics require caller/domain confirmation. |
| `p_source_acc_type` | `varchar2` | IN | — | Input for `loan_int_diff_operation` processing; semantics require caller/domain confirmation. |
| `p_tx_fid` | `number` | IN | — | Input for `loan_int_diff_operation` processing; semantics require caller/domain confirmation. |
| `p_original_amount` | `number` | IN | — | Input for `loan_int_diff_operation` processing; semantics require caller/domain confirmation. |
| `p_eod_sod` | `varchar2` | IN | — | Input for `loan_int_diff_operation` processing; semantics require caller/domain confirmation. |
| `p_payment_date` | `date` | IN | — | Input for `loan_int_diff_operation` processing; semantics require caller/domain confirmation. |
| `p_plan_int_amount` | `number` | IN | — | Input for `loan_int_diff_operation` processing; semantics require caller/domain confirmation. |
| `p_int_amount` | `number` | IN | — | Input for `loan_int_diff_operation` processing; semantics require caller/domain confirmation. |
| `p_calc_amount` | `number` | OUT | — | Output produced by the method. |

**Return Value / Outputs**

OUT/IN OUT parameters: `p_calc_amount`.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `LOAN_INT_CALCULATION_DIFF_HISTORY` |
| INSERT | `LOAN_INT_CALCULATION_DIFF_HISTORY` |
| UPDATE | `LOAN_INT_CALCULATION_DIFF_HISTORY` |
| DELETE | `LOAN_INT_CALCULATION_DIFF_HISTORY` |

Qualified procedure/function references: `GLBL.TO_NUMBER#`, `LOAN_API.GET_GL_VALUE`, `LOAN_API.LOAN_INT_DIFF_OPERATION`.

**Error Handling**

- Source excerpt: `r(p_text => 'p_tx_fid or p_doc_no or p_acc_type or p_eod_sod cant be null!'); end if; if p_trn_type = 'INS' then`
- Source excerpt: `r(p_text => 'original_amount or residual_amount or calc_amount or sum_residual_amount or p_plan_int_amount or p_int_amount is negative'); end if;`
- Source excerpt: `r(p_text => 'Operation type must be INS, OPEN, CLOSE!'); end if; `
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- Direct DML detected: INSERT, UPDATE, DELETE.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.loan_int_diff_operation(...);
```

**Technical Notes**

- **Verified from Source:** 155 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-delay-int-rate"></a>
### Get_Delay_Int_Rate

**Type:** FUNCTION  
**Source:** specification line 225; implementation begins at body line 2937.

**Purpose**

Implements **Get_Delay_Int_Rate** for the interest, penalties and rates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `KRD_TEKLIF_DETAY`
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `When Others Then`

**Business Rules**

Verified from source:
- Conditional expression: `When Others Then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
Function Get_Delay_Int_Rate(p_Loan_Id    In Varchar2,
                              p_Delay_Type In Varchar2) Return Number;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_Loan_Id` | `Varchar2` | IN | — | Input for `Get_Delay_Int_Rate` processing; semantics require caller/domain confirmation. |
| `p_Delay_Type` | `Varchar2` | IN | — | Input for `Get_Delay_Int_Rate` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `Number`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `KRD_TEKLIF_DETAY` |

**Error Handling**

- Source excerpt: `When Others Then Return 0; End;`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.Get_Delay_Int_Rate(...);
```

**Technical Notes**

- **Verified from Source:** 27 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-amount-for-pen-calc-2"></a>
### get_amount_for_pen_calc — overload 2

**Type:** FUNCTION  
**Source:** specification line 266; implementation begins at body line 3175.

**Purpose**

Implements **get_amount_for_pen_calc** for the interest, penalties and rates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `LOAN_PAYMENT_PLAN`, `LOAN_SPECIAL_DAYS_PR`
2. **Invoked external or qualified routines (static call references):** `GLBL_FAIZ.DAY_COUNT_BASIS_NEW`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `when too_many_rows then`
   - `when others then`
   - `if p_for_spec_days = 'N' then`
   - `elsif p_for_spec_days = 'Y' then`

**Business Rules**

Verified from source:
- Conditional expression: `when too_many_rows then`
- Conditional expression: `when others then`
- Conditional expression: `if p_for_spec_days = 'N' then`
- Conditional expression: `elsif p_for_spec_days = 'Y' then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
Function get_amount_for_pen_calc(p_doc_no        In Varchar2,
                                   P_date          In Date,
                                   p_for_spec_days in varchar2 default 'N',
                                   p_int_calc_type in varchar2 default null)
    Return Number;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_doc_no` | `Varchar2` | IN | — | Input for `get_amount_for_pen_calc` processing; semantics require caller/domain confirmation. |
| `P_date` | `Date` | IN | — | Input for `get_amount_for_pen_calc` processing; semantics require caller/domain confirmation. |
| `p_for_spec_days` | `varchar2` | IN | `'N'` | Input for `get_amount_for_pen_calc` processing; semantics require caller/domain confirmation. |
| `p_int_calc_type` | `varchar2` | IN | `null` | Input for `get_amount_for_pen_calc` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `Number`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `LOAN_PAYMENT_PLAN`, `LOAN_SPECIAL_DAYS_PR` |

Qualified procedure/function references: `GLBL_FAIZ.DAY_COUNT_BASIS_NEW`.

**Error Handling**

- Source excerpt: `when too_many_rows then r(p_text => 'Too many rows in loan_special_days_pr for date: ' || p_date);`
- Source excerpt: `r(p_text => 'Too many rows in loan_special_days_pr for date: ' || p_date); when others then`
- Source excerpt: `when others then null; end;`
- Source excerpt: `r(p_text => 'p_for_spec_days must be Y or N!');  end if;`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_amount_for_pen_calc(...);
```

**Technical Notes**

- **Verified from Source:** 62 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="table-log-operation"></a>
### table_log_operation

**Type:** PROCEDURE  
**Source:** specification line 314; implementation begins at body line 4950.

**Purpose**

Implements **table_log_operation** for the interest, penalties and rates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `KRD_KOM_PLAN_DETAY`, `KRD_KOM_PLAN_DETAY_LOG`, `LOAN_CATEGORY`, `LOAN_CATEGORY_TEMP`, `LOAN_FLOW_RATIO_INFO`, `LOAN_FLOW_RATIO_INFO_LOG`, `LOAN_PAYMENT_PLAN`, `LOAN_PAYMENT_PLAN_LOG` and 2 more; inserts into `KRD_KOM_PLAN_DETAY`, `KRD_KOM_PLAN_DETAY_LOG`, `LOAN_CATEGORY`, `LOAN_CATEGORY_TEMP`, `LOAN_FLOW_RATIO_INFO`, `LOAN_FLOW_RATIO_INFO_LOG`, `LOAN_PAYMENT_PLAN`, `LOAN_PAYMENT_PLAN_LOG` and 2 more; updates `OPERATIONS.`; deletes from `KRD_KOM_PLAN_DETAY`, `KRD_KOM_PLAN_DETAY_LOG`, `LOAN_CATEGORY`, `LOAN_CATEGORY_TEMP`, `LOAN_FLOW_RATIO_INFO`, `LOAN_PAYMENT_PLAN`, `LOAN_STOP_RATIO_INFO`
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if p_tx_fid is null or p_doc_no is null then`
   - `if p_oper_type not in ('LOGGING', 'RESTORING') then`
   - `if p_oper_type = 'LOGGING' then`
   - `if nvl(g_additional_info_state, 'X') not in ('CLEAR', 'INIT') then`
   - `IF p_table_name = 'LOAN_PAYMENT_PLAN' then`
   - `if p_oper_type in ('LOGGING') then`
   - `elsif p_oper_type in ('RESTORING') then`
   - `elsif p_table_name = 'LOAN_FLOW_RATIO_INFO' then`
   - `if p_oper_type in ('LOGGING') then`
   - `elsif p_oper_type in ('RESTORING') then`

**Business Rules**

Verified from source:
- Conditional expression: `if p_tx_fid is null or p_doc_no is null then`
- Conditional expression: `if p_oper_type not in ('LOGGING', 'RESTORING') then`
- Conditional expression: `if p_oper_type = 'LOGGING' then`
- Conditional expression: `if nvl(g_additional_info_state, 'X') not in ('CLEAR', 'INIT') then`
- Conditional expression: `IF p_table_name = 'LOAN_PAYMENT_PLAN' then`
- Conditional expression: `if p_oper_type in ('LOGGING') then`
- Conditional expression: `elsif p_oper_type in ('RESTORING') then`
- Conditional expression: `elsif p_table_name = 'LOAN_FLOW_RATIO_INFO' then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
procedure table_log_operation(p_doc_no     in varchar2,
                                p_table_name in varchar2,
                                p_tx_fid     in number,
                                p_oper_type  in varchar2);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_doc_no` | `varchar2` | IN | — | Input for `table_log_operation` processing; semantics require caller/domain confirmation. |
| `p_table_name` | `varchar2` | IN | — | Input for `table_log_operation` processing; semantics require caller/domain confirmation. |
| `p_tx_fid` | `number` | IN | — | Input for `table_log_operation` processing; semantics require caller/domain confirmation. |
| `p_oper_type` | `varchar2` | IN | — | Input for `table_log_operation` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `KRD_KOM_PLAN_DETAY`, `KRD_KOM_PLAN_DETAY_LOG`, `LOAN_CATEGORY`, `LOAN_CATEGORY_TEMP`, `LOAN_FLOW_RATIO_INFO`, `LOAN_FLOW_RATIO_INFO_LOG`, `LOAN_PAYMENT_PLAN`, `LOAN_PAYMENT_PLAN_LOG`, `LOAN_STOP_RATIO_INFO`, `LOAN_STOP_RATIO_INFO_LOG` |
| INSERT | `KRD_KOM_PLAN_DETAY`, `KRD_KOM_PLAN_DETAY_LOG`, `LOAN_CATEGORY`, `LOAN_CATEGORY_TEMP`, `LOAN_FLOW_RATIO_INFO`, `LOAN_FLOW_RATIO_INFO_LOG`, `LOAN_PAYMENT_PLAN`, `LOAN_PAYMENT_PLAN_LOG`, `LOAN_STOP_RATIO_INFO`, `LOAN_STOP_RATIO_INFO_LOG` |
| UPDATE | `OPERATIONS.` |
| DELETE | `KRD_KOM_PLAN_DETAY`, `KRD_KOM_PLAN_DETAY_LOG`, `LOAN_CATEGORY`, `LOAN_CATEGORY_TEMP`, `LOAN_FLOW_RATIO_INFO`, `LOAN_PAYMENT_PLAN`, `LOAN_STOP_RATIO_INFO` |

**Error Handling**

- Source excerpt: `r(p_text => 'p_tx_fid or p_document_no parameters cant be null!'); end if; `
- Source excerpt: `r(p_text => 'Oper type should be LOGGING-for logging or RESTORING-for restoring'); end if; `
- Source excerpt: `r('Function usage incomplete. When using the [loan_api.add_additional_info] or [loan_api.add_column_update] procedures, you must call [loan_api.clear_addtional_data] before initiating update operations.'); end if; `
- Source excerpt: `r(p_text => 'Table name should be [LOAN_PAYMENT_PLAN],[LOAN_FLOW_RATIO_INFO],[LOAN_STOP_RATIO_INFO],[LOAN_CATEGORY],[KRD_KOM_PLAN_DETAY]'); end if; end;`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- Direct DML detected: INSERT, UPDATE, DELETE.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.table_log_operation(...);
```

**Technical Notes**

- **Verified from Source:** 232 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="do-int-calculation"></a>
### do_int_calculation

**Type:** PROCEDURE  
**Source:** specification line 422; implementation begins at body line 7275.

**Purpose**

Implements **do_int_calculation** for the interest, penalties and rates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `CS_ACCOUNT`, `EOD_PROGRAMS_EXCEPTION`, `KRD_TEKLIF_DETAY`, `LOAN_FLOW_RATIO_INFO`, `LOAN_INT_CALC_STOP_FOR_GRACE`, `LOAN_PAYMENT_PLAN`, `LOAN_STOP_RATIO_INFO`
2. **Invoked external or qualified routines (static call references):** `GLBL_FAIZ.DAY_COUNT_BASIS_NEW`, `GLBL_TARIH.ONCEKI_ISGUNU`, `GLBL_TARIH.SONRAKI_ISGUNU`, `GNI_UTILITY.DELETE_BATCH_ERROR`, `GNI_UTILITY.HAS_BATCH_ERROR`, `GNI_UTILITY.LOG_BATCH_ERROR`, `LA.ACC_TYPE`, `LOAN_API.ADD_ADDITIONAL_INFO`, `LOAN_API.ADD_ADDITIONAL_MAIN_GROUP`, `LOAN_API.ADD_COLUMN_UPDATE`, `LOAN_API.CLEAR_ADDTIONAL_DATA`, `LOAN_API.CREATE_LOAN_HISTORY`, `LOAN_API.DO_JOURNAL_ENTRY`, `LOAN_API.DO_PLAN_CONTROL`, `LOAN_API.FINALIZE_ADDTIONAL_PROCESS`, `LOAN_API.GET_AMOUNT_FOR_PEN_CALC`, `LOAN_API.GET_GL_ACC_FROM_MATRIX`, `LOAN_API.GET_GL_VALUE` (plus 9 other calls).
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `when nvl(pr.qeyri_is_gunu, 1) = 1 then`
   - `if m.is_grace_applied_in_trs_acc = 'N' or`
   - `if m.is_int_calc is null or m.is_pen_calc is null then`
   - `if m.product_code is null then`
   - `if m.on_not_working_days not in (1, 2) then`
   - `if m.pen_calc_max_amount = 0 then`
   - `if l_sysdate - m.last_calc_access_date >`
   - `when others then`
   - `when x.rate_type = 'INT' and`
   - `when x.rate_type = 'PEN' and`

**Business Rules**

Verified from source:
- Conditional expression: `when nvl(pr.qeyri_is_gunu, 1) = 1 then`
- Conditional expression: `if m.is_grace_applied_in_trs_acc = 'N' or`
- Conditional expression: `if m.is_int_calc is null or m.is_pen_calc is null then`
- Conditional expression: `if m.product_code is null then`
- Conditional expression: `if m.on_not_working_days not in (1, 2) then`
- Conditional expression: `if m.pen_calc_max_amount = 0 then`
- Conditional expression: `if l_sysdate - m.last_calc_access_date >`
- Conditional expression: `when others then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
procedure do_int_calculation(p_min_id  number default 0,
                               p_max_id  number default 999999999,
                               p_doc_no  in varchar2 default null,
                               p_eod_sod in varchar2 default 'E',
                               p_date    in date default glbl.getsysdate);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_min_id` | `number` | IN | `0` | Input for `do_int_calculation` processing; semantics require caller/domain confirmation. |
| `p_max_id` | `number` | IN | `999999999` | Input for `do_int_calculation` processing; semantics require caller/domain confirmation. |
| `p_doc_no` | `varchar2` | IN | `null` | Input for `do_int_calculation` processing; semantics require caller/domain confirmation. |
| `p_eod_sod` | `varchar2` | IN | `'E'` | Input for `do_int_calculation` processing; semantics require caller/domain confirmation. |
| `p_date` | `date` | IN | `glbl.getsysdate` | Input for `do_int_calculation` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `CS_ACCOUNT`, `EOD_PROGRAMS_EXCEPTION`, `KRD_TEKLIF_DETAY`, `LOAN_FLOW_RATIO_INFO`, `LOAN_INT_CALC_STOP_FOR_GRACE`, `LOAN_PAYMENT_PLAN`, `LOAN_STOP_RATIO_INFO` |

Qualified procedure/function references: `GLBL_FAIZ.DAY_COUNT_BASIS_NEW`, `GLBL_TARIH.ONCEKI_ISGUNU`, `GLBL_TARIH.SONRAKI_ISGUNU`, `GNI_UTILITY.DELETE_BATCH_ERROR`, `GNI_UTILITY.HAS_BATCH_ERROR`, `GNI_UTILITY.LOG_BATCH_ERROR`, `LA.ACC_TYPE`, `LOAN_API.ADD_ADDITIONAL_INFO`, `LOAN_API.ADD_ADDITIONAL_MAIN_GROUP`, `LOAN_API.ADD_COLUMN_UPDATE`, `LOAN_API.CLEAR_ADDTIONAL_DATA`, `LOAN_API.CREATE_LOAN_HISTORY`, `LOAN_API.DO_JOURNAL_ENTRY`, `LOAN_API.DO_PLAN_CONTROL`, `LOAN_API.FINALIZE_ADDTIONAL_PROCESS`, `LOAN_API.GET_AMOUNT_FOR_PEN_CALC`, `LOAN_API.GET_GL_ACC_FROM_MATRIX`, `LOAN_API.GET_GL_VALUE`, `LOAN_API.GET_INTEREST_CALC_DATES`, `LOAN_API.GET_INTEREST_CALC_INFO`, `LOAN_API.GET_OVD_DATE`, `LOAN_API.GET_TRN_CALLER_ID`, `LOAN_API.G_DATE_TAB_TYPE`, `LOAN_API.G_ENTRIES_LIST_TAB`, `LOAN_API.LOAN_INT_DIFF_OPERATION`, `LOAN_REPORT_API.GET_LOAN_MESSAGE`, `PR.URUN_KOD`.

**Error Handling**

- Source excerpt: `r(p_text => 'Int calculation has not finished yet for loans without transit process!'); end if; `
- Source excerpt: `r(p_text => 'is_int_calc or is_pen_calc columns in krd_teklif_detay table is null! Please check...'); end if; `
- Source excerpt: `r(p_text => 'Product code not found in pkrd_turkod_pr table, pls check 22401 app for this loan product!' || m.loan_product_code);`
- Source excerpt: `r(p_text => 'Not working day may be 1 or 2, please check 22401 app, for product code:' || m.loan_product_code);`
- Source excerpt: `r(p_text => 'The maximum penalty amount listed for this product ' || m.loan_product_code || ' on screen 22401 cannot be 0!');`
- Source excerpt: `r(p_text => 'Non calculated days of loan {' || m.doc_no || '} more than ' ||`
- Source excerpt: `when others then l_has_stop_operation := 'N'; end;`
- Source excerpt: `r(p_text => 'No data found in loan_acc_types_pr tables for account type: ' || nn.acc_type); end if;`
- Source excerpt: `r(p_text => 'Counter account for acc_type: ' || nn.acc_type || ' not found! Check loan_api.get_gl_acc_from_matrix with param attributes: p_base_type: ' || case`
- Source excerpt: `when no_data_found then r(p_text => 'No data found in loan_flow_ratio_info table, for date: ' || l_dates(i));`
- Source excerpt: `r(p_text => 'No data found in loan_flow_ratio_info table, for date: ' || l_dates(i)); when too_many_rows then`
- Source excerpt: `when too_many_rows then r(p_text => 'Too many rows found in loan_flow_ratio_info table, for date: ' || l_dates(i));`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **2**; `ROLLBACK` references: **1** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.do_int_calculation(...);
```

**Technical Notes**

- **Verified from Source:** 688 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="do-overdue-transit-operation"></a>
### do_overdue_transit_operation

**Type:** PROCEDURE  
**Source:** specification line 437; implementation begins at body line 6931.

**Purpose**

Implements **do_overdue_transit_operation** for the interest, penalties and rates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `CS_ACCOUNT`, `LOAN_OVERDUE_MAPPING`, `LOAN_OVERDUE_TRANSIT_QUEUE`, `LOAN_PAYMENT_PLAN`; inserts into `LOAN_PAYMENT_PLAN`; updates `KRD_TEKLIF_DETAY`, `LOAN_PAYMENT_PLAN`
2. **Invoked external or qualified routines (static call references):** `CL.ACC_TYPE`, `CL.LOAN_DOC_NO`, `CR.ACC_TYPE`, `CR.LOAN_DOC_NO`, `GNI_UTILITY.DELETE_BATCH_ERROR`, `GNI_UTILITY.HAS_BATCH_ERROR`, `GNI_UTILITY.LOG_BATCH_ERROR`, `LOAN_API.CREATE_ACCOUNT`, `LOAN_API.CREATE_LOAN_HISTORY`, `LOAN_API.DO_JOURNAL_ENTRY`, `LOAN_API.DO_PLAN_CONTROL`, `LOAN_API.FINALIZE_ADDTIONAL_PROCESS`, `LOAN_API.GET_ACC_TYPE_BY_STATUS`, `LOAN_API.GET_TRN_CALLER_ID`, `LOAN_API.G_ENTRIES_LIST_TAB`, `LOAN_API.G_LOAN_ACCOUNTS_TAB`, `LOAN_API.TABLE_LOG_OPERATION`, `LOAN_REPORT_API.GET_LOAN_MESSAGE`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if m.product_code is null then`
   - `if l_acc_cnt = 0 then`
   - `if g.amount > 0 then`
   - `when g.oper_type = 'OVERDUE' then`
   - `when g.oper_type = 'TRANSIT' then`
   - `if sql%rowcount = 0 then`
   - `case when g.oper_type = 'OVERDUE' then p_date end,`
   - `case when g.oper_type = 'TRANSIT' then p_date end);`
   - `when g.acc_type_group in`
   - `when g.acc_type_group in`

**Business Rules**

Verified from source:
- Conditional expression: `if m.product_code is null then`
- Conditional expression: `if l_acc_cnt = 0 then`
- Conditional expression: `if g.amount > 0 then`
- Conditional expression: `when g.oper_type = 'OVERDUE' then`
- Conditional expression: `when g.oper_type = 'TRANSIT' then`
- Conditional expression: `if sql%rowcount = 0 then`
- Conditional expression: `case when g.oper_type = 'OVERDUE' then p_date end,`
- Conditional expression: `case when g.oper_type = 'TRANSIT' then p_date end);`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
Procedure do_overdue_transit_operation(p_min_id number default null,
                                         p_max_id number default null,
                                         p_doc_no in varchar2 default null,
                                         p_date   in date default glbl.getsysdate);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_min_id` | `number` | IN | `null` | Input for `do_overdue_transit_operation` processing; semantics require caller/domain confirmation. |
| `p_max_id` | `number` | IN | `null` | Input for `do_overdue_transit_operation` processing; semantics require caller/domain confirmation. |
| `p_doc_no` | `varchar2` | IN | `null` | Input for `do_overdue_transit_operation` processing; semantics require caller/domain confirmation. |
| `p_date` | `date` | IN | `glbl.getsysdate` | Input for `do_overdue_transit_operation` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `CS_ACCOUNT`, `LOAN_OVERDUE_MAPPING`, `LOAN_OVERDUE_TRANSIT_QUEUE`, `LOAN_PAYMENT_PLAN` |
| INSERT | `LOAN_PAYMENT_PLAN` |
| UPDATE | `KRD_TEKLIF_DETAY`, `LOAN_PAYMENT_PLAN` |

Qualified procedure/function references: `CL.ACC_TYPE`, `CL.LOAN_DOC_NO`, `CR.ACC_TYPE`, `CR.LOAN_DOC_NO`, `GNI_UTILITY.DELETE_BATCH_ERROR`, `GNI_UTILITY.HAS_BATCH_ERROR`, `GNI_UTILITY.LOG_BATCH_ERROR`, `LOAN_API.CREATE_ACCOUNT`, `LOAN_API.CREATE_LOAN_HISTORY`, `LOAN_API.DO_JOURNAL_ENTRY`, `LOAN_API.DO_PLAN_CONTROL`, `LOAN_API.FINALIZE_ADDTIONAL_PROCESS`, `LOAN_API.GET_ACC_TYPE_BY_STATUS`, `LOAN_API.GET_TRN_CALLER_ID`, `LOAN_API.G_ENTRIES_LIST_TAB`, `LOAN_API.G_LOAN_ACCOUNTS_TAB`, `LOAN_API.TABLE_LOG_OPERATION`, `LOAN_REPORT_API.GET_LOAN_MESSAGE`.

**Error Handling**

- Source excerpt: `r(p_text => 'Loan product code not found in pkrd_turkod_pr table!'); end if; `
- Source excerpt: `when others then rollback; gni_utility.log_batch_error(p_tx_fid        => l_tx_fid,`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- Direct DML detected: INSERT, UPDATE.
- Explicit `COMMIT` statements: **2**; `ROLLBACK` references: **1** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.do_overdue_transit_operation(...);
```

**Technical Notes**

- **Verified from Source:** 345 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="do-commission-recognition"></a>
### do_commission_recognition

**Type:** PROCEDURE  
**Source:** specification line 442; implementation begins at body line 8062.

**Purpose**

Implements **do_commission_recognition** for the interest, penalties and rates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `KRD_KOM_EOD`, `KRD_KOM_PLAN_DETAY`, `KRD_TESIS`; inserts into `KRD_KOM_EOD`; updates `KRD_KOM_EOD`
2. **Invoked external or qualified routines (static call references):** `GLBL_BAKIYE.ACCOUNT_BALANCE`, `GLBL_TARIH.AYSONU`, `KRD_EOD.GET_GL_URUN_HESAP`, `KRD_EOD.M_FIS_KES`, `LOAN_API.DO_COM_SCHEDULE_ALLIGNMENT`, `LOAN_API.GET_TRN_CALLER_ID`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `If Pdate != Glbl_Tarih.Aysonu(Pdate) Then`
   - `If Nvl(Ww.Kom_Odenilmeli, 0) < 0 Then`

**Business Rules**

Verified from source:
- Conditional expression: `If Pdate != Glbl_Tarih.Aysonu(Pdate) Then`
- Conditional expression: `If Nvl(Ww.Kom_Odenilmeli, 0) < 0 Then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
Procedure do_commission_recognition(p_doc_no varchar2 default null,
                                      Pdate    In Date Default Glbl.Getsysdate);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_doc_no` | `varchar2` | IN | `null` | Input for `do_commission_recognition` processing; semantics require caller/domain confirmation. |
| `Pdate` | `Date` | IN | `Glbl.Getsysdate` | Input for `do_commission_recognition` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `KRD_KOM_EOD`, `KRD_KOM_PLAN_DETAY`, `KRD_TESIS` |
| INSERT | `KRD_KOM_EOD` |
| UPDATE | `KRD_KOM_EOD` |

Qualified procedure/function references: `GLBL_BAKIYE.ACCOUNT_BALANCE`, `GLBL_TARIH.AYSONU`, `KRD_EOD.GET_GL_URUN_HESAP`, `KRD_EOD.M_FIS_KES`, `LOAN_API.DO_COM_SCHEDULE_ALLIGNMENT`, `LOAN_API.GET_TRN_CALLER_ID`.

**Error Handling**

- Source excerpt: `r(p_text => 'This Program can run only last day of month!'); End If; `
- Source excerpt: `r(p_text => t.Sube_Kod || '-' || t.Musteri_No || '-' || t.Kredi_Hesap_No || ' Mushterinin qrafikinde sehv var!'); End Loop;`
- Source excerpt: `r(p_text => Ww.Sube_Kod || '-' || Ww.Musteri_No || '-' || Ww.Kredi_Hesap_No || ' Odenilmeli mebleg 0-dan az ola bilmez!');`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- Direct DML detected: INSERT, UPDATE.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.do_commission_recognition(...);
```

**Technical Notes**

- **Verified from Source:** 145 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="do-loan-delay-int-rate-upd"></a>
### do_Loan_Delay_Int_Rate_Upd

**Type:** PROCEDURE  
**Source:** specification line 477; implementation begins at body line 8914.

**Purpose**

Implements **do_Loan_Delay_Int_Rate_Upd** for the interest, penalties and rates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `KRD_TESIS`; updates `CS_ACCOUNT`
2. **Invoked external or qualified routines (static call references):** `LOAN_API.GET_DELAY_INT_RATE`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `If Nvl(m.Gec_f_Oran_Son, 0) = 0 And`
   - `When Others Then`

**Business Rules**

Verified from source:
- Conditional expression: `If Nvl(m.Gec_f_Oran_Son, 0) = 0 And`
- Conditional expression: `When Others Then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
Procedure do_Loan_Delay_Int_Rate_Upd;
```

**Parameters**

No parameters.

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `KRD_TESIS` |
| UPDATE | `CS_ACCOUNT` |

Qualified procedure/function references: `LOAN_API.GET_DELAY_INT_RATE`.

**Error Handling**

- Source excerpt: `r(p_text => 'Gecikme Faizi 0-dan ferqli oldugu halda son gecikme faizi 0-dir!'); End If; `
- Source excerpt: `When Others Then r(p_text => 'Kreditde sehv: ' || m.Branch_Id || '-' || m.Account_No || '-' || m.Kredi_Hesap_No || Chr(10) ||`
- Source excerpt: `r(p_text => 'Kreditde sehv: ' || m.Branch_Id || '-' || m.Account_No || '-' || m.Kredi_Hesap_No || Chr(10) || Sqlerrm);`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- Direct DML detected: UPDATE.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.do_Loan_Delay_Int_Rate_Upd(...);
```

**Technical Notes**

- **Verified from Source:** 42 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-flow-ratio-info"></a>
### get_flow_ratio_info

**Type:** FUNCTION  
**Source:** specification line 508; implementation begins at body line 9583.

**Purpose**

Implements **get_flow_ratio_info** for the interest, penalties and rates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `LOAN_FLOW_RATIO_INFO`
3. **Control flow:** no prominent conditional branches were isolated by static inspection; review the implementation for full semantics.

**Business Rules**

Verified from source:
- No explicit business threshold or conditional rule could be isolated in this method segment.
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
FUNCTION get_flow_ratio_info(p_doc_no    VARCHAR2,
                               p_date      DATE DEFAULT glbl.getsysdate,
                               p_full_info varchar2 default 'N')
    RETURN LOAN_FLOW_RATE_TAB;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_doc_no` | `VARCHAR2` | IN | — | Input for `get_flow_ratio_info` processing; semantics require caller/domain confirmation. |
| `p_date` | `DATE` | IN | `glbl.getsysdate` | Input for `get_flow_ratio_info` processing; semantics require caller/domain confirmation. |
| `p_full_info` | `varchar2` | IN | `'N'` | Input for `get_flow_ratio_info` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `LOAN_FLOW_RATE_TAB`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `LOAN_FLOW_RATIO_INFO` |

**Error Handling**

- No explicit error handler or raised application message identified within this method segment. Propagated exceptions from dependencies remain possible.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_flow_ratio_info(...);
```

**Technical Notes**

- **Verified from Source:** 30 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-stop-ratio-info"></a>
### get_stop_ratio_info

**Type:** FUNCTION  
**Source:** specification line 513; implementation begins at body line 9612.

**Purpose**

Implements **get_stop_ratio_info** for the interest, penalties and rates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `LOAN_STOP_RATIO_INFO`
3. **Control flow:** no prominent conditional branches were isolated by static inspection; review the implementation for full semantics.

**Business Rules**

Verified from source:
- No explicit business threshold or conditional rule could be isolated in this method segment.
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
FUNCTION get_stop_ratio_info(p_doc_no    VARCHAR2,
                               p_date      DATE DEFAULT glbl.getsysdate,
                               p_full_info varchar2 default 'N',
                               p_info_type varchar2 default 'INT')
    RETURN LOAN_STOP_RATE_TAB;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_doc_no` | `VARCHAR2` | IN | — | Input for `get_stop_ratio_info` processing; semantics require caller/domain confirmation. |
| `p_date` | `DATE` | IN | `glbl.getsysdate` | Input for `get_stop_ratio_info` processing; semantics require caller/domain confirmation. |
| `p_full_info` | `varchar2` | IN | `'N'` | Input for `get_stop_ratio_info` processing; semantics require caller/domain confirmation. |
| `p_info_type` | `varchar2` | IN | `'INT'` | Input for `get_stop_ratio_info` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `LOAN_STOP_RATE_TAB`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `LOAN_STOP_RATIO_INFO` |

**Error Handling**

- No explicit error handler or raised application message identified within this method segment. Propagated exceptions from dependencies remain possible.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_stop_ratio_info(...);
```

**Technical Notes**

- **Verified from Source:** 31 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-incorrect-days"></a>
### get_incorrect_days

**Type:** FUNCTION  
**Source:** specification line 519; implementation begins at body line 9642.

**Purpose**

Implements **get_incorrect_days** for the interest, penalties and rates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** No direct SQL table access identified in the method segment.
3. **Control flow:** no prominent conditional branches were isolated by static inspection; review the implementation for full semantics.

**Business Rules**

Verified from source:
- No explicit business threshold or conditional rule could be isolated in this method segment.
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
function get_incorrect_days(p_date date) return NUMBER_TT
    pipelined;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_date` | `date` | IN | — | Input for `get_incorrect_days` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `NUMBER_TT`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| Direct SQL | None identified; called routines may perform data access. |

**Error Handling**

- No explicit error handler or raised application message identified within this method segment. Propagated exceptions from dependencies remain possible.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_incorrect_days(...);
```

**Technical Notes**

- **Verified from Source:** 7 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-incorrect-days-count"></a>
### get_incorrect_days_count

**Type:** FUNCTION  
**Source:** specification line 522; implementation begins at body line 9682.

**Purpose**

Implements **get_incorrect_days_count** for the interest, penalties and rates domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** No direct SQL table access identified in the method segment.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if p_date is null then`

**Business Rules**

Verified from source:
- Conditional expression: `if p_date is null then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
function get_incorrect_days_count(p_date date) return number;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_date` | `date` | IN | — | Input for `get_incorrect_days_count` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `number`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| Direct SQL | None identified; called routines may perform data access. |

**Error Handling**

- No explicit error handler or raised application message identified within this method segment. Propagated exceptions from dependencies remain possible.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_incorrect_days_count(...);
```

**Technical Notes**

- **Verified from Source:** 13 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

## Delinquency and status

<a id="get-ovd-trs-oper-type"></a>
### get_ovd_trs_oper_type

**Type:** FUNCTION  
**Source:** specification line 96; implementation begins at body line 990.

**Purpose**

Implements **get_ovd_trs_oper_type** for the delinquency and status domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `GAIA.LOAN_PAYMENT_PLAN`, `LOAN_PAYMENT_PLAN`
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if nvl(p_ovd_balance, 0) < 0 then`
   - `If P_OVERDUE_GRACE_DAYS_TYPE = 'INDIVIDUAL' And P_PLAN_TYPE= 'INT' Then`
   - `WHEN W.ACC_TYPE_GROUP IN`
   - `WHEN W.ACC_TYPE_GROUP IN ('OVD_MAIN', 'OVD_INT') AND`
   - `WHEN P.ACC_TYPE_GROUP IN`
   - `If L_BALANCE=0  Then`
   - `If P_OVERDUE_GRACE_DAYS_TYPE = 'KOS' And P_PLAN_TYPE= 'INT' Then`
   - `WHEN W.ACC_TYPE_GROUP IN`
   - `WHEN W.ACC_TYPE_GROUP IN ('OVD_MAIN', 'OVD_INT') AND`
   - `WHEN P.ACC_TYPE_GROUP IN`

**Business Rules**

Verified from source:
- Conditional expression: `if nvl(p_ovd_balance, 0) < 0 then`
- Conditional expression: `If P_OVERDUE_GRACE_DAYS_TYPE = 'INDIVIDUAL' And P_PLAN_TYPE= 'INT' Then`
- Conditional expression: `WHEN W.ACC_TYPE_GROUP IN`
- Conditional expression: `WHEN W.ACC_TYPE_GROUP IN ('OVD_MAIN', 'OVD_INT') AND`
- Conditional expression: `WHEN P.ACC_TYPE_GROUP IN`
- Conditional expression: `If L_BALANCE=0  Then`
- Conditional expression: `If P_OVERDUE_GRACE_DAYS_TYPE = 'KOS' And P_PLAN_TYPE= 'INT' Then`
- Conditional expression: `WHEN W.ACC_TYPE_GROUP IN`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

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

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_date` | `date` | IN | — | Input for `get_ovd_trs_oper_type` processing; semantics require caller/domain confirmation. |
| `p_acc_type_group` | `varchar2` | IN | — | Input for `get_ovd_trs_oper_type` processing; semantics require caller/domain confirmation. |
| `p_plan_date` | `date` | IN | — | Input for `get_ovd_trs_oper_type` processing; semantics require caller/domain confirmation. |
| `p_overdue_grace_days` | `number` | IN | — | Input for `get_ovd_trs_oper_type` processing; semantics require caller/domain confirmation. |
| `p_balance` | `number` | IN | — | Input for `get_ovd_trs_oper_type` processing; semantics require caller/domain confirmation. |
| `p_overdue_min_amount` | `number` | IN | — | Input for `get_ovd_trs_oper_type` processing; semantics require caller/domain confirmation. |
| `p_ovd_balance` | `number` | IN | — | Input for `get_ovd_trs_oper_type` processing; semantics require caller/domain confirmation. |
| `p_loan_end_date` | `date` | IN | — | Input for `get_ovd_trs_oper_type` processing; semantics require caller/domain confirmation. |
| `p_loan_status` | `varchar2` | IN | — | Input for `get_ovd_trs_oper_type` processing; semantics require caller/domain confirmation. |
| `P_OVERDUE_GRACE_DAYS_TYPE` | `VARCHAR2` | IN | — | Input for `get_ovd_trs_oper_type` processing; semantics require caller/domain confirmation. |
| `P_PLAN_TYPE` | `VARCHAR2` | IN | — | Input for `get_ovd_trs_oper_type` processing; semantics require caller/domain confirmation. |
| `p_doc_no` | `VARCHAR2` | IN | `NULL` | Input for `get_ovd_trs_oper_type` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `varchar2`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `GAIA.LOAN_PAYMENT_PLAN`, `LOAN_PAYMENT_PLAN` |

**Error Handling**

- Source excerpt: `r(p_text => 'Overdue amount {' || p_ovd_balance || '} cant be negative!'); end if;`
- Source excerpt: `r(p_text => 'Overdue amount {' || p_balance || '} cant be negative! doc '||p_doc_no); end if; `
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_ovd_trs_oper_type(...);
```

**Technical Notes**

- **Verified from Source:** 286 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-overdue-min-amount"></a>
### get_overdue_min_amount

**Type:** FUNCTION  
**Source:** specification line 176; implementation begins at body line 2253.

**Purpose**

Implements **get_overdue_min_amount** for the delinquency and status domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `PKRD_TURKOD_PR`
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `when no_data_found then`
   - `when others then`

**Business Rules**

Verified from source:
- Conditional expression: `when no_data_found then`
- Conditional expression: `when others then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
function get_overdue_min_amount(p_product_code in number,
                                  p_acc_type     in varchar2) return number;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_product_code` | `number` | IN | — | Input for `get_overdue_min_amount` processing; semantics require caller/domain confirmation. |
| `p_acc_type` | `varchar2` | IN | — | Input for `get_overdue_min_amount` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `number`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `PKRD_TURKOD_PR` |

**Error Handling**

- Source excerpt: `when no_data_found then r(p_text => 'Product code ' || p_product_code || ' not found in pkrd_turkod_pr table!');`
- Source excerpt: `r(p_text => 'Product code ' || p_product_code || ' not found in pkrd_turkod_pr table!'); when others then`
- Source excerpt: `when others then r(p_text => 'Error encountered in search of Product code ' || p_product_code || ' in pkrd_turkod_pr table!');`
- Source excerpt: `r(p_text => 'Error encountered in search of Product code ' || p_product_code || ' in pkrd_turkod_pr table!'); end;`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_overdue_min_amount(...);
```

**Technical Notes**

- **Verified from Source:** 24 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-ovd-date"></a>
### get_ovd_date

**Type:** FUNCTION  
**Source:** specification line 254; implementation begins at body line 4060.

**Purpose**

Implements **get_ovd_date** for the delinquency and status domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `CS_ACCOUNT`, `GAIA.CS_ACCOUNT`, `KRD_TEKLIF_DETAY`, `LOAN_PAYMENT_PLAN`
2. **Invoked external or qualified routines (static call references):** `LOAN_TRANCHE_API.GET_OVD_DATE`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if p_calc_mode not in ('FOR_PEN_CALC', 'DEFAULT') then`
   - `if p_acc_type = 'OVD_MAIN' then`
   - `IF l_urun_kod = 50001 then`
   - `IF l_rest = 0 THEN`
   - `elsif p_acc_type = 'OVD_INT' then`
   - `IF l_urun_kod = 50001 then`
   - `IF l_rest = 0 THEN`
   - `if l_with_tranche_info = 'Y' then`
   - `elsif l_is_pen_calc_on_int = 'Y'`
   - `IF NVL(l_OVERDUE_GRACE_DAYS_TYPE,'STANDART') IN ('STANDART','KOS') then`

**Business Rules**

Verified from source:
- Conditional expression: `if p_calc_mode not in ('FOR_PEN_CALC', 'DEFAULT') then`
- Conditional expression: `if p_acc_type = 'OVD_MAIN' then`
- Conditional expression: `IF l_urun_kod = 50001 then`
- Conditional expression: `IF l_rest = 0 THEN`
- Conditional expression: `elsif p_acc_type = 'OVD_INT' then`
- Conditional expression: `IF l_urun_kod = 50001 then`
- Conditional expression: `IF l_rest = 0 THEN`
- Conditional expression: `if l_with_tranche_info = 'Y' then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
Function get_ovd_date(p_doc_no   varchar2,
                        p_acc_type varchar2,
                        p_date     date default glbl.getsysdate, 
                        p_calc_mode varchar2 default 'DEFAULT'
                        ) return date;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_doc_no` | `varchar2` | IN | — | Input for `get_ovd_date` processing; semantics require caller/domain confirmation. |
| `p_acc_type` | `varchar2` | IN | — | Input for `get_ovd_date` processing; semantics require caller/domain confirmation. |
| `p_date` | `date` | IN | `glbl.getsysdate` | Input for `get_ovd_date` processing; semantics require caller/domain confirmation. |
| `p_calc_mode` | `varchar2` | IN | `'DEFAULT'` | Input for `get_ovd_date` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `date`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `CS_ACCOUNT`, `GAIA.CS_ACCOUNT`, `KRD_TEKLIF_DETAY`, `LOAN_PAYMENT_PLAN` |

Qualified procedure/function references: `LOAN_TRANCHE_API.GET_OVD_DATE`.

**Error Handling**

- Source excerpt: `r(p_text => 'p_calc_mode should be FOR_PEN_CALC - for penalty calculation, DEFAULT-for reporting'); end if; `
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_ovd_date(...);
```

**Technical Notes**

- **Verified from Source:** 201 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-ovd-date-old"></a>
### get_ovd_date_old

**Type:** FUNCTION  
**Source:** specification line 260; implementation begins at body line 4260.

**Purpose**

Implements **get_ovd_date_old** for the delinquency and status domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `CS_ACCOUNT`, `KRD_TEKLIF_DETAY`, `LOAN_PAYMENT_PLAN`
2. **Invoked external or qualified routines (static call references):** `LOAN_TRANCHE_API.GET_OVD_DATE`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if p_calc_mode not in ('FOR_PEN_CALC', 'DEFAULT') then`
   - `if p_acc_type = 'OVD_MAIN' then`
   - `elsif p_acc_type = 'OVD_INT' then`
   - `if l_with_tranche_info = 'Y' then`
   - `elsif l_is_pen_calc_on_int = 'Y'`
   - `If p_Date > l_end_date And l_ovd_date Is Null Then`
   - `if l_debt_amount > 0 then`

**Business Rules**

Verified from source:
- Conditional expression: `if p_calc_mode not in ('FOR_PEN_CALC', 'DEFAULT') then`
- Conditional expression: `if p_acc_type = 'OVD_MAIN' then`
- Conditional expression: `elsif p_acc_type = 'OVD_INT' then`
- Conditional expression: `if l_with_tranche_info = 'Y' then`
- Conditional expression: `elsif l_is_pen_calc_on_int = 'Y'`
- Conditional expression: `If p_Date > l_end_date And l_ovd_date Is Null Then`
- Conditional expression: `if l_debt_amount > 0 then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
Function get_ovd_date_old(p_doc_no   varchar2,
                        p_acc_type varchar2,
                        p_date     date default glbl.getsysdate,
                        p_calc_mode varchar2 default 'DEFAULT') return date;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_doc_no` | `varchar2` | IN | — | Input for `get_ovd_date_old` processing; semantics require caller/domain confirmation. |
| `p_acc_type` | `varchar2` | IN | — | Input for `get_ovd_date_old` processing; semantics require caller/domain confirmation. |
| `p_date` | `date` | IN | `glbl.getsysdate` | Input for `get_ovd_date_old` processing; semantics require caller/domain confirmation. |
| `p_calc_mode` | `varchar2` | IN | `'DEFAULT'` | Input for `get_ovd_date_old` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `date`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `CS_ACCOUNT`, `KRD_TEKLIF_DETAY`, `LOAN_PAYMENT_PLAN` |

Qualified procedure/function references: `LOAN_TRANCHE_API.GET_OVD_DATE`.

**Error Handling**

- Source excerpt: `r(p_text => 'p_calc_mode should be FOR_PEN_CALC - for penalty calculation, DEFAULT-for reporting'); end if; `
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_ovd_date_old(...);
```

**Technical Notes**

- **Verified from Source:** 132 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="do-loan-status-control"></a>
### do_loan_status_control

**Type:** PROCEDURE  
**Source:** specification line 371; implementation begins at body line 5361.

**Purpose**

Implements **do_loan_status_control** for the delinquency and status domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `LOAN_PORTFOLIO_LITE`
2. **Invoked external or qualified routines (static call references):** `GNI_MESSAGE.GET_MESSAGE`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if m.loan_status is null then`
   - `elsif m.loan_status != 'WOFF' and m.loan_npl_balance != 0 then`
   - `elsif m.loan_status = 'WOFF' and m.loan_balance != 0 then`
   - `elsif m.loan_status = 'NORM' and m.TOP_AMOUNT != 0 then`
   - `elsif m.loan_status in ('OVER', 'OVER60') and m.main_amount != 0 then`
   - `elsif m.loan_status in ('OVER60') and m.int_amount != 0 then`
   - `when others then`

**Business Rules**

Verified from source:
- Conditional expression: `if m.loan_status is null then`
- Conditional expression: `elsif m.loan_status != 'WOFF' and m.loan_npl_balance != 0 then`
- Conditional expression: `elsif m.loan_status = 'WOFF' and m.loan_balance != 0 then`
- Conditional expression: `elsif m.loan_status = 'NORM' and m.TOP_AMOUNT != 0 then`
- Conditional expression: `elsif m.loan_status in ('OVER', 'OVER60') and m.main_amount != 0 then`
- Conditional expression: `elsif m.loan_status in ('OVER60') and m.int_amount != 0 then`
- Conditional expression: `when others then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
procedure do_loan_status_control(p_branch_no   in number,
                                   p_customer_no in number,
                                   p_loan_acc    in number);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_branch_no` | `number` | IN | — | Input for `do_loan_status_control` processing; semantics require caller/domain confirmation. |
| `p_customer_no` | `number` | IN | — | Input for `do_loan_status_control` processing; semantics require caller/domain confirmation. |
| `p_loan_acc` | `number` | IN | — | Input for `do_loan_status_control` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `LOAN_PORTFOLIO_LITE` |

Qualified procedure/function references: `GNI_MESSAGE.GET_MESSAGE`.

**Error Handling**

- Source excerpt: `r(p_text => gni_message.get_message(l_mess_name => 'GNI_SYSTEM_KREDIT_STATUS')); elsif m.loan_status != 'WOFF' and m.loan_npl_balance != 0 then r(p_text => gni_message.get_message('GNI_SYSTEM_UMIDSIZ_SUB'));`
- Source excerpt: `r(p_text => gni_message.get_message('GNI_SYSTEM_UMIDSIZ_SUB')); elsif m.loan_status = 'WOFF' and m.loan_balance != 0 then r(p_text => gni_message.get_message('GNI_SYSTEM_BALANS_SUB'));`
- Source excerpt: `r(p_text => gni_message.get_message('GNI_SYSTEM_BALANS_SUB'));  elsif m.loan_status = 'NORM' and m.TOP_AMOUNT != 0 then`
- Source excerpt: `r(p_text => gni_message.get_message('GNI_SYSTEM_NORM_STATUS'));  elsif m.loan_status in ('OVER', 'OVER60') and m.main_amount != 0 then`
- Source excerpt: `r(p_text => gni_message.get_message('GNI_SYSTEM_OVER_STATUS')); elsif m.loan_status in ('OVER60') and m.int_amount != 0 then r(p_text => gni_message.get_message('GNI_SYSTEM_OVER_STATUS'));`
- Source excerpt: `r(p_text => gni_message.get_message('GNI_SYSTEM_OVER_STATUS'));  end if;`
- Source excerpt: `when others then r(p_text => 'Loan: ' || m.branch_no || '-' || m.customer_no || '-' || m.main_acc || ' ' || SQLERRM);`
- Source excerpt: `r(p_text => 'Loan: ' || m.branch_no || '-' || m.customer_no || '-' || m.main_acc || ' ' || SQLERRM); end;`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.do_loan_status_control(...);
```

**Technical Notes**

- **Verified from Source:** 73 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-acc-type-by-status"></a>
### get_acc_type_by_status

**Type:** FUNCTION  
**Source:** specification line 387; implementation begins at body line 6355.

**Purpose**

Implements **get_acc_type_by_status** for the delinquency and status domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `LOAN`, `LOAN_ACC_TYPE_MAPPING`
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `when NO_DATA_FOUND then`
   - `when others then`

**Business Rules**

Verified from source:
- Conditional expression: `when NO_DATA_FOUND then`
- Conditional expression: `when others then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
function get_acc_type_by_status(p_acc_type         varchar2,
                                  p_to_loan_status   varchar2,
                                  p_from_loan_status varchar2 default 'NORM')
    return varchar2 result_cache;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_acc_type` | `varchar2` | IN | — | Input for `get_acc_type_by_status` processing; semantics require caller/domain confirmation. |
| `p_to_loan_status` | `varchar2` | IN | — | Input for `get_acc_type_by_status` processing; semantics require caller/domain confirmation. |
| `p_from_loan_status` | `varchar2` | IN | `'NORM'` | Input for `get_acc_type_by_status` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `varchar2`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `LOAN`, `LOAN_ACC_TYPE_MAPPING` |

**Error Handling**

- Source excerpt: `when NO_DATA_FOUND then r('Can not find acc type [' || p_acc_type || '] in [loan_acc_type_mapping], To Loan Status - [' ||`
- Source excerpt: `r('Can not find acc type [' || p_acc_type || '] in [loan_acc_type_mapping], To Loan Status - [' || p_to_loan_status || '], From Loan Status [' || p_from_loan_status || ']');`
- Source excerpt: `when others then r('Something went wrong in [loan_acc_type_mapping], Acc Type [' || p_acc_type || ', To Loan Status - [' || p_to_loan_status ||`
- Source excerpt: `r('Something went wrong in [loan_acc_type_mapping], Acc Type [' || p_acc_type || ', To Loan Status - [' || p_to_loan_status || '], From Loan Status [' || p_from_loan_status || ']');`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_acc_type_by_status(...);
```

**Technical Notes**

- **Verified from Source:** 34 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

## Limits, tranches and overdrafts

<a id="evaluate-limit-amount"></a>
### evaluate_limit_amount

**Type:** PROCEDURE  
**Source:** specification line 82; implementation begins at body line 179.

**Purpose**

Implements **evaluate_limit_amount** for the limits, tranches and overdrafts domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `CARDS_ALL`, `CS_ACCOUNT`, `GAIA.LOAN_CATEGORY`, `GAIA.LOAN_OPERATION_HISTORY`, `KRD_TEKLIF_DETAY`
2. **Invoked external or qualified routines (static call references):** `GLBL_HESAP.GET_ACCOUNT_PR`, `LOAN_API.ADD_ADDITIONAL_INFO`, `LOAN_API.CREATE_LOAN_HISTORY`, `LOAN_API.DO_JOURNAL_ENTRY`, `LOAN_API.FINALIZE_ADDTIONAL_PROCESS`, `LOAN_API.GET_TRN_CALLER_ID`, `LOAN_API.G_ENTRIES_LIST_TAB`, `LOAN_REPORT_API.GET_LOAN_MESSAGE`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `when exists (select null`
   - `when k.khat_tip = 2 then -- berpa olunmayan`
   - `if m.lim_diff < 0 then`
   - `if l_entries.count > 0 then`
   - `if p_caller_tx_fid is not null then`
   - `When Others Then`
   - `if p_caller_tx_fid is null and p_doc_no is null then`

**Business Rules**

Verified from source:
- Conditional expression: `when exists (select null`
- Conditional expression: `when k.khat_tip = 2 then -- berpa olunmayan`
- Conditional expression: `if m.lim_diff < 0 then`
- Conditional expression: `if l_entries.count > 0 then`
- Conditional expression: `if p_caller_tx_fid is not null then`
- Conditional expression: `When Others Then`
- Conditional expression: `if p_caller_tx_fid is null and p_doc_no is null then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
procedure evaluate_limit_amount(p_min_id        number default 0,
                                  p_max_id        number default 999999999,
                                  p_doc_no        in varchar2,
                                  p_caller_tx_fid in number default null);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_min_id` | `number` | IN | `0` | Input for `evaluate_limit_amount` processing; semantics require caller/domain confirmation. |
| `p_max_id` | `number` | IN | `999999999` | Input for `evaluate_limit_amount` processing; semantics require caller/domain confirmation. |
| `p_doc_no` | `varchar2` | IN | — | Input for `evaluate_limit_amount` processing; semantics require caller/domain confirmation. |
| `p_caller_tx_fid` | `number` | IN | `null` | Input for `evaluate_limit_amount` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `CARDS_ALL`, `CS_ACCOUNT`, `GAIA.LOAN_CATEGORY`, `GAIA.LOAN_OPERATION_HISTORY`, `KRD_TEKLIF_DETAY` |

Qualified procedure/function references: `GLBL_HESAP.GET_ACCOUNT_PR`, `LOAN_API.ADD_ADDITIONAL_INFO`, `LOAN_API.CREATE_LOAN_HISTORY`, `LOAN_API.DO_JOURNAL_ENTRY`, `LOAN_API.FINALIZE_ADDTIONAL_PROCESS`, `LOAN_API.GET_TRN_CALLER_ID`, `LOAN_API.G_ENTRIES_LIST_TAB`, `LOAN_REPORT_API.GET_LOAN_MESSAGE`.

**Error Handling**

- Source excerpt: `When Others Then r('doc_no: ' || m.doc_no || Chr(10) || Sqlerrm); end;`
- Source excerpt: `r('doc_no: ' || m.doc_no || Chr(10) || Sqlerrm); end; if p_caller_tx_fid is null and p_doc_no is null then`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **1**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.evaluate_limit_amount(...);
```

**Technical Notes**

- **Verified from Source:** 154 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="do-create-tranche"></a>
### do_create_tranche

**Type:** PROCEDURE  
**Source:** specification line 158; implementation begins at body line 8955.

**Purpose**

Implements **do_create_tranche** for the limits, tranches and overdrafts domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `GLBL_TRANSACTION`, `KRD_TEKLIF_DETAY`
2. **Invoked external or qualified routines (static call references):** `APEX_KRD2204_0_API_P.DEL_KRD2204_0`, `APEX_KRD2204_0_API_P.INS_KRD2204_0`, `KRD2204_0_API.JUSTDOIT`, `KRD2204_0_API.UPDATE_PAYMENT_PLAN`, `LOAN_TRANCHE_API.DO_CREATE_TRANCHE`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if p_trn_type = 'CREATE' then`
   - `if p_contract_no is null or p_tranche_amount is null then`
   - `when others then`
   - `if l_kd.with_tranche_info_yn = 'Y' then`
   - `elsif p_trn_type = 'DELETE' then`
   - `when others then`
   - `when others then`
   - `R('Error ocured when [do_create_tranche] ' || sqlerrm);`

**Business Rules**

Verified from source:
- Conditional expression: `if p_trn_type = 'CREATE' then`
- Conditional expression: `if p_contract_no is null or p_tranche_amount is null then`
- Conditional expression: `when others then`
- Conditional expression: `if l_kd.with_tranche_info_yn = 'Y' then`
- Conditional expression: `elsif p_trn_type = 'DELETE' then`
- Conditional expression: `when others then`
- Conditional expression: `when others then`
- Conditional expression: `R('Error ocured when [do_create_tranche] ' || sqlerrm);`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

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

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_contract_no` | `varchar2` | IN | — | Input for `do_create_tranche` processing; semantics require caller/domain confirmation. |
| `p_tranche_type` | `varchar2` | IN | `null` | Input for `do_create_tranche` processing; semantics require caller/domain confirmation. |
| `p_tracnhe_term` | `varchar2` | IN | `null` | Input for `do_create_tranche` processing; semantics require caller/domain confirmation. |
| `p_tranche_amount` | `number` | IN | — | Input for `do_create_tranche` processing; semantics require caller/domain confirmation. |
| `p_int_com_amount` | `number` | IN | `null` | Input for `do_create_tranche` processing; semantics require caller/domain confirmation. |
| `p_trn_type` | `varchar2` | IN | — | Input for `do_create_tranche` processing; semantics require caller/domain confirmation. |
| `p_tx_fid` | `number` | IN OUT | — | Input/output parameter; method may modify the supplied value. |

**Return Value / Outputs**

OUT/IN OUT parameters: `p_tx_fid`.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `GLBL_TRANSACTION`, `KRD_TEKLIF_DETAY` |

Qualified procedure/function references: `APEX_KRD2204_0_API_P.DEL_KRD2204_0`, `APEX_KRD2204_0_API_P.INS_KRD2204_0`, `KRD2204_0_API.JUSTDOIT`, `KRD2204_0_API.UPDATE_PAYMENT_PLAN`, `LOAN_TRANCHE_API.DO_CREATE_TRANCHE`.

**Error Handling**

- Source excerpt: `r('In Creation this parameteres cant be p_contract_no or p_tranche_amount null!'); end if; `
- Source excerpt: `when others then r('Does not find loan in [krd_teklif_detay] with contract_no [' || p_contract_no || ']');`
- Source excerpt: `r('Does not find loan in [krd_teklif_detay] with contract_no [' || p_contract_no || ']'); end;`
- Source excerpt: `when others then r(p_text => 'Error encountered in search of tx_fid in glbl_transaction'); end;`
- Source excerpt: `r(p_text => 'Error encountered in search of tx_fid in glbl_transaction'); end; `
- Source excerpt: `r(p_text => 'p_trn_type should be CREATE - for create, DELETE - for delete'); end if; `
- Source excerpt: `when others then p_tx_fid := l_tx_fid; R('Error ocured when [do_create_tranche] ' || sqlerrm);`
- Source excerpt: `R('Error ocured when [do_create_tranche] ' || sqlerrm); end; `
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.do_create_tranche(...);
```

**Technical Notes**

- **Verified from Source:** 97 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="create-overdrafts"></a>
### create_overdrafts

**Type:** PROCEDURE  
**Source:** specification line 630; implementation begins at body line 11963.

**Purpose**

Implements **create_overdrafts** for the limits, tranches and overdrafts domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `CARDS_ALL`, `CS_ACCOUNT`, `EOD_PROGRAMS_EXCEPTION`, `KRD_TEKLIF_DETAY`; inserts into `TEMP_CARD_BALANCE`; updates `CARDS_ALL`, `CS_ACCOUNT`, `KRD_TEKLIF_DETAY`
2. **Invoked external or qualified routines (static call references):** `API_VISTA.P2P_TRANS_VALUE`, `GLBL_HESAP.HESAPNO_AC`, `GLBL_HESAP.HESAPNO_KAPA`, `LOAN_API.ADD_INFO_TAB`, `LOAN_API.DO_JOURNAL_ENTRY`, `LOAN_API.DO_PLAN_CONTROL`, `LOAN_API.GET_TRN_CALLER_ID`, `LOAN_API.G_ENTRIES_LIST_TAB`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if p_oper_type not in ('CREATE_OVERDRAFT', 'CLOSE_LOAN') then`
   - `if p_oper_type in ('CREATE_OVERDRAFT', 'CLOSE_LOAN') then`
   - `when '9001' then`
   - `if n.acc_closed_date is not null and n.acc_balance = 0 then`
   - `elsif n.acc_closed_date is null and n.teklif_tutar < n.acc_balance then`
   - `When Others Then`
   - `if p_oper_type in ('CREATE_OVERDRAFT') then`
   - `when '9001' then`
   - `if l_acc_tab.count > 0 then`
   - `if l_cnt > 0 then`

**Business Rules**

Verified from source:
- Conditional expression: `if p_oper_type not in ('CREATE_OVERDRAFT', 'CLOSE_LOAN') then`
- Conditional expression: `if p_oper_type in ('CREATE_OVERDRAFT', 'CLOSE_LOAN') then`
- Conditional expression: `when '9001' then`
- Conditional expression: `if n.acc_closed_date is not null and n.acc_balance = 0 then`
- Conditional expression: `elsif n.acc_closed_date is null and n.teklif_tutar < n.acc_balance then`
- Conditional expression: `When Others Then`
- Conditional expression: `if p_oper_type in ('CREATE_OVERDRAFT') then`
- Conditional expression: `when '9001' then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
procedure create_overdrafts(p_customer in number default null,
                              p_min_id   in number default null,
                              p_max_id   in number default null, 
                              p_oper_type in varchar2 default 'CREATE_OVERDRAFT');
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_customer` | `number` | IN | `null` | Input for `create_overdrafts` processing; semantics require caller/domain confirmation. |
| `p_min_id` | `number` | IN | `null` | Input for `create_overdrafts` processing; semantics require caller/domain confirmation. |
| `p_max_id` | `number` | IN | `null` | Input for `create_overdrafts` processing; semantics require caller/domain confirmation. |
| `p_oper_type` | `varchar2` | IN | `'CREATE_OVERDRAFT'` | Input for `create_overdrafts` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `CARDS_ALL`, `CS_ACCOUNT`, `EOD_PROGRAMS_EXCEPTION`, `KRD_TEKLIF_DETAY` |
| INSERT | `TEMP_CARD_BALANCE` |
| UPDATE | `CARDS_ALL`, `CS_ACCOUNT`, `KRD_TEKLIF_DETAY` |

Qualified procedure/function references: `API_VISTA.P2P_TRANS_VALUE`, `GLBL_HESAP.HESAPNO_AC`, `GLBL_HESAP.HESAPNO_KAPA`, `LOAN_API.ADD_INFO_TAB`, `LOAN_API.DO_JOURNAL_ENTRY`, `LOAN_API.DO_PLAN_CONTROL`, `LOAN_API.GET_TRN_CALLER_ID`, `LOAN_API.G_ENTRIES_LIST_TAB`.

**Error Handling**

- Source excerpt: `r(p_text => 'p_oper_type should be CREATE_OVERDRAFT or CLOSE_LOAN'); end if; --------------- Borcu baglanmish OV-in evvelki sublarini acmaq ------------------`
- Source excerpt: `When Others Then r('doc_no: ' || n.sened_no || Chr(10) || Sqlerrm); end;`
- Source excerpt: `r('doc_no: ' || n.sened_no || Chr(10) || Sqlerrm); end; end loop;`
- Source excerpt: `When Others Then r('cust_no: ' || m.customer || Chr(10) || Sqlerrm); end;`
- Source excerpt: `r('cust_no: ' || m.customer || Chr(10) || Sqlerrm); end; end loop;`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- Direct DML detected: INSERT, UPDATE.
- Explicit `COMMIT` statements: **2**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.create_overdrafts(...);
```

**Technical Notes**

- **Verified from Source:** 318 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-new-ov-cont-no"></a>
### get_new_ov_cont_no

**Type:** FUNCTION  
**Source:** specification line 635; implementation begins at body line 12280.

**Purpose**

Implements **get_new_ov_cont_no** for the limits, tranches and overdrafts domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `CS_ACCOUNT`, `KRD_TEKLIF_DETAY`
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `when no_data_found then`
   - `when others then`

**Business Rules**

Verified from source:
- Conditional expression: `when no_data_found then`
- Conditional expression: `when others then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
function get_new_ov_cont_no(p_branch_no in number,
                              p_cust_no   in number,
                              p_acc       in number) return varchar2;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_branch_no` | `number` | IN | — | Input for `get_new_ov_cont_no` processing; semantics require caller/domain confirmation. |
| `p_cust_no` | `number` | IN | — | Input for `get_new_ov_cont_no` processing; semantics require caller/domain confirmation. |
| `p_acc` | `number` | IN | — | Input for `get_new_ov_cont_no` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `varchar2`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `CS_ACCOUNT`, `KRD_TEKLIF_DETAY` |

**Error Handling**

- Source excerpt: `when no_data_found then r('Musteri hesabi tapilmadi!'); when others then`
- Source excerpt: `r('Musteri hesabi tapilmadi!'); when others then r('Musteri melumatlarinda sehv var!');`
- Source excerpt: `when others then r('Musteri melumatlarinda sehv var!'); end;`
- Source excerpt: `r('Musteri melumatlarinda sehv var!'); end; `
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_new_ov_cont_no(...);
```

**Technical Notes**

- **Verified from Source:** 33 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

## Accounting and audit

<a id="add-column-update-1"></a>
### add_column_update — overload 1

**Type:** PROCEDURE  
**Source:** specification line 141; implementation begins at body line 1637.

**Purpose**

Implements **add_column_update** for the accounting and audit domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `LOAN_HISTORY_MAPPING`, `LOAN_TRANCHE_INFO`; updates `OPERATIONS.`
2. **Invoked external or qualified routines (static call references):** `RUHA3H.LOG`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if nvl(g_additional_info_state, 'X') not in ('CLEAR', 'INIT') then`
   - `when others then`
   - `if lhm.data_type = 'UNKNOWN' then`
   - `if p_tranche_no is not null then`

**Business Rules**

Verified from source:
- Conditional expression: `if nvl(g_additional_info_state, 'X') not in ('CLEAR', 'INIT') then`
- Conditional expression: `when others then`
- Conditional expression: `if lhm.data_type = 'UNKNOWN' then`
- Conditional expression: `if p_tranche_no is not null then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
procedure add_column_update(p_tag_name   varchar2,
                              p_old_value  varchar2,
                              p_new_value  varchar2,
                              p_tranche_no number default null);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_tag_name` | `varchar2` | IN | — | Input for `add_column_update` processing; semantics require caller/domain confirmation. |
| `p_old_value` | `varchar2` | IN | — | Input for `add_column_update` processing; semantics require caller/domain confirmation. |
| `p_new_value` | `varchar2` | IN | — | Input for `add_column_update` processing; semantics require caller/domain confirmation. |
| `p_tranche_no` | `number` | IN | `null` | Input for `add_column_update` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `LOAN_HISTORY_MAPPING`, `LOAN_TRANCHE_INFO` |
| UPDATE | `OPERATIONS.` |

Qualified procedure/function references: `RUHA3H.LOG`.

**Error Handling**

- Source excerpt: `r('Function usage incomplete. When using the [loan_api.add_additional_info] or [loan_api.add_column_update] procedures, you must call [loan_api.clear_addtional_data] before initiating update operations.'); end if; `
- Source excerpt: `when others then r('Tag [' || p_tag_name || '] not declared in [loan_history_mapping]');`
- Source excerpt: `r('Tag [' || p_tag_name || '] not declared in [loan_history_mapping]'); end;`
- Source excerpt: `r('Tag [' || p_tag_name || '] is [loan_history_mapping] is incorrect!'); end if;`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- Direct DML detected: UPDATE.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.add_column_update(...);
```

**Technical Notes**

- **Verified from Source:** 63 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="add-column-update-2"></a>
### add_column_update — overload 2

**Type:** PROCEDURE  
**Source:** specification line 145; implementation begins at body line 1699.

**Purpose**

Implements **add_column_update** for the accounting and audit domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** No direct SQL table access identified in the method segment.
3. **Control flow:** no prominent conditional branches were isolated by static inspection; review the implementation for full semantics.

**Business Rules**

Verified from source:
- No explicit business threshold or conditional rule could be isolated in this method segment.
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
procedure add_column_update(p_tag_name   varchar2,
                              p_old_value  date,
                              p_new_value  date,
                              p_tranche_no number default null);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_tag_name` | `varchar2` | IN | — | Input for `add_column_update` processing; semantics require caller/domain confirmation. |
| `p_old_value` | `date` | IN | — | Input for `add_column_update` processing; semantics require caller/domain confirmation. |
| `p_new_value` | `date` | IN | — | Input for `add_column_update` processing; semantics require caller/domain confirmation. |
| `p_tranche_no` | `number` | IN | `null` | Input for `add_column_update` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| Direct SQL | None identified; called routines may perform data access. |

**Error Handling**

- No explicit error handler or raised application message identified within this method segment. Propagated exceptions from dependencies remain possible.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.add_column_update(...);
```

**Technical Notes**

- **Verified from Source:** 12 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-voucher-data-from-query"></a>
### get_voucher_data_from_query

**Type:** FUNCTION  
**Source:** specification line 184; implementation begins at body line 2316.

**Purpose**

Implements **get_voucher_data_from_query** for the accounting and audit domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** No direct SQL table access identified in the method segment.
2. **Invoked external or qualified routines (static call references):** `DBMS_SQL.CLOSE_CURSOR`, `DBMS_SQL.COLUMN_VALUE`, `DBMS_SQL.DEFINE_COLUMN`, `DBMS_SQL.DESCRIBE_COLUMNS`, `DBMS_SQL.EXECUTE`, `DBMS_SQL.FETCH_ROWS`, `DBMS_SQL.IS_OPEN`, `DBMS_SQL.PARSE`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if p_query is null then`
   - `if p_result_type not in ('SINGLE_ROW', 'MULTI_ROW') then`
   - `if l_desc_t(i).col_type = 2 then`
   - `elsif l_desc_t(i).col_type = 12 then`
   - `when p_result_type = 'SINGLE_ROW' then`
   - `if l_desc_t(i).col_type = 2 then`
   - `elsif l_desc_t(i).col_type = 12 then`
   - `when l_date_val is not null then`
   - `if upper(l_desc_t(i).col_name) = 'GROUP_CODE' then`
   - `if l_group_code is null then`

**Business Rules**

Verified from source:
- Conditional expression: `if p_query is null then`
- Conditional expression: `if p_result_type not in ('SINGLE_ROW', 'MULTI_ROW') then`
- Conditional expression: `if l_desc_t(i).col_type = 2 then`
- Conditional expression: `elsif l_desc_t(i).col_type = 12 then`
- Conditional expression: `when p_result_type = 'SINGLE_ROW' then`
- Conditional expression: `if l_desc_t(i).col_type = 2 then`
- Conditional expression: `elsif l_desc_t(i).col_type = 12 then`
- Conditional expression: `when l_date_val is not null then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
function get_voucher_data_from_query(p_query       in varchar2,
                                       p_result_type in varchar2)
    return g_col_value_tab_map;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_query` | `varchar2` | IN | — | Input for `get_voucher_data_from_query` processing; semantics require caller/domain confirmation. |
| `p_result_type` | `varchar2` | IN | — | Input for `get_voucher_data_from_query` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `g_col_value_tab_map`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| Direct SQL | None identified; called routines may perform data access. |

Qualified procedure/function references: `DBMS_SQL.CLOSE_CURSOR`, `DBMS_SQL.COLUMN_VALUE`, `DBMS_SQL.DEFINE_COLUMN`, `DBMS_SQL.DESCRIBE_COLUMNS`, `DBMS_SQL.EXECUTE`, `DBMS_SQL.FETCH_ROWS`, `DBMS_SQL.IS_OPEN`, `DBMS_SQL.PARSE`.

**Error Handling**

- Source excerpt: `r('p_query can be null!'); end if; `
- Source excerpt: `r('p_result_type should be SINGLE_ROW or MULTI_ROW!'); end if; `
- Source excerpt: `r('GROUP_CODE field is not defined in query or GROUP_CODE field is null!'); end if; `
- Source excerpt: `r('Result of query is empty!'); elsif p_result_type = 'SINGLE_ROW' and l_col_value_tab_map.count > 1 then r('Result of query return multi row!');`
- Source excerpt: `r('Result of query return multi row!'); end if; `
- Source excerpt: `when others then if dbms_sql.is_open(l_cursor_id) then dbms_sql.close_cursor(l_cursor_id);`
- Source excerpt: `r('Error encountered in query! ' || sqlerrm); raise; end;`
- Source excerpt: `raise; end; `
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_voucher_data_from_query(...);
```

**Technical Notes**

- **Verified from Source:** 121 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-gl-value"></a>
### get_gl_value

**Type:** FUNCTION  
**Source:** specification line 199; implementation begins at body line 2551.

**Purpose**

Implements **get_gl_value** for the accounting and audit domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `LOAN_GLOBAL_PARAMETERS_PR`
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `when NO_DATA_FOUND then`
   - `when TOO_MANY_ROWS then`
   - `when OTHERS then`

**Business Rules**

Verified from source:
- Conditional expression: `when NO_DATA_FOUND then`
- Conditional expression: `when TOO_MANY_ROWS then`
- Conditional expression: `when OTHERS then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
function get_gl_value(p_parameter_name in varchar2) return varchar2;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_parameter_name` | `varchar2` | IN | — | Input for `get_gl_value` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `varchar2`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `LOAN_GLOBAL_PARAMETERS_PR` |

**Error Handling**

- Source excerpt: `when NO_DATA_FOUND then r(p_text => 'Parameter{' || p_parameter_name || '} not found in loan_global_parameters_pr table!');`
- Source excerpt: `r(p_text => 'Parameter{' || p_parameter_name || '} not found in loan_global_parameters_pr table!'); when TOO_MANY_ROWS then`
- Source excerpt: `when TOO_MANY_ROWS then r(p_text => 'Too many rows in search of parameter{' || p_parameter_name ||`
- Source excerpt: `r(p_text => 'Too many rows in search of parameter{' || p_parameter_name || '} in loan_global_parameters_pr table!');`
- Source excerpt: `when OTHERS then r(p_text => 'Encountered error in search of parameter {' || p_parameter_name ||`
- Source excerpt: `r(p_text => 'Encountered error in search of parameter {' || p_parameter_name || '} in loan_global_parameters_pr table!');`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_gl_value(...);
```

**Technical Notes**

- **Verified from Source:** 23 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-gl-acc-active-passive"></a>
### get_gl_acc_active_passive

**Type:** FUNCTION  
**Source:** specification line 215; implementation begins at body line 2727.

**Purpose**

Implements **get_gl_acc_active_passive** for the accounting and audit domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `GL_ACCOUNT_DEFINE`
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `when no_data_found then`
   - `when too_many_rows then`
   - `when others then`

**Business Rules**

Verified from source:
- Conditional expression: `when no_data_found then`
- Conditional expression: `when too_many_rows then`
- Conditional expression: `when others then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
function get_gl_acc_active_passive(p_acc_no in varchar2) return varchar2 result_cache;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_acc_no` | `varchar2` | IN | — | Input for `get_gl_acc_active_passive` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `varchar2`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `GL_ACCOUNT_DEFINE` |

**Error Handling**

- Source excerpt: `when no_data_found then r(p_text => 'Account_no: ' || p_acc_no || ' not found in gl_account_define table!');`
- Source excerpt: `r(p_text => 'Account_no: ' || p_acc_no || ' not found in gl_account_define table!'); when too_many_rows then`
- Source excerpt: `when too_many_rows then r(p_text => 'Encountered more than one row in gl_account_define table in search of account_no: ' ||`
- Source excerpt: `r(p_text => 'Encountered more than one row in gl_account_define table in search of account_no: ' || p_acc_no);`
- Source excerpt: `when others then r(p_text => 'Encountered error in gl_account_define table in search of account_no: ' ||`
- Source excerpt: `r(p_text => 'Encountered error in gl_account_define table in search of account_no: ' || p_acc_no);`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_gl_acc_active_passive(...);
```

**Technical Notes**

- **Verified from Source:** 23 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-gl-acc-from-matrix"></a>
### get_gl_acc_from_matrix

**Type:** FUNCTION  
**Source:** specification line 217; implementation begins at body line 2749.

**Purpose**

Implements **get_gl_acc_from_matrix** for the accounting and audit domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `CS_ACCOUNT`, `GL_URUN_HESAP_PR`, `KRD_TEKLIF_DETAY`, `SP_URUN_PR`
2. **Invoked external or qualified routines (static call references):** `GLBL_HESAP.GET_ACCOUNT_PR`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if p_base_type not in ('MAIN', 'OVD_MAIN') then`
   - `if p_loan_doc_no is not null then`
   - `when others then`
   - `when others then`
   - `when no_data_found then`
   - `when too_many_rows then`
   - `when others then`
   - `if p_acc_type in ('MAIN_RES_EXPENSE') then`
   - `elsif p_acc_type = 'LIM_RES_EXPENSE' then`
   - `elsif p_acc_type in ('MAIN_RES') then`

**Business Rules**

Verified from source:
- Conditional expression: `if p_base_type not in ('MAIN', 'OVD_MAIN') then`
- Conditional expression: `if p_loan_doc_no is not null then`
- Conditional expression: `when others then`
- Conditional expression: `when others then`
- Conditional expression: `when no_data_found then`
- Conditional expression: `when too_many_rows then`
- Conditional expression: `when others then`
- Conditional expression: `if p_acc_type in ('MAIN_RES_EXPENSE') then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

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

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_product_code` | `number` | IN | `null` | Input for `get_gl_acc_from_matrix` processing; semantics require caller/domain confirmation. |
| `p_cust_type` | `number` | IN | `null` | Input for `get_gl_acc_from_matrix` processing; semantics require caller/domain confirmation. |
| `p_period_id` | `number` | IN | `null` | Input for `get_gl_acc_from_matrix` processing; semantics require caller/domain confirmation. |
| `p_currency_id` | `number` | IN | `null` | Input for `get_gl_acc_from_matrix` processing; semantics require caller/domain confirmation. |
| `p_base_type` | `varchar2` | IN | — | Input for `get_gl_acc_from_matrix` processing; semantics require caller/domain confirmation. |
| `p_loan_doc_no` | `varchar2` | IN | `null` | Input for `get_gl_acc_from_matrix` processing; semantics require caller/domain confirmation. |
| `p_acc_type` | `varchar2` | IN | — | Input for `get_gl_acc_from_matrix` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `varchar2`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `CS_ACCOUNT`, `GL_URUN_HESAP_PR`, `KRD_TEKLIF_DETAY`, `SP_URUN_PR` |

Qualified procedure/function references: `GLBL_HESAP.GET_ACCOUNT_PR`.

**Error Handling**

- Source excerpt: `r(p_text => 'p_gl_base_type should be MAIN - for main account, OVD_MAIN - for overdue account!'); end if; `
- Source excerpt: `when others then r(p_text => 'Error encountered in search of loan_doc_no: ' || p_loan_doc_no);`
- Source excerpt: `r(p_text => 'Error encountered in search of loan_doc_no: ' || p_loan_doc_no); end;`
- Source excerpt: `when others then r(p_text => 'Error encountered in search krd_teklif_detay table of loan_doc_no: ' || p_loan_doc_no);`
- Source excerpt: `r(p_text => 'Error encountered in search krd_teklif_detay table of loan_doc_no: ' || p_loan_doc_no); end;`
- Source excerpt: `when no_data_found then r(p_text => 'No data found in gl_urun_hesap_pr table!'); when too_many_rows then`
- Source excerpt: `r(p_text => 'No data found in gl_urun_hesap_pr table!'); when too_many_rows then r(p_text => 'Many rows found in gl_urun_hesap_pr table!');`
- Source excerpt: `when too_many_rows then r(p_text => 'Many rows found in gl_urun_hesap_pr table!'); when others then`
- Source excerpt: `r(p_text => 'Many rows found in gl_urun_hesap_pr table!'); when others then r(p_text => 'Error encountered in gl_urun_hesap_pr table!');`
- Source excerpt: `when others then r(p_text => 'Error encountered in gl_urun_hesap_pr table!'); end;`
- Source excerpt: `r(p_text => 'Error encountered in gl_urun_hesap_pr table!'); end; `
- Source excerpt: `r(p_text => 'p_acc_type is invalid!'); end if; return l_gl_acc;`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_gl_acc_from_matrix(...);
```

**Technical Notes**

- **Verified from Source:** 189 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="do-journal-entry"></a>
### do_journal_entry

**Type:** PROCEDURE  
**Source:** specification line 319; implementation begins at body line 4441.

**Purpose**

Implements **do_journal_entry** for the accounting and audit domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `ENTRIES_LIST_TAB`, `SS_MUH1201_0_LOG`; inserts into `ENTRIES_LIST_TAB`; deletes from `ENTRIES_LIST_TAB`
2. **Invoked external or qualified routines (static call references):** `GLBL_FUNCTIONS.GUN_KUR_BUL`, `GLBL_HESAP.GET_ACC_CUR`, `MM_ACCOUNTING#.POST_JOURNAL`, `PA_API#.CREATE_J_WSQL`, `TRN_BROKER.REGISTER_EOD`, `TRN_BROKER.SETTXDETAILS`, `TRN_BROKER.SETTXSTATE`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if p_tx_fid is not null then`
   - `if p_entries_list.count > 0 or l_expence_count > 0 then`
   - `if p_trn_type not in ('CREATE', 'POST') then`
   - `if p_is_eod = 'Y' then`
   - `if p_entries_list.count > 0 then`
   - `If d_Sira != -1 and p_trn_type = 'POST' Then`
   - `If l_err = 0 Then`

**Business Rules**

Verified from source:
- Conditional expression: `if p_tx_fid is not null then`
- Conditional expression: `if p_entries_list.count > 0 or l_expence_count > 0 then`
- Conditional expression: `if p_trn_type not in ('CREATE', 'POST') then`
- Conditional expression: `if p_is_eod = 'Y' then`
- Conditional expression: `if p_entries_list.count > 0 then`
- Conditional expression: `If d_Sira != -1 and p_trn_type = 'POST' Then`
- Conditional expression: `If l_err = 0 Then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
Procedure do_journal_entry(p_entries_list  g_entries_list_tab,
                             p_trn_caller_id in number,
                             p_tx_fid        in out number,
                             p_trn_type      in varchar2,
                             p_is_eod        in varchar2 default 'Y');
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_entries_list` | `g_entries_list_tab` | IN | — | Input for `do_journal_entry` processing; semantics require caller/domain confirmation. |
| `p_trn_caller_id` | `number` | IN | — | Input for `do_journal_entry` processing; semantics require caller/domain confirmation. |
| `p_tx_fid` | `number` | IN OUT | — | Input/output parameter; method may modify the supplied value. |
| `p_trn_type` | `varchar2` | IN | — | Input for `do_journal_entry` processing; semantics require caller/domain confirmation. |
| `p_is_eod` | `varchar2` | IN | `'Y'` | Input for `do_journal_entry` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

OUT/IN OUT parameters: `p_tx_fid`.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `ENTRIES_LIST_TAB`, `SS_MUH1201_0_LOG` |
| INSERT | `ENTRIES_LIST_TAB` |
| DELETE | `ENTRIES_LIST_TAB` |

Qualified procedure/function references: `GLBL_FUNCTIONS.GUN_KUR_BUL`, `GLBL_HESAP.GET_ACC_CUR`, `MM_ACCOUNTING#.POST_JOURNAL`, `PA_API#.CREATE_J_WSQL`, `TRN_BROKER.REGISTER_EOD`, `TRN_BROKER.SETTXDETAILS`, `TRN_BROKER.SETTXSTATE`.

**Error Handling**

- Source excerpt: `r(p_text => 'p_trn_type must be CREATE or POST!'); end if; `
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- Direct DML detected: INSERT, DELETE.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.do_journal_entry(...);
```

**Technical Notes**

- **Verified from Source:** 120 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="create-journal-entries"></a>
### create_journal_entries

**Type:** PROCEDURE  
**Source:** specification line 325; implementation begins at body line 4560.

**Purpose**

Implements **create_journal_entries** for the accounting and audit domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `LOAN_OPERATION_DESC`, `LOAN_OPERATION_VOUCHER`, `SS_MUH1201_0_LOG`
2. **Invoked external or qualified routines (static call references):** `LOAN_API.DO_JOURNAL_ENTRY`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `when no_data_found then`
   - `when too_many_rows then`
   - `when others then`
   - `if l_o.voucher_query is not null then`
   - `if upper(l_v.dr_branch_id) = l_column_name then`
   - `if upper(l_v.DR_ACCOUNT_NO) = l_column_name then`
   - `if upper(l_v.dr_account_sub) = l_column_name then`
   - `if upper(l_v.dr_amount) = l_column_name then`
   - `if upper(l_v.dr_amount_lc) = l_column_name then`
   - `if upper(l_v.dr_cust_type) = l_column_name then`

**Business Rules**

Verified from source:
- Conditional expression: `when no_data_found then`
- Conditional expression: `when too_many_rows then`
- Conditional expression: `when others then`
- Conditional expression: `if l_o.voucher_query is not null then`
- Conditional expression: `if upper(l_v.dr_branch_id) = l_column_name then`
- Conditional expression: `if upper(l_v.DR_ACCOUNT_NO) = l_column_name then`
- Conditional expression: `if upper(l_v.dr_account_sub) = l_column_name then`
- Conditional expression: `if upper(l_v.dr_amount) = l_column_name then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
procedure create_journal_entries(p_oper_type in varchar2,
                                   p_tx_fid    in number,
                                   p_trn_type  in varchar2);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_oper_type` | `varchar2` | IN | — | Input for `create_journal_entries` processing; semantics require caller/domain confirmation. |
| `p_tx_fid` | `number` | IN | — | Input for `create_journal_entries` processing; semantics require caller/domain confirmation. |
| `p_trn_type` | `varchar2` | IN | — | Input for `create_journal_entries` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `LOAN_OPERATION_DESC`, `LOAN_OPERATION_VOUCHER`, `SS_MUH1201_0_LOG` |

Qualified procedure/function references: `LOAN_API.DO_JOURNAL_ENTRY`.

**Error Handling**

- Source excerpt: `when no_data_found then r('No data found in loan_operation_desc!'); when too_many_rows then`
- Source excerpt: `r('No data found in loan_operation_desc!'); when too_many_rows then r('Too many rows found in loan_operation_desc!');`
- Source excerpt: `when too_many_rows then r('Too many rows found in loan_operation_desc!'); when others then`
- Source excerpt: `r('Too many rows found in loan_operation_desc!'); when others then r('Error encountered in loan_operation_desc!');`
- Source excerpt: `when others then r('Error encountered in loan_operation_desc!'); end;`
- Source excerpt: `r('Error encountered in loan_operation_desc!'); end; `
- Source excerpt: `when others then r(' Query column: ' || l_column_name || ', with value: ' || l_column_value || ' ' || sqlerrm);`
- Source excerpt: `r(' Query column: ' || l_column_name || ', with value: ' || l_column_value || ' ' || sqlerrm); end;`
- Source excerpt: `when others then r('Error encountered in requirement result: ' || l_v.requirement ||`
- Source excerpt: `r('Error encountered in requirement result: ' || l_v.requirement || ' please check requirement in loan_operation_voucher table');`
- Source excerpt: `r('Voucher for the group_code: ' || l_col_value_tab(k).group_code || ' not found in loan_operation_voucher table'); end if;`
- Source excerpt: `when others then l_error_msg := sqlerrm; r('In operation type: ' || p_oper_type || ' ' || l_error_msg);`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.create_journal_entries(...);
```

**Technical Notes**

- **Verified from Source:** 178 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="do-journal-control"></a>
### do_journal_control

**Type:** PROCEDURE  
**Source:** specification line 454; implementation begins at body line 8487.

**Purpose**

Implements **do_journal_control** for the accounting and audit domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `CS_ACCOUNT`
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if l_count > 0 then`
   - `if m.main_top_amount > 0 then`
   - `elsif m.main_top_amount < 0 then`
   - `if m.int_top_amount > 0 then`
   - `elsif m.int_top_amount < 0 then`
   - `\*if m.ovd_int_top_amount > 0 then`
   - `elsif m.ovd_int_top_amount < 0 then`
   - `if l_accounts.count > 0 then`
   - `when others then`

**Business Rules**

Verified from source:
- Conditional expression: `if l_count > 0 then`
- Conditional expression: `if m.main_top_amount > 0 then`
- Conditional expression: `elsif m.main_top_amount < 0 then`
- Conditional expression: `if m.int_top_amount > 0 then`
- Conditional expression: `elsif m.int_top_amount < 0 then`
- Conditional expression: `\*if m.ovd_int_top_amount > 0 then`
- Conditional expression: `elsif m.ovd_int_top_amount < 0 then`
- Conditional expression: `if l_accounts.count > 0 then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
procedure do_journal_control(p_branch_id   IN Number,
                               p_customer_no IN Number,
                               p_account_sub IN Number);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_branch_id` | `Number` | IN | — | Input for `do_journal_control` processing; semantics require caller/domain confirmation. |
| `p_customer_no` | `Number` | IN | — | Input for `do_journal_control` processing; semantics require caller/domain confirmation. |
| `p_account_sub` | `Number` | IN | — | Input for `do_journal_control` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `CS_ACCOUNT` |

**Error Handling**

- Source excerpt: `r(p_text => '???????? ?? ????. ?????? ????? ???? ?????? ?? ?????????? ?????? !!!'); end if; end;`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.do_journal_control(...);
```

**Technical Notes**

- **Verified from Source:** 258 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

## History, metadata and reversal

<a id="clear-addtional-data"></a>
### clear_addtional_data

**Type:** PROCEDURE  
**Source:** specification line 134; implementation begins at body line 1570.

**Purpose**

Implements **clear_addtional_data** for the history, metadata and reversal domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** No direct SQL table access identified in the method segment.
2. **Invoked external or qualified routines (static call references):** `RUHA3H.LOG`.
3. **Control flow:** no prominent conditional branches were isolated by static inspection; review the implementation for full semantics.

**Business Rules**

Verified from source:
- No explicit business threshold or conditional rule could be isolated in this method segment.
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
procedure clear_addtional_data(p_state varchar2 default 'CLEAR');
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_state` | `varchar2` | IN | `'CLEAR'` | Input for `clear_addtional_data` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| Direct SQL | None identified; called routines may perform data access. |

Qualified procedure/function references: `RUHA3H.LOG`.

**Error Handling**

- No explicit error handler or raised application message identified within this method segment. Propagated exceptions from dependencies remain possible.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.clear_addtional_data(...);
```

**Technical Notes**

- **Verified from Source:** 15 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="add-additional-group"></a>
### add_additional_group

**Type:** PROCEDURE  
**Source:** specification line 136; implementation begins at body line 1600.

**Purpose**

Implements **add_additional_group** for the history, metadata and reversal domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** No direct SQL table access identified in the method segment.
2. **Invoked external or qualified routines (static call references):** `APEX_JSON.OPEN_OBJECT`, `RUHA3H.LOG`.
3. **Control flow:** no prominent conditional branches were isolated by static inspection; review the implementation for full semantics.

**Business Rules**

Verified from source:
- No explicit business threshold or conditional rule could be isolated in this method segment.
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
procedure add_additional_group(p_tag_name varchar2 default null);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_tag_name` | `varchar2` | IN | `null` | Input for `add_additional_group` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| Direct SQL | None identified; called routines may perform data access. |

Qualified procedure/function references: `APEX_JSON.OPEN_OBJECT`, `RUHA3H.LOG`.

**Error Handling**

- No explicit error handler or raised application message identified within this method segment. Propagated exceptions from dependencies remain possible.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.add_additional_group(...);
```

**Technical Notes**

- **Verified from Source:** 9 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="end-additional-group"></a>
### end_additional_group

**Type:** PROCEDURE  
**Source:** specification line 137; implementation begins at body line 1608.

**Purpose**

Implements **end_additional_group** for the history, metadata and reversal domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** No direct SQL table access identified in the method segment.
2. **Invoked external or qualified routines (static call references):** `RUHA3H.LOG`.
3. **Control flow:** no prominent conditional branches were isolated by static inspection; review the implementation for full semantics.

**Business Rules**

Verified from source:
- No explicit business threshold or conditional rule could be isolated in this method segment.
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
procedure end_additional_group;
```

**Parameters**

No parameters.

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| Direct SQL | None identified; called routines may perform data access. |

Qualified procedure/function references: `RUHA3H.LOG`.

**Error Handling**

- No explicit error handler or raised application message identified within this method segment. Propagated exceptions from dependencies remain possible.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.end_additional_group(...);
```

**Technical Notes**

- **Verified from Source:** 9 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="add-additional-info-1"></a>
### add_additional_info — overload 1

**Type:** PROCEDURE  
**Source:** specification line 138; implementation begins at body line 1616.

**Purpose**

Implements **add_additional_info** for the history, metadata and reversal domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** updates `OPERATIONS.`
2. **Invoked external or qualified routines (static call references):** `APEX_JSON.WRITE`, `RUHA3H.LOG`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if nvl(g_additional_info_state, 'X') not in ('CLEAR', 'INIT') then`

**Business Rules**

Verified from source:
- Conditional expression: `if nvl(g_additional_info_state, 'X') not in ('CLEAR', 'INIT') then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
procedure add_additional_info(p_tag_name varchar2, p_value varchar2);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_tag_name` | `varchar2` | IN | — | Input for `add_additional_info` processing; semantics require caller/domain confirmation. |
| `p_value` | `varchar2` | IN | — | Input for `add_additional_info` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| UPDATE | `OPERATIONS.` |

Qualified procedure/function references: `APEX_JSON.WRITE`, `RUHA3H.LOG`.

**Error Handling**

- Source excerpt: `r('Function usage incomplete. When using the [loan_api.add_additional_info] or [loan_api.add_column_update] procedures, you must call [loan_api.clear_addtional_data] before initiating update operations.'); end if; `
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- Direct DML detected: UPDATE.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.add_additional_info(...);
```

**Technical Notes**

- **Verified from Source:** 16 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="add-additional-info-2"></a>
### add_additional_info — overload 2

**Type:** PROCEDURE  
**Source:** specification line 139; implementation begins at body line 1631.

**Purpose**

Implements **add_additional_info** for the history, metadata and reversal domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** No direct SQL table access identified in the method segment.
3. **Control flow:** no prominent conditional branches were isolated by static inspection; review the implementation for full semantics.

**Business Rules**

Verified from source:
- No explicit business threshold or conditional rule could be isolated in this method segment.
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
procedure add_additional_info(p_tag_name varchar2, p_value date);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_tag_name` | `varchar2` | IN | — | Input for `add_additional_info` processing; semantics require caller/domain confirmation. |
| `p_value` | `date` | IN | — | Input for `add_additional_info` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| Direct SQL | None identified; called routines may perform data access. |

**Error Handling**

- No explicit error handler or raised application message identified within this method segment. Propagated exceptions from dependencies remain possible.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.add_additional_info(...);
```

**Technical Notes**

- **Verified from Source:** 7 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="get-additional-info"></a>
### get_additional_info

**Type:** FUNCTION  
**Source:** specification line 150; implementation begins at body line 1710.

**Purpose**

Implements **get_additional_info** for the history, metadata and reversal domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `LOAN_OPERATION_HISTORY`
2. **Invoked external or qualified routines (static call references):** `JSON_OBJECT_T.PARSE`, `L_OBJ.GET_STRING`.
3. **Control flow:** no prominent conditional branches were isolated by static inspection; review the implementation for full semantics.

**Business Rules**

Verified from source:
- No explicit business threshold or conditional rule could be isolated in this method segment.
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
function get_additional_info(p_Tx_fid number, p_tag_name varchar2)
    return varchar2;
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_Tx_fid` | `number` | IN | — | Input for `get_additional_info` processing; semantics require caller/domain confirmation. |
| `p_tag_name` | `varchar2` | IN | — | Input for `get_additional_info` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

Return type: `varchar2`. The meaning of the resulting value depends on the documented processing conditions.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `LOAN_OPERATION_HISTORY` |

Qualified procedure/function references: `JSON_OBJECT_T.PARSE`, `L_OBJ.GET_STRING`.

**Error Handling**

- No explicit error handler or raised application message identified within this method segment. Propagated exceptions from dependencies remain possible.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.get_additional_info(...);
```

**Technical Notes**

- **Verified from Source:** 17 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="finalize-addtional-process"></a>
### finalize_addtional_process

**Type:** PROCEDURE  
**Source:** specification line 153; implementation begins at body line 1726.

**Purpose**

Implements **finalize_addtional_process** for the history, metadata and reversal domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** No direct SQL table access identified in the method segment.
2. **Invoked external or qualified routines (static call references):** `LOAN_TRANCHE_API.G_LOAN_TRANCHE_TAB`.
3. **Control flow:** no prominent conditional branches were isolated by static inspection; review the implementation for full semantics.

**Business Rules**

Verified from source:
- No explicit business threshold or conditional rule could be isolated in this method segment.
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
procedure finalize_addtional_process(p_doc_no   varchar2,
                                       p_offer_id varchar2);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_doc_no` | `varchar2` | IN | — | Input for `finalize_addtional_process` processing; semantics require caller/domain confirmation. |
| `p_offer_id` | `varchar2` | IN | — | Input for `finalize_addtional_process` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| Direct SQL | None identified; called routines may perform data access. |

Qualified procedure/function references: `LOAN_TRANCHE_API.G_LOAN_TRANCHE_TAB`.

**Error Handling**

- No explicit error handler or raised application message identified within this method segment. Propagated exceptions from dependencies remain possible.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.finalize_addtional_process(...);
```

**Technical Notes**

- **Verified from Source:** 8 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="reverse-update"></a>
### reverse_update

**Type:** PROCEDURE  
**Source:** specification line 156; implementation begins at body line 1998.

**Purpose**

Implements **reverse_update** for the history, metadata and reversal domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `KRD_TEKLIF_DETAY`, `LOAN_OPERATION_HISTORY`
2. **Invoked external or qualified routines (static call references):** `JSON_OBJECT_T.PARSE`, `LOAN_API.DO_DELETE_OPERATION`, `L_LOG.GET_STRING`, `L_OBJ.GET`, `L_OLD.GET_STRING`, `L_TRN.GET`, `L_TRNS.GET`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `when others then`
   - `when others then`
   - `if l_log is not null then`
   - `if l_new is not null then`
   - `if l_trns is not null then`
   - `if l_new is not null then`

**Business Rules**

Verified from source:
- Conditional expression: `when others then`
- Conditional expression: `when others then`
- Conditional expression: `if l_log is not null then`
- Conditional expression: `if l_new is not null then`
- Conditional expression: `if l_trns is not null then`
- Conditional expression: `if l_new is not null then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
procedure reverse_update(p_tx_fid number);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_tx_fid` | `number` | IN | — | Input for `reverse_update` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `KRD_TEKLIF_DETAY`, `LOAN_OPERATION_HISTORY` |

Qualified procedure/function references: `JSON_OBJECT_T.PARSE`, `LOAN_API.DO_DELETE_OPERATION`, `L_LOG.GET_STRING`, `L_OBJ.GET`, `L_OLD.GET_STRING`, `L_TRN.GET`, `L_TRNS.GET`.

**Error Handling**

- Source excerpt: `when others then r('Can not get additional info in [loan_operation_history] with tx fid [' || p_Tx_fid || ']');`
- Source excerpt: `r('Can not get additional info in [loan_operation_history] with tx fid [' || p_Tx_fid || ']'); end;`
- Source excerpt: `when others then l_offer_id := 'X'; --r('Can not get find loan[' || l_doc_no || '] in [krd_teklif_detay]');`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.reverse_update(...);
```

**Technical Notes**

- **Verified from Source:** 112 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="create-loan-history"></a>
### create_loan_history

**Type:** PROCEDURE  
**Source:** specification line 375; implementation begins at body line 5433.

**Purpose**

Implements **create_loan_history** for the history, metadata and reversal domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `GLBL_TRANSACTION`, `GL_JOURNAL_LINES`, `LOAN_OPERATION_DESC`, `LOAN_OPERATION_HISTORY`; inserts into `LOAN_OPERATION_HISTORY`; updates `ACTIONS.`, `LOAN_OPERATION_HISTORY`
2. **Invoked external or qualified routines (static call references):** `LOAN_API.GET_GL_ACC_ACTIVE_PASSIVE`, `LOAN_API.LOAN_INT_DIFF_OPERATION`, `TRN_BROKER.REGISTER_EOD`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if p_trn_type != 'C' then`
   - `when no_data_found then`
   - `when others then`
   - `if l_tx_fid is null then`
   - `when no_data_found then`
   - `when others then`
   - `if p_trn_type in ('I', 'U') then`
   - `if nvl(g_additional_info_state, 'FINISH') != 'FINISH' then`
   - `if g_additional_info_state is null then`
   - `if p_add_info is not null then`

**Business Rules**

Verified from source:
- Conditional expression: `if p_trn_type != 'C' then`
- Conditional expression: `when no_data_found then`
- Conditional expression: `when others then`
- Conditional expression: `if l_tx_fid is null then`
- Conditional expression: `when no_data_found then`
- Conditional expression: `when others then`
- Conditional expression: `if p_trn_type in ('I', 'U') then`
- Conditional expression: `if nvl(g_additional_info_state, 'FINISH') != 'FINISH' then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
procedure create_loan_history(p_oper_type VARCHAR2 default null,
                                p_doc_no    VARCHAR2 default null,
                                p_trn_date  DATE default glbl.getsysdate,
                                p_tx_fid    NUMBER,
                                p_trn_type  varchar2,
                                p_add_info  add_info_tab default null);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_oper_type` | `VARCHAR2` | IN | `null` | Input for `create_loan_history` processing; semantics require caller/domain confirmation. |
| `p_doc_no` | `VARCHAR2` | IN | `null` | Input for `create_loan_history` processing; semantics require caller/domain confirmation. |
| `p_trn_date` | `DATE` | IN | `glbl.getsysdate` | Input for `create_loan_history` processing; semantics require caller/domain confirmation. |
| `p_tx_fid` | `NUMBER` | IN | — | Input for `create_loan_history` processing; semantics require caller/domain confirmation. |
| `p_trn_type` | `varchar2` | IN | — | Input for `create_loan_history` processing; semantics require caller/domain confirmation. |
| `p_add_info` | `add_info_tab` | IN | `null` | Input for `create_loan_history` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `GLBL_TRANSACTION`, `GL_JOURNAL_LINES`, `LOAN_OPERATION_DESC`, `LOAN_OPERATION_HISTORY` |
| INSERT | `LOAN_OPERATION_HISTORY` |
| UPDATE | `ACTIONS.`, `LOAN_OPERATION_HISTORY` |

Qualified procedure/function references: `LOAN_API.GET_GL_ACC_ACTIVE_PASSIVE`, `LOAN_API.LOAN_INT_DIFF_OPERATION`, `TRN_BROKER.REGISTER_EOD`.

**Error Handling**

- Source excerpt: `when no_data_found then r(p_text => 'p_app_oper_code not found in loan_operation_desc table!'); when others then`
- Source excerpt: `r(p_text => 'p_app_oper_code not found in loan_operation_desc table!'); when others then r(p_text => 'error encountered in search of oper_type');`
- Source excerpt: `when others then r(p_text => 'error encountered in search of oper_type'); end;`
- Source excerpt: `r(p_text => 'error encountered in search of oper_type'); end; `
- Source excerpt: `when no_data_found then r(p_text => 'Transaction with tx_fid: ' || l_tx_fid || ' , trn_arg: ' || p_trn_type || ' , trn_date: ' ||`
- Source excerpt: `r(p_text => 'Transaction with tx_fid: ' || l_tx_fid || ' , trn_arg: ' || p_trn_type || ' , trn_date: ' || p_trn_date || ' , trn_caller: ' || l_op.trn_caller ||`
- Source excerpt: `when others then r(p_text => 'error encountered in search of tx_fid in glbl_transaction table!'); `
- Source excerpt: `r(p_text => 'error encountered in search of tx_fid in glbl_transaction table!');  end;`
- Source excerpt: `r('Procedure usage incomplete. When using a [loan_api.add_column_update] or [loan_api.add_additional_info] or [loan_api.clear_addtional_data] procedure, you must finalize your operation with [loan_api.finalize_addtional_process]. Ensur`
- Source excerpt: `r(p_text => 'You need delete this operation(s) [' || h.tx_fids || '] before delete this operation [' || l_tx_fid || ']'); end loop;`
- Source excerpt: `r(p_text => 'p_trn_type must be I-insert, U-update, D-delete'); end if; `
- Source excerpt: `when others then clear_addtional_data(null); r(sqlerrm);`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- Direct DML detected: INSERT, UPDATE.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.create_loan_history(...);
```

**Technical Notes**

- **Verified from Source:** 500 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="update-loan-history"></a>
### update_loan_history

**Type:** PROCEDURE  
**Source:** specification line 382; implementation begins at body line 5932.

**Purpose**

Implements **update_loan_history** for the history, metadata and reversal domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `CS_ACCOUNT`, `GL_JOURNAL_LINES`, `LOAN_OPERATION_DESC`, `LOAN_OPERATION_HISTORY`; merges into `LOAN_OPERATION_HISTORY`
2. **Invoked external or qualified routines (static call references):** `LOAN_API.DO_PLAN_CONTROL`, `LOAN_API.GET_GL_ACC_ACTIVE_PASSIVE`, `LOAN_TRANCHE_API.OVD_AMOUNT_CORRECTION`.
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if p_tx_fid is null then`
   - `when NO_DATA_FOUND then`
   - `when TOO_MANY_ROWS then`
   - `when others then`
   - `WHEN MATCHED THEN`
   - `when others then`
   - `if l_od.plan_control = 'Y' then`
   - `if l_od.oper_type in ('PAYMENT', 'CLOSE', 'TRANCHE', 'WOFF_PAYMENT') then`

**Business Rules**

Verified from source:
- Conditional expression: `if p_tx_fid is null then`
- Conditional expression: `when NO_DATA_FOUND then`
- Conditional expression: `when TOO_MANY_ROWS then`
- Conditional expression: `when others then`
- Conditional expression: `WHEN MATCHED THEN`
- Conditional expression: `when others then`
- Conditional expression: `if l_od.plan_control = 'Y' then`
- Conditional expression: `if l_od.oper_type in ('PAYMENT', 'CLOSE', 'TRANCHE', 'WOFF_PAYMENT') then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
procedure update_loan_history(p_tx_fid number);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_tx_fid` | `number` | IN | — | Input for `update_loan_history` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `CS_ACCOUNT`, `GL_JOURNAL_LINES`, `LOAN_OPERATION_DESC`, `LOAN_OPERATION_HISTORY` |
| MERGE | `LOAN_OPERATION_HISTORY` |

Qualified procedure/function references: `LOAN_API.DO_PLAN_CONTROL`, `LOAN_API.GET_GL_ACC_ACTIVE_PASSIVE`, `LOAN_TRANCHE_API.OVD_AMOUNT_CORRECTION`.

**Error Handling**

- Source excerpt: `r('[p_tx_fid] is null at [loan_api.update_loan_history]'); end if; `
- Source excerpt: `when NO_DATA_FOUND then r('Can not find information in [loan_operation_history] with tx fid [' || p_tx_fid || ']!');`
- Source excerpt: `r('Can not find information in [loan_operation_history] with tx fid [' || p_tx_fid || ']!'); when TOO_MANY_ROWS then`
- Source excerpt: `when TOO_MANY_ROWS then r('Find duplicate information in [loan_operation_history] with tx fid [' || p_tx_fid || ']!');`
- Source excerpt: `r('Find duplicate information in [loan_operation_history] with tx fid [' || p_tx_fid || ']!'); when others then`
- Source excerpt: `when others then r('Error ocured [' || sqlerrm || '] find information in [loan_operation_history] with tx fid [' ||`
- Source excerpt: `r('Error ocured [' || sqlerrm || '] find information in [loan_operation_history] with tx fid [' || p_tx_fid || ']!');`
- Source excerpt: `when others then r('Error ocured [' || sqlerrm || '] find information in [loan_operation_desc] with oper_type [' ||`
- Source excerpt: `r('Error ocured [' || sqlerrm || '] find information in [loan_operation_desc] with oper_type [' || l_op.OPER_TYPE || ']!');`
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- Direct DML detected: MERGE.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.update_loan_history(...);
```

**Technical Notes**

- **Verified from Source:** 155 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---

<a id="init-global-variables"></a>
### init_global_variables

**Type:** PROCEDURE  
**Source:** specification line 640; implementation begins at body line 12312.

**Purpose**

Implements **init_global_variables** for the history, metadata and reversal domain. Refer to the verified processing operations, conditions, and database effects below for the exact behavior.

**Business Logic (source-backed)**

1. **Data interactions:** reads `KRD_ODEME_PLAN`, `KRD_TEKLIF`, `KRD_TEKLIF_DETAY`, `KRD_TESIS`
3. **Control-flow evidence:** the implementation contains these conditions/branches (code excerpts, not an exhaustive execution trace):
   - `if p_doc_no is null then`
   - `IF nvl(G_KTD.Sened_No, 'X') != p_doc_no or p_reset then`
   - `when others then`
   - `when others then`
   - `when others then`
   - `when others then`
   - `when others then`

**Business Rules**

Verified from source:
- Conditional expression: `if p_doc_no is null then`
- Conditional expression: `IF nvl(G_KTD.Sened_No, 'X') != p_doc_no or p_reset then`
- Conditional expression: `when others then`
- Conditional expression: `when others then`
- Conditional expression: `when others then`
- Conditional expression: `when others then`
- Conditional expression: `when others then`
- **Inferred — Needs Review:** product-specific meaning of status codes, flags, and thresholds requires confirmation against configuration and referenced routines.

**PL/SQL Signature**

```sql
Procedure init_global_variables(p_doc_no varchar2,
                                  p_reset  boolean default false);
```

**Parameters**

| Parameter | Data type | Direction | Default | Description |
|---|---|---|---|---|
| `p_doc_no` | `varchar2` | IN | — | Input for `init_global_variables` processing; semantics require caller/domain confirmation. |
| `p_reset` | `boolean` | IN | `false` | Input for `init_global_variables` processing; semantics require caller/domain confirmation. |

**Return Value / Outputs**

No explicit OUT parameter; the result may be a database or package-state change.

**Database Dependencies**

| Operation | Referenced objects (direct textual SQL references) |
|---|---|
| READ | `KRD_ODEME_PLAN`, `KRD_TEKLIF`, `KRD_TEKLIF_DETAY`, `KRD_TESIS` |

**Error Handling**

- Source excerpt: `raise finalize; end if; `
- Source excerpt: `when others then r('[krd_teklif_detay] is invalid'); end;`
- Source excerpt: `r('[krd_teklif_detay] is invalid'); end; `
- Source excerpt: `when others then r('[krd_teklif] is invalid'); end;`
- Source excerpt: `r('[krd_teklif] is invalid'); end; `
- Source excerpt: `when others then r('[krd_tesis] is invalid'); end;`
- Source excerpt: `r('[krd_tesis] is invalid'); end; `
- Source excerpt: `when others then r('[krd_odeme_plan] is invalid'); end;`
- Source excerpt: `r('[krd_odeme_plan] is invalid'); end; end if;`
- Source excerpt: `when others then G_KTD := null; G_KTE := null;`
- Source excerpt: `raise finalize; end; `
- The behavior of the shared `R(...)` error routine is not defined in the provided package.

**Side Effects & Transaction Notes**

- No direct DML identified in this method segment; delegated writes via called routines are possible.
- Explicit `COMMIT` statements: **0**; `ROLLBACK` references: **0** (static counts within implementation segment).
- Transaction ownership cannot be concluded from absence of `COMMIT`/`ROLLBACK`, because the invoked packages may manage transactions.

**Usage Example**

```sql
-- Template only: supply verified test parameters and review side effects.
-- gaia.loan_api.init_global_variables(...);
```

**Technical Notes**

- **Verified from Source:** 64 approximate lines in the extracted implementation segment; the segment may contain adjacent comments/private declarations.
- **Not Determined:** Detailed behavior in referenced packages, triggers, and database constraints is outside the provided source.

---
