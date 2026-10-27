# LOAN_API — Complete Public API Reference

> **Status:** Draft / Requires technical and business approval.  **Scope:** All 88 active public declarations in the supplied package specification, including 4 pairs of overloads.

> **Source of truth:** Supplied `LOAN_API` specification and body. No production SQL has been executed. Statements marked **Verify** require a developer to confirm usage semantics and implementation details.

## Navigation

Each entry links to one exact declaration below. Overloads have distinct stable anchors.

### Accounts & Balances

- [`get_loan_amount`](#get_loan_amount) — function · specification line 130
- [`get_overdue_min_amount`](#get_overdue_min_amount) — function · specification line 136
- [`get_gl_value`](#get_gl_value) — function · specification line 161
- [`get_gl_acc_active_passive`](#get_gl_acc_active_passive) — function · specification line 189
- [`get_gl_acc_from_matrix`](#get_gl_acc_from_matrix) — function · specification line 191
- [`get_offer_id`](#get_offer_id) — function · specification line 219
- [`get_account_feature`](#get_account_feature) — function · specification line 273
- [`is_acc_exists`](#is_acc_exists) — function · specification line 278
- [`is_online_offer`](#is_online_offer) — function · specification line 287
- [`create_account`](#create_account) — procedure · specification line 304
- [`get_new_acc`](#get_new_acc) — function · specification line 320
- [`do_loan_status_control`](#do_loan_status_control) — procedure · specification line 340
- [`get_acc_type_by_status`](#get_acc_type_by_status) — function · specification line 353
- [`change_account_status`](#change_account_status) — procedure · specification line 453

### Interest & Penalties

- [`get_pen_info_for_calc`](#get_pen_info_for_calc--overload-1) — procedure (overload 1) · specification line 73
- [`get_interest_calc_dates`](#get_interest_calc_dates) — function · specification line 80
- [`get_interest_calc_dates_ex`](#get_interest_calc_dates_ex) — function · specification line 85
- [`get_interest_calc_info`](#get_interest_calc_info) — procedure · specification line 90
- [`get_interest_calc_info_ex`](#get_interest_calc_info_ex) — procedure · specification line 101
- [`get_pen_info_for_calc`](#get_pen_info_for_calc--overload-2) — procedure (overload 2) · specification line 137
- [`get_basis_year_days_cnt`](#get_basis_year_days_cnt) — function · specification line 158
- [`loan_int_diff_operation`](#loan_int_diff_operation) — procedure · specification line 163
- [`loan_int_diff_operation_ex`](#loan_int_diff_operation_ex) — procedure · specification line 177
- [`Get_Delay_Int_Rate`](#get_delay_int_rate) — function · specification line 201
- [`get_amount_for_pen_calc`](#get_amount_for_pen_calc) — function · specification line 233
- [`do_Loan_Delay_Int_Rate_Upd`](#do_loan_delay_int_rate_upd) — procedure · specification line 450

### Schedules & Rates

- [`get_formatted_grace_from_list`](#get_formatted_grace_from_list) — function · specification line 150
- [`get_grace_info`](#get_grace_info) — function · specification line 153
- [`get_commission_schedule`](#get_commission_schedule) — function · specification line 205
- [`add_months_for_loan`](#add_months_for_loan) — function · specification line 211
- [`get_plan_payment_amount`](#get_plan_payment_amount) — function · specification line 225
- [`get_ovd_date`](#get_ovd_date) — function · specification line 229
- [`get_Plan_Month_Count`](#get_plan_month_count) — function · specification line 241
- [`get_plan_paid_month_count`](#get_plan_paid_month_count) — function · specification line 252
- [`get_plan_error`](#get_plan_error) — function · specification line 257
- [`get_Annuity_Amount`](#get_annuity_amount) — function · specification line 260
- [`get_Pym_Startdate`](#get_pym_startdate) — function · specification line 265
- [`is_Payment_Date`](#is_payment_date) — function · specification line 285
- [`do_plan_control`](#do_plan_control) — procedure · specification line 337
- [`do_schedule_allignment`](#do_schedule_allignment) — procedure · specification line 438
- [`do_com_schedule_allignment`](#do_com_schedule_allignment) — procedure · specification line 443
- [`calculate_xirr`](#calculate_xirr) — function · specification line 467
- [`get_min_flow_ratio`](#get_min_flow_ratio) — function · specification line 475
- [`get_flow_ratio_info`](#get_flow_ratio_info) — function · specification line 499
- [`get_stop_ratio_info`](#get_stop_ratio_info) — function · specification line 504
- [`get_incorrect_days`](#get_incorrect_days) — function · specification line 510
- [`get_incorrect_days_count`](#get_incorrect_days_count) — function · specification line 513
- [`get_schedule_from_memo`](#get_schedule_from_memo) — function · specification line 515
- [`get_standart_schedule`](#get_standart_schedule) — function · specification line 521
- [`get_annuity_schedule`](#get_annuity_schedule) — function · specification line 542
- [`get_created_schedule`](#get_created_schedule) — procedure · specification line 570
- [`create_schedule`](#create_schedule) — procedure · specification line 574

### Payments & Allocation

- [`recalculate_int_payment_plan`](#recalculate_int_payment_plan) — procedure · specification line 311
- [`generate_allocated_payment_list`](#generate_allocated_payment_list) — procedure · specification line 358
- [`add_payment_details`](#add_payment_details) — procedure · specification line 364
- [`do_Auto_Payment`](#do_auto_payment) — procedure · specification line 370

### Journal & Vouchers

- [`get_trn_caller_id`](#get_trn_caller_id) — function · specification line 144
- [`get_voucher_data_from_query`](#get_voucher_data_from_query) — function · specification line 146
- [`do_journal_entry`](#do_journal_entry) — procedure · specification line 294
- [`create_journal_entries`](#create_journal_entries) — procedure · specification line 300
- [`do_commission_recognition`](#do_commission_recognition) — procedure · specification line 416
- [`do_journal_control`](#do_journal_control) — procedure · specification line 428

### History & Changes

- [`clear_addtional_data`](#clear_addtional_data) — procedure · specification line 109
- [`add_additional_group`](#add_additional_group) — procedure · specification line 111
- [`end_additional_group`](#end_additional_group) — procedure · specification line 113
- [`end_additional_main_group`](#end_additional_main_group) — procedure · specification line 114
- [`add_additional_info`](#add_additional_info--overload-1) — procedure (overload 1) · specification line 115
- [`add_additional_info`](#add_additional_info--overload-2) — procedure (overload 2) · specification line 117
- [`add_column_update`](#add_column_update--overload-1) — procedure (overload 1) · specification line 118
- [`add_column_update`](#add_column_update--overload-2) — procedure (overload 2) · specification line 122
- [`finalize_addtional_process`](#finalize_addtional_process) — procedure · specification line 125
- [`reverse_update`](#reverse_update) — procedure · specification line 128
- [`table_log_operation`](#table_log_operation) — procedure · specification line 289
- [`create_loan_history`](#create_loan_history) — procedure · specification line 343
- [`do_delete_operation`](#do_delete_operation) — procedure · specification line 368

### EOD/SOD & Operations

- [`do_loan_collateral_out`](#do_loan_collateral_out) — procedure · specification line 352
- [`do_int_calculation`](#do_int_calculation) — procedure · specification line 382
- [`do_int_calculation_ex`](#do_int_calculation_ex) — procedure · specification line 396
- [`do_overdue_transit_operation`](#do_overdue_transit_operation) — procedure · specification line 402
- [`do_guarantee_out`](#do_guarantee_out) — procedure · specification line 418
- [`do_Loan_Close_With_Collateral_Out`](#do_loan_close_with_collateral_out) — procedure · specification line 422
- [`do_non_cash_loan_close`](#do_non_cash_loan_close) — procedure · specification line 424
- [`stop_eod_task`](#stop_eod_task) — procedure · specification line 455
- [`stop_loan_task`](#stop_loan_task) — procedure · specification line 457
- [`run_loan_task`](#run_loan_task) — procedure · specification line 460
- [`do_loan_control`](#do_loan_control--overload-1) — procedure (overload 1) · specification line 604
- [`do_loan_control`](#do_loan_control--overload-2) — procedure (overload 2) · specification line 607

### Utilities & Configuration

- [`get_next_Plan_Pym`](#get_next_plan_pym) — function · specification line 215

---

## Method Documentation

Each entry includes the original signature, parameter semantics, evidence from the implementation, business considerations, related database objects, exceptions and operational cautions.


<a id="get_pen_info_for_calc--overload-1"></a>

### `get_pen_info_for_calc` — PROCEDURE (overload 1)

**Purpose:** Computes overdue amount and days for the requested account-type group, applying penalty grace days.

**Business Logic**

Computes overdue amount and days for the requested account-type group, applying penalty grace days.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.

**Business Rules / Preconditions**

- Grace days influence when scheduled unpaid amounts qualify as overdue.
- The implementation rejects negative overdue amounts or negative day counts.

**Public Signature**

```sql
procedure get_pen_info_for_calc(p_date                   in date default glbl.getsysdate,
p_doc_no                 in varchar2,
p_acc_type               in varchar2,
p_pen_calc_grace_days    in number,
p_ovd_amount             out number,
p_calculated_pen_day_cnt out number);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_date` | IN | `date default glbl.getsysdate` | Relevant calculation or operation date |
| `p_doc_no` | IN | `varchar2` | Loan document reference |
| `p_acc_type` | IN | `varchar2` | Loan account type or account-type group |
| `p_pen_calc_grace_days` | IN | `number` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_ovd_amount` | OUT | `number` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_calculated_pen_day_cnt` | OUT | `number` | Context-specific parameter; confirm accepted values with the owning developer. |

**Outputs:** `p_ovd_amount`, `p_calculated_pen_day_cnt`

**Related Database Objects**

- Observed reads: `LOAN_PAYMENT_PLAN`.

**Error Handling**

- Observed message or error code: `Overdue Main amount for penalty calculation or overdue days count is negative!`

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment; delegated operations may still modify data.

**Source Evidence:** Specification line 73; body declaration approximately line 70.

[↑ Back to index](#navigation)

---

<a id="get_interest_calc_dates"></a>

### `get_interest_calc_dates` — FUNCTION

**Purpose:** Returns the dates eligible for interest calculation across the current EOD/SOD processing window.

**Business Logic**

Returns the dates eligible for interest calculation across the current EOD/SOD processing window.
Observed delegated calls include `LOAN_API.G_DATE_TAB_TYPE`, `GLBL_TARIH.AYBASI`, `GLBL_TARIH.SONRAKI_ISGUNU`.

**Business Rules / Preconditions**

- `p_int_calc_at` must be `EOD` or `SOD`.
- `p_eod_sod` must be `E` or `S`.
- The returned dates depend on working-day and month-boundary logic.

**Public Signature**

```sql
function get_interest_calc_dates(p_last_calc_access_date in date,
p_eod_sod               in varchar2,
p_int_calc_at           in varchar2)
return loan_api.g_date_tab_type;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_last_calc_access_date` | IN | `date` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_eod_sod` | IN | `varchar2` | End-of-day (`E`) or start-of-day (`S`) indicator (where supported) |
| `p_int_calc_at` | IN | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |

**Return Value:** `loan_api.g_date_tab_type`. Business interpretation: Returns the dates eligible for interest calculation across the current EOD/SOD processing window.

**Related Database Objects**

- No direct static SQL dependencies identified in the isolated routine segment; dependencies may occur through called packages or dynamic SQL.

**Error Handling**

- Observed message or error code: `p_int_calc_at param should be EOD or SOD!!`
- Observed message or error code: `P_EOD_SOD param should be E - EOD or S - SOD!!`
- Observed message or error code: `Interest calculation should be done at EOD or SOD!!`

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 80; body declaration approximately line 259.

[↑ Back to index](#navigation)

---

<a id="get_interest_calc_dates_ex"></a>

### `get_interest_calc_dates_ex` — FUNCTION

**Purpose:** Returns interest-calculation dates for an explicitly supplied processing date.

**Business Logic**

Returns interest-calculation dates for an explicitly supplied processing date.
Observed delegated calls include `GLBL_TARIH.AYBASI`, `GLBL_TARIH.SONRAKI_ISGUNU`.

**Business Rules / Preconditions**

- `p_int_calc_at` must be `EOD` or `SOD`; `p_eod_sod` must be `E` or `S`.

**Public Signature**

```sql
function get_interest_calc_dates_ex(p_date        in date,
p_eod_sod     in varchar2,
p_int_calc_at in varchar2)
return g_date_tab_type;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_date` | IN | `date` | Relevant calculation or operation date |
| `p_eod_sod` | IN | `varchar2` | End-of-day (`E`) or start-of-day (`S`) indicator (where supported) |
| `p_int_calc_at` | IN | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |

**Return Value:** `g_date_tab_type`. Business interpretation: Returns interest-calculation dates for an explicitly supplied processing date.

**Related Database Objects**

- No direct static SQL dependencies identified in the isolated routine segment; dependencies may occur through called packages or dynamic SQL.

**Error Handling**

- Observed message or error code: `p_int_calc_at param should be EOD or SOD!!`
- Observed message or error code: `P_EOD_SOD param should be E - EOD or S - SOD!!`
- Observed message or error code: `Interest calculation should be done at EOD or SOD!!`

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 85; body declaration approximately line 324.

[↑ Back to index](#navigation)

---

<a id="get_interest_calc_info"></a>

### `get_interest_calc_info` — PROCEDURE

**Purpose:** Computes interest-accrual day count and year basis using configured rate and day-count conventions.

**Business Logic**

Computes interest-accrual day count and year basis using configured rate and day-count conventions.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.

**Business Rules / Preconditions**

- Payment day is required.
- Transaction date earlier than last calculation date is rejected.
- Day-count convention is read from `LOAN_INT_CALC_TYPES_PR`.

**Public Signature**

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

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_last_calc_date` | IN | `date` | Last interest calculation date |
| `p_pymt_day` | IN | `number` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_trn_date` | IN | `date` | Transaction date |
| `p_int_calc_type` | IN | `varchar2` | Interest day-count/calculation convention |
| `p_rate_type` | IN | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_int_rate_periodicity` | IN | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_calc_day_count` | OUT | `number` | Computed accrual day count |
| `p_year_day_count` | OUT | `number` | Computed annual day-count basis |

**Outputs:** `p_calc_day_count`, `p_year_day_count`

**Related Database Objects**

- Observed reads: `LOAN_INT_CALC_TYPES_PR`.

**Error Handling**

- Observed message or error code: `Payment day cant be null, please check!`
- Observed message or error code: `error encountered in search of interest calculation type: `
- Observed message or error code: `Transaction date cant be less than last calculation date!`

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment; delegated operations may still modify data.

**Source Evidence:** Specification line 90; body declaration approximately line 104.

[↑ Back to index](#navigation)

---

<a id="get_interest_calc_info_ex"></a>

### `get_interest_calc_info_ex` — PROCEDURE

**Purpose:** Computes accrual day count and year basis from an interest calculation type.

**Business Logic**

Computes accrual day count and year basis from an interest calculation type.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
procedure get_interest_calc_info_ex(p_last_calc_date in date,
p_pymt_day       in number,
p_trn_date       in date,
p_int_calc_type  in varchar2,
p_calc_day_count out number,
p_year_day_count out number);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_last_calc_date` | IN | `date` | Last interest calculation date |
| `p_pymt_day` | IN | `number` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_trn_date` | IN | `date` | Transaction date |
| `p_int_calc_type` | IN | `varchar2` | Interest day-count/calculation convention |
| `p_calc_day_count` | OUT | `number` | Computed accrual day count |
| `p_year_day_count` | OUT | `number` | Computed annual day-count basis |

**Outputs:** `p_calc_day_count`, `p_year_day_count`

**Related Database Objects**

- Observed reads: `LOAN_INT_CALC_TYPES_PR`.

**Error Handling**

- Observed message or error code: `error encountered in search of interest calculation type: `
- Observed message or error code: `Payment day cant be null, please check!`
- Observed message or error code: `Transaction date cant be less than last calculation date!`

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment; delegated operations may still modify data.

**Source Evidence:** Specification line 101; body declaration approximately line 183.

[↑ Back to index](#navigation)

---

<a id="clear_addtional_data"></a>

### `clear_addtional_data` — PROCEDURE

**Purpose:** Initializes the additional-information JSON and resets pending loan change-tracking buffers.

**Business Logic**

Initializes the additional-information JSON and resets pending loan change-tracking buffers.
Observed delegated calls include `RUHA3H.LOG`.

**Business Rules / Preconditions**

- **Verify:** Accepted codes, required upstream states, and boundary conditions are not fully specified in the package specification.

**Public Signature**

```sql
procedure clear_addtional_data(p_state varchar2 default 'CLEAR');
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_state` | IN | `varchar2 default 'CLEAR'` | Context-specific parameter; confirm accepted values with the owning developer. |

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- No direct static SQL dependencies identified in the isolated routine segment; dependencies may occur through called packages or dynamic SQL.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment; delegated operations may still modify data.

**Source Evidence:** Specification line 109; body declaration approximately line 379.

[↑ Back to index](#navigation)

---

<a id="add_additional_group"></a>

### `add_additional_group` — PROCEDURE

**Purpose:** Opens a named JSON object to group additional loan operation details.

**Business Logic**

Opens a named JSON object to group additional loan operation details.

**Business Rules / Preconditions**

- **Verify:** Accepted codes, required upstream states, and boundary conditions are not fully specified in the package specification.

**Public Signature**

```sql
procedure add_additional_group(p_tag_name varchar2 default null);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_tag_name` | IN | `varchar2 default null` | Context-specific parameter; confirm accepted values with the owning developer. |

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- No direct static SQL dependencies identified in the isolated routine segment; dependencies may occur through called packages or dynamic SQL.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment; delegated operations may still modify data.

**Source Evidence:** Specification line 111; body declaration approximately line 404.

[↑ Back to index](#navigation)

---

<a id="end_additional_group"></a>

### `end_additional_group` — PROCEDURE

**Purpose:** Closes the current JSON object in the additional-information structure.

**Business Logic**

Closes the current JSON object in the additional-information structure.

**Business Rules / Preconditions**

- **Verify:** Accepted codes, required upstream states, and boundary conditions are not fully specified in the package specification.

**Public Signature**

```sql
procedure end_additional_group;
```

**Parameters**

No parameters.

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- No direct static SQL dependencies identified in the isolated routine segment; dependencies may occur through called packages or dynamic SQL.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment; delegated operations may still modify data.

**Source Evidence:** Specification line 113; body declaration approximately line 410.

[↑ Back to index](#navigation)

---

<a id="end_additional_main_group"></a>

### `end_additional_main_group` — PROCEDURE

**Purpose:** Closes the current JSON array in the additional-information structure.

**Business Logic**

Closes the current JSON array in the additional-information structure.

**Business Rules / Preconditions**

- **Verify:** Accepted codes, required upstream states, and boundary conditions are not fully specified in the package specification.

**Public Signature**

```sql
procedure end_additional_main_group;
```

**Parameters**

No parameters.

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- No direct static SQL dependencies identified in the isolated routine segment; dependencies may occur through called packages or dynamic SQL.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment; delegated operations may still modify data.

**Source Evidence:** Specification line 114; body declaration approximately line 398.

[↑ Back to index](#navigation)

---

<a id="add_additional_info--overload-1"></a>

### `add_additional_info` — PROCEDURE (overload 1)

**Purpose:** Writes a text-valued tag into the loan operation's additional-information JSON.

**Business Logic**

Writes a text-valued tag into the loan operation's additional-information JSON.
The observed implementation modifies database records; this is **not** a read-only routine. Review transaction and rollback behavior before calling it.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
procedure add_additional_info(p_tag_name varchar2, p_value varchar2);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_tag_name` | IN | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_value` | IN | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- Observed writes: `OPERATIONS.`.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- Performs data modification in its observed body segment. Do not assume automatic rollback or commit; verify transaction ownership.

**Source Evidence:** Specification line 115; body declaration approximately line 416.

[↑ Back to index](#navigation)

---

<a id="add_additional_info--overload-2"></a>

### `add_additional_info` — PROCEDURE (overload 2)

**Purpose:** Writes a date-valued tag in the additional-information JSON after date formatting.

**Business Logic**

Writes a date-valued tag in the additional-information JSON after date formatting.

**Business Rules / Preconditions**

- **Verify:** Accepted codes, required upstream states, and boundary conditions are not fully specified in the package specification.

**Public Signature**

```sql
procedure add_additional_info(p_tag_name varchar2, p_value date);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_tag_name` | IN | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_value` | IN | `date` | Context-specific parameter; confirm accepted values with the owning developer. |

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- No direct static SQL dependencies identified in the isolated routine segment; dependencies may occur through called packages or dynamic SQL.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment; delegated operations may still modify data.

**Source Evidence:** Specification line 117; body declaration approximately line 428.

[↑ Back to index](#navigation)

---

<a id="add_column_update--overload-1"></a>

### `add_column_update` — PROCEDURE (overload 1)

**Purpose:** Stages a text-valued, mapped old/new column change for loan operation history and update handling.

**Business Logic**

Stages a text-valued, mapped old/new column change for loan operation history and update handling.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
The observed implementation modifies database records; this is **not** a read-only routine. Review transaction and rollback behavior before calling it.

**Business Rules / Preconditions**

- The tag must be declared in `LOAN_HISTORY_MAPPING`.
- Change collection must be initialized before adding updates.

**Public Signature**

```sql
procedure add_column_update(p_tag_name  varchar2,
p_old_value varchar2,
p_new_value varchar2);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_tag_name` | IN | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_old_value` | IN | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_new_value` | IN | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- Observed reads: `LOAN_HISTORY_MAPPING`.
- Observed writes: `OPERATIONS.`.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- Performs data modification in its observed body segment. Do not assume automatic rollback or commit; verify transaction ownership.

**Source Evidence:** Specification line 118; body declaration approximately line 434.

[↑ Back to index](#navigation)

---

<a id="add_column_update--overload-2"></a>

### `add_column_update` — PROCEDURE (overload 2)

**Purpose:** Stages a date-valued, mapped old/new column change for loan operation history and update handling.

**Business Logic**

Stages a date-valued, mapped old/new column change for loan operation history and update handling.

**Business Rules / Preconditions**

- The tag must be declared in `LOAN_HISTORY_MAPPING`.
- Change collection must be initialized before adding updates.

**Public Signature**

```sql
procedure add_column_update(p_tag_name  varchar2,
p_old_value date,
p_new_value date);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_tag_name` | IN | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_old_value` | IN | `date` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_new_value` | IN | `date` | Context-specific parameter; confirm accepted values with the owning developer. |

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- No direct static SQL dependencies identified in the isolated routine segment; dependencies may occur through called packages or dynamic SQL.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment; delegated operations may still modify data.

**Source Evidence:** Specification line 122; body declaration approximately line 471.

[↑ Back to index](#navigation)

---

<a id="finalize_addtional_process"></a>

### `finalize_addtional_process` — PROCEDURE

**Purpose:** Finalizes tracked loan changes, records old/new values in JSON and executes mapped table updates.

**Business Logic**

Finalizes tracked loan changes, records old/new values in JSON and executes mapped table updates.

**Business Rules / Preconditions**

- Only mapped tables and supported data types are expected.
- The implementation builds dynamic SQL; escaping, validation, and transaction ownership require a security review.

**Public Signature**

```sql
procedure finalize_addtional_process(p_doc_no   varchar2,
p_offer_id varchar2);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_doc_no` | IN | `varchar2` | Loan document reference |
| `p_offer_id` | IN | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- No direct static SQL dependencies identified in the isolated routine segment; dependencies may occur through called packages or dynamic SQL.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment; delegated operations may still modify data.
- **Security review:** Dynamic SQL is involved. Restrict query text or mapped values to trusted, validated inputs.

**Source Evidence:** Specification line 125; body declaration approximately line 480.

[↑ Back to index](#navigation)

---

<a id="reverse_update"></a>

### `reverse_update` — PROCEDURE

**Purpose:** Reverses mapped loan changes using previous operation-history data.

**Business Logic**

Reverses mapped loan changes using previous operation-history data.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
Observed delegated calls include `L_OBJ.GET`, `L_OLD.GET_STRING`.

**Business Rules / Preconditions**

- Reads the old/new change data from `LOAN_OPERATION_HISTORY` for the given transaction.

**Public Signature**

```sql
procedure reverse_update(p_tx_fid number);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_tx_fid` | IN | `number` | Transaction identifier |

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- Observed reads: `KRD_TEKLIF_DETAY`, `LOAN_OPERATION_HISTORY`.

**Error Handling**

- Observed message or error code: `Can not get additional info in [loan_operation_history] with tx fid [`
- Observed message or error code: `Can not get find loan[`

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment; delegated operations may still modify data.
- **Operational caution:** Test with non-production data and approved transaction controls. Never execute examples against live financial records without authorization.

**Source Evidence:** Specification line 128; body declaration approximately line 591.

[↑ Back to index](#navigation)

---

<a id="get_loan_amount"></a>

### `get_loan_amount` — FUNCTION

**Purpose:** Returns a loan's TOTAL balance, payable DEBT, or currently DUE amount based on configuration.

**Business Logic**

Returns a loan's TOTAL balance, payable DEBT, or currently DUE amount based on configuration.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
Observed delegated calls include `LOAN_API.GET_PLAN_PAYMENT_AMOUNT`, `P.ACC_TYPE`, `O.PARAM_ID`, `O.TYPE_ID`.

**Business Rules / Preconditions**

- `p_amount_type` accepts `TOTAL`, `DEBT`, or `DUE`.
- For `DUE`, configured allocation type determines whether current balance or scheduled payment is used.
- Missing account-type or payment-order configuration can raise an application error.

**Public Signature**

```sql
function get_loan_amount(p_doc_no      in varchar2,
p_amount_type in varchar2,
p_date        in date default glbl.getsysdate,
p_oper_type   in varchar2 default null)
return number;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_doc_no` | IN | `varchar2` | Loan document reference |
| `p_amount_type` | IN | `varchar2` | Amount mode |
| `p_date` | IN | `date default glbl.getsysdate` | Relevant calculation or operation date |
| `p_oper_type` | IN | `varchar2 default null` | Operation code used for routing or validation |

**Return Value:** `number`. Business interpretation: Returns a loan's TOTAL balance, payable DEBT, or currently DUE amount based on configuration.

**Related Database Objects**

- Observed reads: `CS_ACCOUNT`, `IN_LIST`.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 130; body declaration approximately line 643.

[↑ Back to index](#navigation)

---

<a id="get_overdue_min_amount"></a>

### `get_overdue_min_amount` — FUNCTION

**Purpose:** Reads the product-specific minimum overdue amount from product configuration.

**Business Logic**

Reads the product-specific minimum overdue amount from product configuration.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.

**Business Rules / Preconditions**

- Product code must exist in `PKRD_TURKOD_PR`; missing products raise a message-driven error.

**Public Signature**

```sql
function get_overdue_min_amount(p_product_code in number) return number;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_product_code` | IN | `number` | Loan product code |

**Return Value:** `number`. Business interpretation: Reads the product-specific minimum overdue amount from product configuration.

**Related Database Objects**

- Observed reads: `PKRD_TURKOD_PR`.

**Error Handling**

- Observed message or error code: `Product code `
- Observed message or error code: `Error encountered in search of Product code `

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 136; body declaration approximately line 719.

[↑ Back to index](#navigation)

---

<a id="get_pen_info_for_calc--overload-2"></a>

### `get_pen_info_for_calc` — PROCEDURE (overload 2)

**Purpose:** Calculates a penalty base using overdue principal and a configured percentage, and returns overdue day count.

**Business Logic**

Calculates a penalty base using overdue principal and a configured percentage, and returns overdue day count.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.

**Business Rules / Preconditions**

- Grace days influence when scheduled unpaid amounts qualify as overdue.
- The implementation rejects negative overdue amounts or negative day counts.

**Public Signature**

```sql
procedure get_pen_info_for_calc(p_date                in date default glbl.getsysdate,
p_doc_no              in varchar2,
p_pen_calc_grace_days in number,
p_PEN_INT_RATIO       in number,
p_ovd_amount_for_pen  out number,
p_pen_calc_days_count out number);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_date` | IN | `date default glbl.getsysdate` | Relevant calculation or operation date |
| `p_doc_no` | IN | `varchar2` | Loan document reference |
| `p_pen_calc_grace_days` | IN | `number` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_PEN_INT_RATIO` | IN | `number` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_ovd_amount_for_pen` | OUT | `number` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_pen_calc_days_count` | OUT | `number` | Context-specific parameter; confirm accepted values with the owning developer. |

**Outputs:** `p_ovd_amount_for_pen`, `p_pen_calc_days_count`

**Related Database Objects**

- Observed reads: `LOAN_PAYMENT_PLAN`.

**Error Handling**

- Observed message or error code: `Overdue Main amount for penalty calculation or overdue days count is negative!`

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment; delegated operations may still modify data.

**Source Evidence:** Specification line 137; body declaration approximately line 736.

[↑ Back to index](#navigation)

---

<a id="get_trn_caller_id"></a>

### `get_trn_caller_id` — FUNCTION

**Purpose:** Resolves the transaction caller identifier for a configured loan operation type.

**Business Logic**

Resolves the transaction caller identifier for a configured loan operation type.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.

**Business Rules / Preconditions**

- **Verify:** Accepted codes, required upstream states, and boundary conditions are not fully specified in the package specification.

**Public Signature**

```sql
function get_trn_caller_id(p_oper_type in varchar2) return number;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_oper_type` | IN | `varchar2` | Operation code used for routing or validation |

**Return Value:** `number`. Business interpretation: Resolves the transaction caller identifier for a configured loan operation type.

**Related Database Objects**

- Observed reads: `LOAN_OPERATION_DESC`.

**Error Handling**

- Observed message or error code: `Operation type `
- Observed message or error code: `Error encountered in search of Operation type `

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 144; body declaration approximately line 772.

[↑ Back to index](#navigation)

---

<a id="get_voucher_data_from_query"></a>

### `get_voucher_data_from_query` — FUNCTION

**Purpose:** Executes a voucher-related SQL query and maps resulting columns to grouped voucher values.

**Business Logic**

Executes a voucher-related SQL query and maps resulting columns to grouped voucher values.

**Business Rules / Preconditions**

- `p_result_type` is `SINGLE_ROW` or `MULTI_ROW`.
- The supplied SQL is dynamically parsed with `DBMS_SQL`; queries must be strictly controlled and reviewed.

**Public Signature**

```sql
function get_voucher_data_from_query(p_query       in varchar2,
p_result_type in varchar2)
return g_col_value_tab_map;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_query` | IN | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_result_type` | IN | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |

**Return Value:** `g_col_value_tab_map`. Business interpretation: Executes a voucher-related SQL query and maps resulting columns to grouped voucher values.

**Related Database Objects**

- No direct static SQL dependencies identified in the isolated routine segment; dependencies may occur through called packages or dynamic SQL.

**Error Handling**

- Observed message or error code: `-20001`

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.
- **Security review:** Dynamic SQL is involved. Restrict query text or mapped values to trusted, validated inputs.

**Source Evidence:** Specification line 146; body declaration approximately line 789.

[↑ Back to index](#navigation)

---

<a id="get_formatted_grace_from_list"></a>

### `get_formatted_grace_from_list` — FUNCTION

**Purpose:** Formats a grace-period specification from a stored period list.

**Business Logic**

Formats a grace-period specification from a stored period list.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
function get_formatted_grace_from_list(p_period_list in varchar2)
return varchar2;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_period_list` | IN | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |

**Return Value:** `varchar2`. Business interpretation: Formats a grace-period specification from a stored period list.

**Related Database Objects**

- No direct static SQL dependencies identified in the isolated routine segment; dependencies may occur through called packages or dynamic SQL.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 150; body declaration approximately line 912.

[↑ Back to index](#navigation)

---

<a id="get_grace_info"></a>

### `get_grace_info` — FUNCTION

**Purpose:** Retrieves grace-period information for a loan, date and account category.

**Business Logic**

Retrieves grace-period information for a loan, date and account category.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
Observed delegated calls include `LOAN_API.GET_FORMATTED_GRACE_FROM_LIST`.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
function get_grace_info(p_Doc_No          In Varchar2,
p_period_end_date in date,
p_acc_type        In Varchar2 default 'A',
p_info_type       in varchar2) Return varchar2;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_Doc_No` | IN | `Varchar2` | Loan document reference |
| `p_period_end_date` | IN | `date` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_acc_type` | IN | `Varchar2 default 'A'` | Loan account type or account-type group |
| `p_info_type` | IN | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |

**Return Value:** `varchar2`. Business interpretation: Retrieves grace-period information for a loan, date and account category.

**Related Database Objects**

- Observed reads: `LOAN_PAYMENT_PLAN`.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 153; body declaration approximately line 952.

[↑ Back to index](#navigation)

---

<a id="get_basis_year_days_cnt"></a>

### `get_basis_year_days_cnt` — FUNCTION

**Purpose:** Determines the configured interest calculation year-day basis.

**Business Logic**

Determines the configured interest calculation year-day basis.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.

**Business Rules / Preconditions**

- **Verify:** Accepted codes, required upstream states, and boundary conditions are not fully specified in the package specification.

**Public Signature**

```sql
function get_basis_year_days_cnt(p_int_calc_type in varchar2,
p_date          in date) return number;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_int_calc_type` | IN | `varchar2` | Interest day-count/calculation convention |
| `p_date` | IN | `date` | Relevant calculation or operation date |

**Return Value:** `number`. Business interpretation: Determines the configured interest calculation year-day basis.

**Related Database Objects**

- Observed reads: `LOAN_INT_CALC_TYPES_PR`.

**Error Handling**

- Observed message or error code: `Error encountered in search of int calc type `

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 158; body declaration approximately line 998.

[↑ Back to index](#navigation)

---

<a id="get_gl_value"></a>

### `get_gl_value` — FUNCTION

**Purpose:** Returns an accounting configuration value by its parameter name.

**Business Logic**

Returns an accounting configuration value by its parameter name.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.

**Business Rules / Preconditions**

- **Verify:** Accepted codes, required upstream states, and boundary conditions are not fully specified in the package specification.

**Public Signature**

```sql
function get_gl_value(p_parameter_name in varchar2) return varchar2;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_parameter_name` | IN | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |

**Return Value:** `varchar2`. Business interpretation: Returns an accounting configuration value by its parameter name.

**Related Database Objects**

- Observed reads: `LOAN_GLOBAL_PARAMETERS_PR`.

**Error Handling**

- Observed message or error code: `Parameter not found in loan_global_parameters_pr table!`
- Observed message or error code: `Too many rows in search of parameter in loan_global_parameters_pr table!`
- Observed message or error code: `Encountered error in search of parameter in loan_global_parameters_pr table!`

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 161; body declaration approximately line 1026.

[↑ Back to index](#navigation)

---

<a id="loan_int_diff_operation"></a>

### `loan_int_diff_operation` — PROCEDURE

**Purpose:** Processes the difference between scheduled and calculated loan interest in transaction context.

**Business Logic**

Processes the difference between scheduled and calculated loan interest in transaction context.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
The observed implementation modifies database records; this is **not** a read-only routine. Review transaction and rollback behavior before calling it.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

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

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_trn_date` | IN | `date` | Transaction date |
| `p_oper_type` | IN | `varchar2` | Operation code used for routing or validation |
| `p_trn_type` | IN | `varchar2` | Transaction action/type |
| `p_doc_no` | IN | `varchar2` | Loan document reference |
| `p_acc_type` | IN | `varchar2` | Loan account type or account-type group |
| `p_source_acc_type` | IN | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_tx_fid` | IN | `number` | Transaction identifier |
| `p_original_amount` | IN | `number` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_eod_sod` | IN | `varchar2` | End-of-day (`E`) or start-of-day (`S`) indicator (where supported) |
| `p_payment_date` | IN | `date` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_plan_int_amount` | IN | `number` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_int_amount` | IN | `number` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_calc_amount` | OUT | `number` | Context-specific parameter; confirm accepted values with the owning developer. |

**Outputs:** `p_calc_amount`

**Related Database Objects**

- Observed reads: `LOAN_INT_CALCULATION_DIFF_HISTORY`.
- Observed writes: `LOAN_INT_CALCULATION_DIFF_HISTORY`.

**Error Handling**

- Observed message or error code: `p_tx_fid or p_doc_no or p_acc_type or p_eod_sod cant be null!`
- Observed message or error code: `Operation type must be INS, OPEN, CLOSE!`

**Side Effects & Transaction Notes**

- Performs data modification in its observed body segment. Do not assume automatic rollback or commit; verify transaction ownership.

**Source Evidence:** Specification line 163; body declaration approximately line 1043.

[↑ Back to index](#navigation)

---

<a id="loan_int_diff_operation_ex"></a>

### `loan_int_diff_operation_ex` — PROCEDURE

**Purpose:** Processes a variant of loan interest differences with a reduced parameter set.

**Business Logic**

Processes a variant of loan interest differences with a reduced parameter set.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
The observed implementation modifies database records; this is **not** a read-only routine. Review transaction and rollback behavior before calling it.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
procedure loan_int_diff_operation_ex(p_oper_type       in varchar2,
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

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_oper_type` | IN | `varchar2` | Operation code used for routing or validation |
| `p_doc_no` | IN | `varchar2` | Loan document reference |
| `p_acc_type` | IN | `varchar2` | Loan account type or account-type group |
| `p_source_acc_type` | IN | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_tx_fid` | IN | `number` | Transaction identifier |
| `p_original_amount` | IN | `number` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_eod_sod` | IN | `varchar2` | End-of-day (`E`) or start-of-day (`S`) indicator (where supported) |
| `p_payment_date` | IN | `date` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_plan_int_amount` | IN | `number` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_int_amount` | IN | `number` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_calc_amount` | OUT | `number` | Context-specific parameter; confirm accepted values with the owning developer. |

**Outputs:** `p_calc_amount`

**Related Database Objects**

- Observed reads: `LOAN_INT_CALCULATION_DIFF_HISTORY`.
- Observed writes: `LOAN_INT_CALCULATION_DIFF_HISTORY`.

**Error Handling**

- Observed message or error code: `p_tx_fid or p_doc_no or p_acc_type or p_eod_sod cant be null!`
- Observed message or error code: `Operation type must be INS, OPEN, CLOSE!`

**Side Effects & Transaction Notes**

- Performs data modification in its observed body segment. Do not assume automatic rollback or commit; verify transaction ownership.

**Source Evidence:** Specification line 177; body declaration approximately line 1197.

[↑ Back to index](#navigation)

---

<a id="get_gl_acc_active_passive"></a>

### `get_gl_acc_active_passive` — FUNCTION

**Purpose:** Determines whether a general-ledger account is active or passive.

**Business Logic**

Determines whether a general-ledger account is active or passive.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.

**Business Rules / Preconditions**

- **Verify:** Accepted codes, required upstream states, and boundary conditions are not fully specified in the package specification.

**Public Signature**

```sql
function get_gl_acc_active_passive(p_acc_no in varchar2) return varchar2 result_cache;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_acc_no` | IN | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |

**Return Value:** `varchar2`. Business interpretation: Determines whether a general-ledger account is active or passive.

**Related Database Objects**

- Observed reads: `GL_ACCOUNT_DEFINE`.

**Error Handling**

- Observed message or error code: `Account_no: `
- Observed message or error code: `Encountered more than one row in gl_account_define 
                              table in search of account_no: `
- Observed message or error code: `Encountered error in gl_account_define 
                              table in search of account_no: `

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 189; body declaration approximately line 1345.

[↑ Back to index](#navigation)

---

<a id="get_gl_acc_from_matrix"></a>

### `get_gl_acc_from_matrix` — FUNCTION

**Purpose:** Resolves a general-ledger account using product, customer, currency, period and account-type criteria.

**Business Logic**

Resolves a general-ledger account using product, customer, currency, period and account-type criteria.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
Observed delegated calls include `GLBL_NAME.GET_CUSTOMER_MUS_TIP`, `GLBL_HESAP.GET_ACCOUNT_PR`.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
function get_gl_acc_from_matrix(p_product_code in number default null,
p_cust_type    in number default null,
p_period_id    in number default null,
p_currency_id  in number default null,
p_base_type    in varchar2,
p_loan_doc_no  in varchar2 default null,
p_customer_no  in varchar2 default null,
p_acc_type     in varchar2) return varchar2 result_cache;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_product_code` | IN | `number default null` | Loan product code |
| `p_cust_type` | IN | `number default null` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_period_id` | IN | `number default null` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_currency_id` | IN | `number default null` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_base_type` | IN | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_loan_doc_no` | IN | `varchar2 default null` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_customer_no` | IN | `varchar2 default null` | Customer identifier |
| `p_acc_type` | IN | `varchar2` | Loan account type or account-type group |

**Return Value:** `varchar2`. Business interpretation: Resolves a general-ledger account using product, customer, currency, period and account-type criteria.

**Related Database Objects**

- Observed reads: `CS_ACCOUNT`, `GAIA.KRD_CARI_URUN_KP_PR`, `GL_URUN_HESAP_PR`, `KRD_TEKLIF_DETAY`, `SP_URUN_PR`.

**Error Handling**

- Observed message or error code: `p_gl_base_type should be MAIN - for main account, OVD_MAIN - for overdue account!`
- Observed message or error code: `Error encountered in search of loan_doc_no: `
- Observed message or error code: `Error encountered in search krd_teklif_detay table of loan_doc_no: `

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 191; body declaration approximately line 1367.

[↑ Back to index](#navigation)

---

<a id="get_delay_int_rate"></a>

### `Get_Delay_Int_Rate` — FUNCTION

**Purpose:** Obtains a loan's delayed-interest rate for a selected delay category.

**Business Logic**

Obtains a loan's delayed-interest rate for a selected delay category.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.

**Business Rules / Preconditions**

- **Verify:** Accepted codes, required upstream states, and boundary conditions are not fully specified in the package specification.

**Public Signature**

```sql
Function Get_Delay_Int_Rate(p_Loan_Id    In Varchar2,
p_Delay_Type In Varchar2) Return Number;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_Loan_Id` | IN | `Varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_Delay_Type` | IN | `Varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |

**Return Value:** `Number`. Business interpretation: Obtains a loan's delayed-interest rate for a selected delay category.

**Related Database Objects**

- Observed reads: `KRD_TEKLIF_DETAY`.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 201; body declaration approximately line 1602.

[↑ Back to index](#navigation)

---

<a id="get_commission_schedule"></a>

### `get_commission_schedule` — FUNCTION

**Purpose:** Generates the commission payment schedule for an amount and period.

**Business Logic**

Generates the commission payment schedule for an amount and period.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
Observed delegated calls include `GLBL_FAIZ.DAYS_BETWEEN2`, `GNI_MESSAGE.GET_MESSAGE`, `GLBL_TARIH.ONCEKI_ISGUNU`.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
Function get_commission_schedule(p_begin_date    In Date,
p_end_date      In Date,
p_amount        In Number,
p_int_calc_type in varchar2)
Return Krd_Kom_Plan_Tt
Pipelined;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_begin_date` | IN | `Date` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_end_date` | IN | `Date` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_amount` | IN | `Number` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_int_calc_type` | IN | `varchar2` | Interest day-count/calculation convention |

**Return Value:** `Krd_Kom_Plan_Tt`. Business interpretation: Generates the commission payment schedule for an amount and period.

**Related Database Objects**

- Observed reads: `L_BITME_TAR`.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 205; body declaration approximately line 1628.

[↑ Back to index](#navigation)

---

<a id="add_months_for_loan"></a>

### `add_months_for_loan` — FUNCTION

**Purpose:** Adjusts a loan date by a number of months with optional target payment day handling.

**Business Logic**

Adjusts a loan date by a number of months with optional target payment day handling.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
function add_months_for_loan(p_date   date,
p_months number,
p_day    number default null) return date;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_date` | IN | `date` | Relevant calculation or operation date |
| `p_months` | IN | `number` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_day` | IN | `number default null` | Context-specific parameter; confirm accepted values with the owning developer. |

**Return Value:** `date`. Business interpretation: Adjusts a loan date by a number of months with optional target payment day handling.

**Related Database Objects**

- Observed reads: `L_DATE`, `L_LAST_DATE`.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 211; body declaration approximately line 1744.

[↑ Back to index](#navigation)

---

<a id="get_next_plan_pym"></a>

### `get_next_Plan_Pym` — FUNCTION

**Purpose:** Determines the next planned payment amount for a loan account type.

**Business Logic**

Determines the next planned payment amount for a loan account type.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.

**Business Rules / Preconditions**

- **Verify:** Accepted codes, required upstream states, and boundary conditions are not fully specified in the package specification.

**Public Signature**

```sql
Function get_next_Plan_Pym(p_doc_no   In Varchar2,
P_date     In Date,
p_acc_type in varchar2) Return Number;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_doc_no` | IN | `Varchar2` | Loan document reference |
| `P_date` | IN | `Date` | Relevant calculation or operation date |
| `p_acc_type` | IN | `varchar2` | Loan account type or account-type group |

**Return Value:** `Number`. Business interpretation: Determines the next planned payment amount for a loan account type.

**Related Database Objects**

- Observed reads: `LOAN_PAYMENT_PLAN`.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 215; body declaration approximately line 1776.

[↑ Back to index](#navigation)

---

<a id="get_offer_id"></a>

### `get_offer_id` — FUNCTION

**Purpose:** Generates or retrieves a loan offer identifier for a branch and date.

**Business Logic**

Generates or retrieves a loan offer identifier for a branch and date.
The observed implementation modifies database records; this is **not** a read-only routine. Review transaction and rollback behavior before calling it.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
Function get_offer_id(p_branch_id In Number Default Glbl.Getsube,
P_date      In Date Default Glbl.Getsysdate)
Return Varchar2;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_branch_id` | IN | `Number Default Glbl.Getsube` | Branch identifier |
| `P_date` | IN | `Date Default Glbl.Getsysdate` | Relevant calculation or operation date |

**Return Value:** `Varchar2`. Business interpretation: Generates or retrieves a loan offer identifier for a branch and date.

**Related Database Objects**

- Observed writes: `KRD_TEKLIF_NO`.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- Performs data modification in its observed body segment. Do not assume automatic rollback or commit; verify transaction ownership.

**Source Evidence:** Specification line 219; body declaration approximately line 1807.

[↑ Back to index](#navigation)

---

<a id="get_plan_payment_amount"></a>

### `get_plan_payment_amount` — FUNCTION

**Purpose:** Returns the planned payment amount for a date and optional account type.

**Business Logic**

Returns the planned payment amount for a date and optional account type.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.

**Business Rules / Preconditions**

- **Verify:** Accepted codes, required upstream states, and boundary conditions are not fully specified in the package specification.

**Public Signature**

```sql
function get_plan_payment_amount(p_doc_no   in varchar2,
p_date     in date default glbl.getsysdate,
p_acc_type in varchar2 default null)
return number;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_doc_no` | IN | `varchar2` | Loan document reference |
| `p_date` | IN | `date default glbl.getsysdate` | Relevant calculation or operation date |
| `p_acc_type` | IN | `varchar2 default null` | Loan account type or account-type group |

**Return Value:** `number`. Business interpretation: Returns the planned payment amount for a date and optional account type.

**Related Database Objects**

- Observed reads: `LOAN_PAYMENT_PLAN`.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 225; body declaration approximately line 1832.

[↑ Back to index](#navigation)

---

<a id="get_ovd_date"></a>

### `get_ovd_date` — FUNCTION

**Purpose:** Finds the overdue date associated with a loan's account type.

**Business Logic**

Finds the overdue date associated with a loan's account type.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
Observed delegated calls include `LOAN_TRANCHE_API.GET_OVD_DATE`.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
Function get_ovd_date(p_doc_no   varchar2,
p_acc_type varchar2,
p_date     date default glbl.getsysdate) return date;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_doc_no` | IN | `varchar2` | Loan document reference |
| `p_acc_type` | IN | `varchar2` | Loan account type or account-type group |
| `p_date` | IN | `date default glbl.getsysdate` | Relevant calculation or operation date |

**Return Value:** `date`. Business interpretation: Finds the overdue date associated with a loan's account type.

**Related Database Objects**

- Observed reads: `KRD_TESIS`, `LOAN_PAYMENT_PLAN`.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 229; body declaration approximately line 2734.

[↑ Back to index](#navigation)

---

<a id="get_amount_for_pen_calc"></a>

### `get_amount_for_pen_calc` — FUNCTION

**Purpose:** Determines the amount used as the base for penalty calculation.

**Business Logic**

Determines the amount used as the base for penalty calculation.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
Observed delegated calls include `GLBL_FAIZ.DAY_COUNT_BASIS_NEW`.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
Function get_amount_for_pen_calc(p_doc_no        In Varchar2,
P_date          In Date,
p_for_spec_days in varchar2 default 'N',
p_int_calc_type in varchar2 default null)
Return Number;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_doc_no` | IN | `Varchar2` | Loan document reference |
| `P_date` | IN | `Date` | Relevant calculation or operation date |
| `p_for_spec_days` | IN | `varchar2 default 'N'` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_int_calc_type` | IN | `varchar2 default null` | Interest day-count/calculation convention |

**Return Value:** `Number`. Business interpretation: Determines the amount used as the base for penalty calculation.

**Related Database Objects**

- Observed reads: `LOAN_PAYMENT_PLAN`, `LOAN_SPECIAL_DAYS_PR`.

**Error Handling**

- Observed message or error code: `Too many rows in loan_special_days_pr for date: `
- Observed message or error code: `p_for_spec_days must be Y or N!`

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 233; body declaration approximately line 1850.

[↑ Back to index](#navigation)

---

<a id="get_plan_month_count"></a>

### `get_Plan_Month_Count` — FUNCTION

**Purpose:** Calculates the number of payment-plan months between two dates.

**Business Logic**

Calculates the number of payment-plan months between two dates.
Observed delegated calls include `GLBL_FAIZ.DAYS_BETWEEN2`, `LOAN_API.ADD_MONTHS_FOR_LOAN`, `GLBL_TARIH.SONRAKI_ISGUNU`.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
Function get_Plan_Month_Count(p_Start_Date    In Date,
p_End_Date      In Date,
p_int_calc_type varchar2 default '30/360 AZ',
p_work_days     varchar2 default 'Y',
p_pymt_day      number default null)
Return Number;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_Start_Date` | IN | `Date` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_End_Date` | IN | `Date` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_int_calc_type` | IN | `varchar2 default '30/360 AZ'` | Interest day-count/calculation convention |
| `p_work_days` | IN | `varchar2 default 'Y'` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_pymt_day` | IN | `number default null` | Context-specific parameter; confirm accepted values with the owning developer. |

**Return Value:** `Number`. Business interpretation: Calculates the number of payment-plan months between two dates.

**Related Database Objects**

- No direct static SQL dependencies identified in the isolated routine segment; dependencies may occur through called packages or dynamic SQL.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 241; body declaration approximately line 1944.

[↑ Back to index](#navigation)

---

<a id="get_plan_paid_month_count"></a>

### `get_plan_paid_month_count` — FUNCTION

**Purpose:** Determines how many plan months have been paid for the specified loan.

**Business Logic**

Determines how many plan months have been paid for the specified loan.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
function get_plan_paid_month_count(p_doc_no in varchar2,
p_term   in number,
p_date   in date) return number;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_doc_no` | IN | `varchar2` | Loan document reference |
| `p_term` | IN | `number` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_date` | IN | `date` | Relevant calculation or operation date |

**Return Value:** `number`. Business interpretation: Determines how many plan months have been paid for the specified loan.

**Related Database Objects**

- No direct static SQL dependencies identified in the isolated routine segment; dependencies may occur through called packages or dynamic SQL.

**Error Handling**

- Observed message or error code: `Salaaaam`

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 252; body declaration approximately line 1987.

[↑ Back to index](#navigation)

---

<a id="get_plan_error"></a>

### `get_plan_error` — FUNCTION

**Purpose:** Checks the loan payment plan for configured validation errors.

**Business Logic**

Checks the loan payment plan for configured validation errors.

**Business Rules / Preconditions**

- **Verify:** Accepted codes, required upstream states, and boundary conditions are not fully specified in the package specification.

**Public Signature**

```sql
Function get_plan_error(p_doc_no varchar2, p_date date default glbl.getsysdate) return varchar2;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_doc_no` | IN | `varchar2` | Loan document reference |
| `p_date` | IN | `date default glbl.getsysdate` | Relevant calculation or operation date |

**Return Value:** `varchar2`. Business interpretation: Checks the loan payment plan for configured validation errors.

**Related Database Objects**

- No direct static SQL dependencies identified in the isolated routine segment; dependencies may occur through called packages or dynamic SQL.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 257; body declaration approximately line 2047.

[↑ Back to index](#navigation)

---

<a id="get_annuity_amount"></a>

### `get_Annuity_Amount` — FUNCTION

**Purpose:** Obtains a loan's annuity payment amount with configurable handling of zero values.

**Business Logic**

Obtains a loan's annuity payment amount with configurable handling of zero values.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.

**Business Rules / Preconditions**

- **Verify:** Accepted codes, required upstream states, and boundary conditions are not fully specified in the package specification.

**Public Signature**

```sql
Function get_Annuity_Amount(p_Doc_No      In Varchar2,
p_return_type In varchar2 default 'NO_ZERO')
Return Number;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_Doc_No` | IN | `Varchar2` | Loan document reference |
| `p_return_type` | IN | `varchar2 default 'NO_ZERO'` | Context-specific parameter; confirm accepted values with the owning developer. |

**Return Value:** `Number`. Business interpretation: Obtains a loan's annuity payment amount with configurable handling of zero values.

**Related Database Objects**

- Observed reads: `LOAN_PAYMENT_PLAN`.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 260; body declaration approximately line 2604.

[↑ Back to index](#navigation)

---

<a id="get_pym_startdate"></a>

### `get_Pym_Startdate` — FUNCTION

**Purpose:** Computes the applicable start date for scheduled payments.

**Business Logic**

Computes the applicable start date for scheduled payments.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
Observed delegated calls include `GNI_MESSAGE.GET_MESSAGE`, `GLBL_FAIZ.DAYS_BETWEEN2`.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

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

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_Doc_No` | IN | `Varchar2` | Loan document reference |
| `p_pymt_date` | IN | `Date` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_pymt_day` | IN | `Number` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_pymt_period` | IN | `Number` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_acc_type` | IN | `varchar2` | Loan account type or account-type group |
| `p_loan_end_Date` | IN | `date` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_check_is_closed` | IN | `varchar2 default 'Y'` | Context-specific parameter; confirm accepted values with the owning developer. |

**Return Value:** `Date`. Business interpretation: Computes the applicable start date for scheduled payments.

**Related Database Objects**

- Observed reads: `LOAN_PAYMENT_PLAN`.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 265; body declaration approximately line 2633.

[↑ Back to index](#navigation)

---

<a id="get_account_feature"></a>

### `get_account_feature` — FUNCTION

**Purpose:** Returns an account-feature value for a branch, account and subaccount.

**Business Logic**

Returns an account-feature value for a branch, account and subaccount.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.

**Business Rules / Preconditions**

- **Verify:** Accepted codes, required upstream states, and boundary conditions are not fully specified in the package specification.

**Public Signature**

```sql
function get_account_feature(p_branch_no   number,
p_account_no  number,
p_account_sub number)
return cs_account.account_feature%type;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_branch_no` | IN | `number` | Branch identifier |
| `p_account_no` | IN | `number` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_account_sub` | IN | `number` | Context-specific parameter; confirm accepted values with the owning developer. |

**Return Value:** `cs_account.account_feature`. Business interpretation: Returns an account-feature value for a branch, account and subaccount.

**Related Database Objects**

- Observed reads: `CS_ACCOUNT`.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 273; body declaration approximately line 2799.

[↑ Back to index](#navigation)

---

<a id="is_acc_exists"></a>

### `is_acc_exists` — FUNCTION

**Purpose:** Checks whether a related account exists for the supplied customer and loan context.

**Business Logic**

Checks whether a related account exists for the supplied customer and loan context.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
function is_acc_exists(p_customer_no   number,
p_memorandum_id varchar2 default null,
p_doc_no        varchar2,
p_acc_type      varchar2) return varchar2;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_customer_no` | IN | `number` | Customer identifier |
| `p_memorandum_id` | IN | `varchar2 default null` | Memorandum identifier |
| `p_doc_no` | IN | `varchar2` | Loan document reference |
| `p_acc_type` | IN | `varchar2` | Loan account type or account-type group |

**Return Value:** `varchar2`. Business interpretation: Checks whether a related account exists for the supplied customer and loan context.

**Related Database Objects**

- Observed reads: `CS_ACCOUNT`.

**Error Handling**

- Observed message or error code: `in [is_acc_exists] , [acc_type] or [p_customer_no] , can not be null!`

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 278; body declaration approximately line 2818.

[↑ Back to index](#navigation)

---

<a id="is_payment_date"></a>

### `is_Payment_Date` — FUNCTION

**Purpose:** Checks whether a specified date qualifies as a loan payment date.

**Business Logic**

Checks whether a specified date qualifies as a loan payment date.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
Observed delegated calls include `GLBL_TARIH.ONCEKI_ISGUNU`.

**Business Rules / Preconditions**

- **Verify:** Accepted codes, required upstream states, and boundary conditions are not fully specified in the package specification.

**Public Signature**

```sql
Function is_Payment_Date(p_Document_No In Varchar2, p_Date Date)
Return Varchar2;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_Document_No` | IN | `Varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_Date` | IN | `Date` | Relevant calculation or operation date |

**Return Value:** `Varchar2`. Business interpretation: Checks whether a specified date qualifies as a loan payment date.

**Related Database Objects**

- Observed reads: `LOAN_PAYMENT_PLAN`.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 285; body declaration approximately line 2845.

[↑ Back to index](#navigation)

---

<a id="is_online_offer"></a>

### `is_online_offer` — FUNCTION

**Purpose:** Determines whether a memorandum is associated with an online loan offer.

**Business Logic**

Determines whether a memorandum is associated with an online loan offer.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
function is_online_offer(p_memorandum_id varchar2) return varchar2;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_memorandum_id` | IN | `varchar2` | Memorandum identifier |

**Return Value:** `varchar2`. Business interpretation: Determines whether a memorandum is associated with an online loan offer.

**Related Database Objects**

- Observed reads: `KRD_SCOR_MAIN`.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 287; body declaration approximately line 2858.

[↑ Back to index](#navigation)

---

<a id="table_log_operation"></a>

### `table_log_operation` — PROCEDURE

**Purpose:** Logs a loan table operation for a transaction and operation type.

**Business Logic**

Logs a loan table operation for a transaction and operation type.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
The observed implementation modifies database records; this is **not** a read-only routine. Review transaction and rollback behavior before calling it.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
procedure table_log_operation(p_doc_no     in varchar2,
p_table_name in varchar2,
p_tx_fid     in number,
p_oper_type  in varchar2);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_doc_no` | IN | `varchar2` | Loan document reference |
| `p_table_name` | IN | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_tx_fid` | IN | `number` | Transaction identifier |
| `p_oper_type` | IN | `varchar2` | Operation code used for routing or validation |

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- Observed reads: `LOAN_FLOW_RATIO_INFO`, `LOAN_FLOW_RATIO_INFO_LOG`, `LOAN_PAYMENT_PLAN`, `LOAN_PAYMENT_PLAN_LOG`, `LOAN_STOP_RATIO_INFO`, `LOAN_STOP_RATIO_INFO_LOG`.
- Observed writes: `LOAN_FLOW_RATIO_INFO`, `LOAN_FLOW_RATIO_INFO_LOG`, `LOAN_PAYMENT_PLAN`, `LOAN_PAYMENT_PLAN_LOG`, `LOAN_STOP_RATIO_INFO`, `LOAN_STOP_RATIO_INFO_LOG`.

**Error Handling**

- Observed message or error code: `p_tx_fid or p_document_no parameters cant be null!`
- Observed message or error code: `Oper type should be LOGGING-for logging or RESTORING-for restoring`
- Observed message or error code: `Table name should be [LOAN_PAYMENT_PLAN]`

**Side Effects & Transaction Notes**

- Performs data modification in its observed body segment. Do not assume automatic rollback or commit; verify transaction ownership.

**Source Evidence:** Specification line 289; body declaration approximately line 3344.

[↑ Back to index](#navigation)

---

<a id="do_journal_entry"></a>

### `do_journal_entry` — PROCEDURE

**Purpose:** Creates a general-ledger journal entry from supplied debit/credit lines.

**Business Logic**

Creates a general-ledger journal entry from supplied debit/credit lines.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
The observed implementation modifies database records; this is **not** a read-only routine. Review transaction and rollback behavior before calling it.
Observed delegated calls include `TRN_BROKER.REGISTER_EOD`, `TRN_BROKER.SETTXDETAILS`, `PA_API#.CREATE_J_WSQL`, `MM_ACCOUNTING#.POST_JOURNAL`, `TRN_BROKER.SETTXSTATE`.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
Procedure do_journal_entry(p_entries_list  g_entries_list_tab,
p_trn_caller_id in number,
p_tx_fid        in out number,
p_trn_type      in varchar2,
p_is_eod        in varchar2 default 'Y');
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_entries_list` | IN | `g_entries_list_tab` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_trn_caller_id` | IN | `number` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_tx_fid` | IN OUT | `number` | Transaction identifier |
| `p_trn_type` | IN | `varchar2` | Transaction action/type |
| `p_is_eod` | IN | `varchar2 default 'Y'` | Context-specific parameter; confirm accepted values with the owning developer. |

**Outputs:** `p_tx_fid`

**Related Database Objects**

- Observed reads: `PA_VOUCHER`.
- Observed writes: `ENTRIES_LIST_TAB`.

**Error Handling**

- Observed message or error code: `p_trn_type must be CREATE or POST!`
- Observed message or error code: `Sql text for LOAN journal operations not found in [pa_voucher] by voucer id [LOAN]!`

**Side Effects & Transaction Notes**

- Performs data modification in its observed body segment. Do not assume automatic rollback or commit; verify transaction ownership.
- **Operational caution:** Test with non-production data and approved transaction controls. Never execute examples against live financial records without authorization.

**Source Evidence:** Specification line 294; body declaration approximately line 2876.

[↑ Back to index](#navigation)

---

<a id="create_journal_entries"></a>

### `create_journal_entries` — PROCEDURE

**Purpose:** Builds journal entries for a configured loan operation.

**Business Logic**

Builds journal entries for a configured loan operation.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
Observed delegated calls include `LOAN_API.DO_JOURNAL_ENTRY`.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
procedure create_journal_entries(p_oper_type in varchar2,
p_tx_fid    in number,
p_trn_type  in varchar2);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_oper_type` | IN | `varchar2` | Operation code used for routing or validation |
| `p_tx_fid` | IN | `number` | Transaction identifier |
| `p_trn_type` | IN | `varchar2` | Transaction action/type |

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- Observed reads: `LOAN_OPERATION_DESC`, `LOAN_OPERATION_VOUCHER`.

**Error Handling**

- Observed message or error code: `-20001`

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment; delegated operations may still modify data.
- **Operational caution:** Test with non-production data and approved transaction controls. Never execute examples against live financial records without authorization.

**Source Evidence:** Specification line 300; body declaration approximately line 2954.

[↑ Back to index](#navigation)

---

<a id="create_account"></a>

### `create_account` — PROCEDURE

**Purpose:** Creates or associates loan accounts according to loan document, account type and operation.

**Business Logic**

Creates or associates loan accounts according to loan document, account type and operation.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
The observed implementation modifies database records; this is **not** a read-only routine. Review transaction and rollback behavior before calling it.
Observed delegated calls include `GLBL_TARIH.DAYSBETWEEN`, `GLBL_NAME.GET_CUSTOMER_NOVU_CODE`, `GNI_MESSAGE.GET_MESSAGE`, `LOAN_API.GET_GL_ACC_FROM_MATRIX`, `LOAN_API.GET_NEW_ACC`.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
procedure create_account(p_doc_no        in varchar2,
p_memorandum_id in varchar2 default null,
p_oper_type     in varchar2,
p_acc_type      in varchar2 default null,
p_tx_fid        in number,
p_created_acc   out g_loan_accounts_tab);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_doc_no` | IN | `varchar2` | Loan document reference |
| `p_memorandum_id` | IN | `varchar2 default null` | Memorandum identifier |
| `p_oper_type` | IN | `varchar2` | Operation code used for routing or validation |
| `p_acc_type` | IN | `varchar2 default null` | Loan account type or account-type group |
| `p_tx_fid` | IN | `number` | Transaction identifier |
| `p_created_acc` | OUT | `g_loan_accounts_tab` | Output collection of resulting account records |

**Outputs:** `p_created_acc`

**Related Database Objects**

- Observed reads: `IN_LIST`, `KRD_TEKLIF_DETAY`, `KRD_TESIS`, `LOAN_ACCOUNTS`, `LOAN_ACC_TYPES_PR`, `LOAN_API.GET_GL_ACC_FROM_MATRIX`, `SP_FAIZ_GUN_TANIM_PR`.
- Observed writes: `KRD_TEKLIF_DETAY`, `KRD_TESIS`.

**Error Handling**

- Observed message or error code: `-20001`
- Observed message or error code: `Creation scope for acc type [`
- Observed message or error code: `Balance account for `

**Side Effects & Transaction Notes**

- Performs data modification in its observed body segment. Do not assume automatic rollback or commit; verify transaction ownership.
- **Operational caution:** Test with non-production data and approved transaction controls. Never execute examples against live financial records without authorization.

**Source Evidence:** Specification line 304; body declaration approximately line 3129.

[↑ Back to index](#navigation)

---

<a id="recalculate_int_payment_plan"></a>

### `recalculate_int_payment_plan` — PROCEDURE

**Purpose:** Recalculates the interest component of a loan's payment plan.

**Business Logic**

Recalculates the interest component of a loan's payment plan.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
The observed implementation modifies database records; this is **not** a read-only routine. Review transaction and rollback behavior before calling it.
Observed delegated calls include `GLBL_FAIZ.DAY_COUNT_BASIS_NEW`.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
procedure recalculate_int_payment_plan(p_doc_no               in varchar2,
p_acc_type             in varchar2,
p_main_amount          in number,
p_INT_RATIO            in number,
p_int_calc_type        in varchar2,
p_schedule_update_type in number);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_doc_no` | IN | `varchar2` | Loan document reference |
| `p_acc_type` | IN | `varchar2` | Loan account type or account-type group |
| `p_main_amount` | IN | `number` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_INT_RATIO` | IN | `number` | Interest rate input |
| `p_int_calc_type` | IN | `varchar2` | Interest day-count/calculation convention |
| `p_schedule_update_type` | IN | `number` | Context-specific parameter; confirm accepted values with the owning developer. |

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- Observed reads: `LOAN_PAYMENT_PLAN`.
- Observed writes: `LOAN_PAYMENT_PLAN`.

**Error Handling**

- Observed message or error code: `p_schedule_update_type should be 3 or 4!`

**Side Effects & Transaction Notes**

- Performs data modification in its observed body segment. Do not assume automatic rollback or commit; verify transaction ownership.

**Source Evidence:** Specification line 311; body declaration approximately line 3445.

[↑ Back to index](#navigation)

---

<a id="get_new_acc"></a>

### `get_new_acc` — FUNCTION

**Purpose:** Opens or resolves an account for a particular loan/account classification.

**Business Logic**

Opens or resolves an account for a particular loan/account classification.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
Observed delegated calls include `GNI_MESSAGE.GET_MESSAGE`, `GLBL_HESAP.YENI_M2_HESAPNO`.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

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
p_memorandum_id   in varchar2 default null,
p_loan_doc_no     in varchar2,
p_loan_acc_type   in varchar2,
p_tx_fid          in number) return number;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_branch_no` | IN | `number` | Branch identifier |
| `p_customer_no` | IN | `number` | Customer identifier |
| `p_balance_acc` | IN | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_detail_code` | IN | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_ccy_id` | IN | `number` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_main_acc` | IN | `number default null` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_cr_int_rate` | IN | `number default null` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_dr_int_rate` | IN | `number default null` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_com_int_rate` | IN | `number default null` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_product_code` | IN | `number default null` | Loan product code |
| `p_period_id` | IN | `number default null` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_acc_description` | IN | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_memorandum_id` | IN | `varchar2 default null` | Memorandum identifier |
| `p_loan_doc_no` | IN | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_loan_acc_type` | IN | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_tx_fid` | IN | `number` | Transaction identifier |

**Return Value:** `number`. Business interpretation: Opens or resolves an account for a particular loan/account classification.

**Related Database Objects**

- Observed reads: `CS_ACCOUNT`, `LOAN_ACC_TYPES_PR`.

**Error Handling**

- Observed message or error code: `Creation scope for acc type [`

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 320; body declaration approximately line 2520.

[↑ Back to index](#navigation)

---

<a id="do_plan_control"></a>

### `do_plan_control` — PROCEDURE

**Purpose:** Runs configured checks against a loan payment plan.

**Business Logic**

Runs configured checks against a loan payment plan.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
procedure do_plan_control(p_document_no in varchar2);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_document_no` | IN | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- No direct static SQL dependencies identified in the isolated routine segment; dependencies may occur through called packages or dynamic SQL.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment; delegated operations may still modify data.
- **Operational caution:** Test with non-production data and approved transaction controls. Never execute examples against live financial records without authorization.

**Source Evidence:** Specification line 337; body declaration approximately line 3506.

[↑ Back to index](#navigation)

---

<a id="do_loan_status_control"></a>

### `do_loan_status_control` — PROCEDURE

**Purpose:** Checks loan account state and validity for a specified account.

**Business Logic**

Checks loan account state and validity for a specified account.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
Observed delegated calls include `GNI_MESSAGE.GET_MESSAGE`.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
procedure do_loan_status_control(p_branch_no   in number,
p_customer_no in number,
p_loan_acc    in number);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_branch_no` | IN | `number` | Branch identifier |
| `p_customer_no` | IN | `number` | Customer identifier |
| `p_loan_acc` | IN | `number` | Context-specific parameter; confirm accepted values with the owning developer. |

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- Observed reads: `LOAN_PORTFOLIO_LITE`.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment; delegated operations may still modify data.
- **Operational caution:** Test with non-production data and approved transaction controls. Never execute examples against live financial records without authorization.

**Source Evidence:** Specification line 340; body declaration approximately line 3515.

[↑ Back to index](#navigation)

---

<a id="create_loan_history"></a>

### `create_loan_history` — PROCEDURE

**Purpose:** Records a loan operation and its accompanying information in loan history.

**Business Logic**

Records a loan operation and its accompanying information in loan history.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
The observed implementation modifies database records; this is **not** a read-only routine. Review transaction and rollback behavior before calling it.
Observed delegated calls include `TRN_BROKER.REGISTER_EOD`, `RUHA3H.CLOB_OUT`, `LOAN_API.GET_GL_ACC_ACTIVE_PASSIVE`, `LOAN_API.LOAN_INT_DIFF_OPERATION`.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
procedure create_loan_history(p_oper_type VARCHAR2 default null,
p_doc_no    VARCHAR2 default null,
p_trn_date  DATE default glbl.getsysdate,
p_tx_fid    NUMBER,
p_trn_type  varchar2,
p_add_info  add_info_tab default null);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_oper_type` | IN | `VARCHAR2 default null` | Operation code used for routing or validation |
| `p_doc_no` | IN | `VARCHAR2 default null` | Loan document reference |
| `p_trn_date` | IN | `DATE default glbl.getsysdate` | Transaction date |
| `p_tx_fid` | IN | `NUMBER` | Transaction identifier |
| `p_trn_type` | IN | `varchar2` | Transaction action/type |
| `p_add_info` | IN | `add_info_tab default null` | Context-specific parameter; confirm accepted values with the owning developer. |

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- Observed reads: `GLBL_TRANSACTION`, `GL_JOURNAL_LINES`, `LOAN_ACCOUNTS_VS_OPERATION_HISTORY_FOR_CTRL_V`, `LOAN_LINES_FOR_CTRL_V`, `LOAN_OPERATION_DESC`, `LOAN_OPERATION_HISTORY`, `LOAN_OPERATION_HISTORY_FOR_CTRL_V`.
- Observed writes: `ACTIONS.`, `LOAN_OPERATION_HISTORY`.

**Error Handling**

- Observed message or error code: `p_app_oper_code not found in loan_operation_desc table!`
- Observed message or error code: `error encountered in search of oper_type`
- Observed message or error code: `Transaction with tx_fid: `

**Side Effects & Transaction Notes**

- Performs data modification in its observed body segment. Do not assume automatic rollback or commit; verify transaction ownership.

**Source Evidence:** Specification line 343; body declaration approximately line 3587.

[↑ Back to index](#navigation)

---

<a id="do_loan_collateral_out"></a>

### `do_loan_collateral_out` — PROCEDURE

**Purpose:** Processes release of collateral in a loan context.

**Business Logic**

Processes release of collateral in a loan context.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
The observed implementation modifies database records; this is **not** a read-only routine. Review transaction and rollback behavior before calling it.
Observed delegated calls include `GLBL_EOD.GETCALLERID`, `TRN_BROKER.REGISTER_EOD`, `TRN_BROKER.SETTXDETAILS`, `GLBL_CCY.TO_CCY_MB`, `GLBL_CCY.GET_CUR_RATE`, `PA_API#.CREATE_J_WSQL`, `MM_ACCOUNTING#.POST_JOURNAL`, `TRN_BROKER.SETTXSTATE`.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
procedure do_loan_collateral_out(p_doc_no in varchar2);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_doc_no` | IN | `varchar2` | Loan document reference |

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- Observed reads: `CS_ACCOUNT`, `KRD_SCOR_AUTO_C`, `KRD_SCOR_EMANET_C`, `KRD_SCOR_ESYA_C`, `KRD_SCOR_QARANT_C`, `KRD_SCOR_REAL_ESTATE_C`, `KRD_SCOR_SEHMLER_C`, `KRD_SCOR_TEMINAT_ALAKA_C`, `KRD_SCOR_ZAMIN_C`, `KRD_SKOR_GIROV_OTHER_C`, `KRD_TEMINAT_TIP_PR`.
- Observed writes: `KRD_SCOR_TEMINAT_ALAKA_C`.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- Performs data modification in its observed body segment. Do not assume automatic rollback or commit; verify transaction ownership.
- **Operational caution:** Test with non-production data and approved transaction controls. Never execute examples against live financial records without authorization.

**Source Evidence:** Specification line 352; body declaration approximately line 3942.

[↑ Back to index](#navigation)

---

<a id="get_acc_type_by_status"></a>

### `get_acc_type_by_status` — FUNCTION

**Purpose:** Maps an account type when transitioning between loan statuses.

**Business Logic**

Maps an account type when transitioning between loan statuses.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.

**Business Rules / Preconditions**

- **Verify:** Accepted codes, required upstream states, and boundary conditions are not fully specified in the package specification.

**Public Signature**

```sql
function get_acc_type_by_status(p_acc_type         varchar2,
p_to_loan_status   varchar2,
p_from_loan_status varchar2 default 'NORM')
return varchar2;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_acc_type` | IN | `varchar2` | Loan account type or account-type group |
| `p_to_loan_status` | IN | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_from_loan_status` | IN | `varchar2 default 'NORM'` | Context-specific parameter; confirm accepted values with the owning developer. |

**Return Value:** `varchar2`. Business interpretation: Maps an account type when transitioning between loan statuses.

**Related Database Objects**

- Observed reads: `LOAN`, `LOAN_ACC_TYPE_MAPPING`.

**Error Handling**

- Observed message or error code: `Can not find acc type [`
- Observed message or error code: `Something went wrong in [loan_acc_type_mapping], Acc Type [`

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 353; body declaration approximately line 4211.

[↑ Back to index](#navigation)

---

<a id="generate_allocated_payment_list"></a>

### `generate_allocated_payment_list` — PROCEDURE

**Purpose:** Allocates an incoming payment across loan account categories based on applicable rules.

**Business Logic**

Allocates an incoming payment across loan account categories based on applicable rules.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
Observed delegated calls include `LOAN_API.G_LOAN_ACCOUNTS_TAB`, `P.ACC_TYPE`, `O.PARAM_ID`, `O.TYPE_ID`, `LOAN_API.G_LOAN_ACCOUNTS_REC_TYPE`, `LOAN_API.GET_PLAN_PAYMENT_AMOUNT`.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
procedure generate_allocated_payment_list(p_doc_no                in varchar2,
p_oper_type             in varchar2,
p_pym_amount            in number,
p_has_schedule_upd_type out varchar2,
p_payment_list          out loan_api.g_loan_accounts_tab);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_doc_no` | IN | `varchar2` | Loan document reference |
| `p_oper_type` | IN | `varchar2` | Operation code used for routing or validation |
| `p_pym_amount` | IN | `number` | Payment amount to allocate |
| `p_has_schedule_upd_type` | OUT | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_payment_list` | OUT | `loan_api.g_loan_accounts_tab` | Collection containing allocated payment records |

**Outputs:** `p_has_schedule_upd_type`, `p_payment_list`

**Related Database Objects**

- Observed reads: `CS_ACCOUNT`, `IN_LIST`.

**Error Handling**

- Observed message or error code: `acc_type[`
- Observed message or error code: `Payment branch or customer or account is null Pymt_branch_no: `
- Observed message or error code: `Payment amount cant be more than balance amount! 
                            Please check amount of acc_type: `

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment; delegated operations may still modify data.
- **Operational caution:** Test with non-production data and approved transaction controls. Never execute examples against live financial records without authorization.

**Source Evidence:** Specification line 358; body declaration approximately line 4239.

[↑ Back to index](#navigation)

---

<a id="add_payment_details"></a>

### `add_payment_details` — PROCEDURE

**Purpose:** Enriches or adjusts allocation details for loan payment processing.

**Business Logic**

Enriches or adjusts allocation details for loan payment processing.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
Observed delegated calls include `LOAN_API.G_LOAN_ACCOUNTS_TAB`, `LOAN_API.GET_PLAN_PAYMENT_AMOUNT`.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
procedure add_payment_details(p_doc_no                in varchar2,
p_has_schedule_upd_type out varchar2,
p_payment_list          in out loan_api.g_loan_accounts_tab);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_doc_no` | IN | `varchar2` | Loan document reference |
| `p_has_schedule_upd_type` | OUT | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_payment_list` | IN OUT | `loan_api.g_loan_accounts_tab` | Collection containing allocated payment records |

**Outputs:** `p_has_schedule_upd_type`, `p_payment_list`

**Related Database Objects**

- Observed reads: `CS_ACCOUNT`.

**Error Handling**

- Observed message or error code: `Acc_type: `
- Observed message or error code: `Payment branch or customer or account is null Pymt_branch_no: `

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment; delegated operations may still modify data.

**Source Evidence:** Specification line 364; body declaration approximately line 4389.

[↑ Back to index](#navigation)

---

<a id="do_delete_operation"></a>

### `do_delete_operation` — PROCEDURE

**Purpose:** Reverses or removes a loan operation identified by its transaction ID.

**Business Logic**

Reverses or removes a loan operation identified by its transaction ID.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
The observed implementation modifies database records; this is **not** a read-only routine. Review transaction and rollback behavior before calling it.
Observed delegated calls include `LOAN_TRANCHE_API.DO_DELETE_OPERATION`, `LOAN_API.REVERSE_UPDATE`, `MM_ACCOUNTING#.FIS_SIL`, `KRD_EOD.TERS_FIS_KES`, `LOAN_API.CREATE_LOAN_HISTORY`.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
procedure do_delete_operation(p_tx_fid number);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_tx_fid` | IN | `number` | Transaction identifier |

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- Observed reads: `GL_JOURNAL_LINES`, `LOAN_OPERATION_HISTORY`.
- Observed writes: `GLBL_TRANSACTION`.

**Error Handling**

- Observed message or error code: `Can not get additional info in [loan_operation_history] with tx fid [`
- Observed message or error code: `Not declared delete operation [`

**Side Effects & Transaction Notes**

- Performs data modification in its observed body segment. Do not assume automatic rollback or commit; verify transaction ownership.
- **Operational caution:** Test with non-production data and approved transaction controls. Never execute examples against live financial records without authorization.

**Source Evidence:** Specification line 368; body declaration approximately line 4483.

[↑ Back to index](#navigation)

---

<a id="do_auto_payment"></a>

### `do_Auto_Payment` — PROCEDURE

**Purpose:** Processes automatic loan payments in EOD/SOD batch context.

**Business Logic**

Processes automatic loan payments in EOD/SOD batch context.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
Observed delegated calls include `LOAN_API.G_LOAN_ACCOUNTS_TAB`, `GNI_UTILITY.DELETE_BATCH_ERROR`, `LOAN_API.GET_OVD_DATE`, `LOAN_API.GET_LOAN_AMOUNT`, `GLBL_BAKIYE.REAL_BALANCE`, `GLBL_CCY.GET_CUR_RATE`, `LOAN_TRANCHE_API.DO_TRANCHE_OPERATION`, `LOAN_API.GENERATE_ALLOCATED_PAYMENT_LIST`; additional calls omitted.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
Procedure do_Auto_Payment(p_min_id     number default null,
p_max_id     number default null,
p_doc_no     in varchar2 default null,
p_eod_sod    in varchar2 default 'E',
p_test_param in number default null);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_min_id` | IN | `number default null` | Lower bound of batch selection |
| `p_max_id` | IN | `number default null` | Upper bound of batch selection |
| `p_doc_no` | IN | `varchar2 default null` | Loan document reference |
| `p_eod_sod` | IN | `varchar2 default 'E'` | End-of-day (`E`) or start-of-day (`S`) indicator (where supported) |
| `p_test_param` | IN | `number default null` | Context-specific parameter; confirm accepted values with the owning developer. |

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- Observed reads: `EOD_PROGRAMS_EXCEPTION`, `IN_LIST`, `KRD_TEKLIF_DETAY`, `LOAN_PAYMENT_PLAN`.

**Error Handling**

- Observed message or error code: `Auto payment type should be 1-Plan payment or 2-Off plan payment!`

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment; delegated operations may still modify data.
- **Operational caution:** Test with non-production data and approved transaction controls. Never execute examples against live financial records without authorization.

**Source Evidence:** Specification line 370; body declaration approximately line 4540.

[↑ Back to index](#navigation)

---

<a id="do_int_calculation"></a>

### `do_int_calculation` — PROCEDURE

**Purpose:** Calculates loan interest in a batch or selected-loan EOD/SOD context.

**Business Logic**

Calculates loan interest in a batch or selected-loan EOD/SOD context.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
Observed delegated calls include `GLBL_TARIH.SONRAKI_ISGUNU`, `LOAN_API.G_DATE_TAB_TYPE`, `LOAN_API.GET_GL_VALUE`, `GLBL_TARIH.ONCEKI_ISGUNU`, `LOAN_API.G_ENTRIES_LIST_TAB`, `LOAN_API.GET_TRN_CALLER_ID`, `O.SENED_NO`, `PR.URUN_KOD`; additional calls omitted.

**Business Rules / Preconditions**

- `p_min_id` and `p_max_id` limit batch scope; `p_doc_no` can select a loan.
- `p_eod_sod` identifies the requested processing phase.

**Public Signature**

```sql
procedure do_int_calculation(p_min_id  number default 0,
p_max_id  number default 999999999,
p_doc_no  in varchar2 default null,
p_eod_sod in varchar2 default 'E',
p_date    in date default glbl.getsysdate);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_min_id` | IN | `number default 0` | Lower bound of batch selection |
| `p_max_id` | IN | `number default 999999999` | Upper bound of batch selection |
| `p_doc_no` | IN | `varchar2 default null` | Loan document reference |
| `p_eod_sod` | IN | `varchar2 default 'E'` | End-of-day (`E`) or start-of-day (`S`) indicator (where supported) |
| `p_date` | IN | `date default glbl.getsysdate` | Relevant calculation or operation date |

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- Observed reads: `CS_ACCOUNT`, `EOD_PROGRAMS_EXCEPTION`, `KRD_TEKLIF_DETAY`, `LOAN_FLOW_RATIO_INFO`, `LOAN_INT_CALC_STOP_FOR_GRACE`, `LOAN_PAYMENT_PLAN`, `LOAN_STOP_RATIO_INFO`.

**Error Handling**

- Observed message or error code: `is_int_calc or is_pen_calc columns in krd_teklif_detay table is null! Please check...`
- Observed message or error code: `Product code not found in pkrd_turkod_pr table, 
                   pls check 22401 app for this loan product!`
- Observed message or error code: `Not working day may be 1 or 2, please check 22401 app, 
                                       for product code:`

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment; delegated operations may still modify data.
- **Operational caution:** Test with non-production data and approved transaction controls. Never execute examples against live financial records without authorization.

**Source Evidence:** Specification line 382; body declaration approximately line 5136.

[↑ Back to index](#navigation)

---

<a id="do_int_calculation_ex"></a>

### `do_int_calculation_ex` — PROCEDURE

**Purpose:** Calculates loan interest using the alternative calculation implementation.

**Business Logic**

Calculates loan interest using the alternative calculation implementation.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
The observed implementation modifies database records; this is **not** a read-only routine. Review transaction and rollback behavior before calling it.
Observed delegated calls include `GLBL_TARIH.SONRAKI_ISGUNU`, `LOAN_API.G_DATE_TAB_TYPE`, `LOAN_API.GET_GL_VALUE`, `LOAN_API.G_ENTRIES_LIST_TAB`, `LOAN_API.GET_TRN_CALLER_ID`, `LOAN_API.GET_INTEREST_CALC_DATES_EX`, `V.DOC_NO`, `O.SENED_NO`; additional calls omitted.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
procedure do_int_calculation_ex(p_min_id  number default 0,
p_max_id  number default 999999999,
p_doc_no  in varchar2 default null,
p_eod_sod in varchar2 default 'E',
p_date    in date default glbl.getsysdate);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_min_id` | IN | `number default 0` | Lower bound of batch selection |
| `p_max_id` | IN | `number default 999999999` | Upper bound of batch selection |
| `p_doc_no` | IN | `varchar2 default null` | Loan document reference |
| `p_eod_sod` | IN | `varchar2 default 'E'` | End-of-day (`E`) or start-of-day (`S`) indicator (where supported) |
| `p_date` | IN | `date default glbl.getsysdate` | Relevant calculation or operation date |

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- Observed reads: `CS_ACCOUNT`, `KRD_TEKLIF_DETAY`, `LOAN_ACC_TYPES_PR`, `LOAN_FLOW_RATIO_INFO`, `LOAN_PAYMENT_DATES_LIST`, `LOAN_PAYMENT_PLAN`, `LOAN_STOP_RATIO_INFO`.
- Observed writes: `LOAN_PAYMENT_DATES_LIST`.

**Error Handling**

- Observed message or error code: `is_int_calc or is_pen_calc columns in krd_teklif_detay table is null! Please check...`
- Observed message or error code: `Product code not found in pkrd_turkod_pr table, 
                   pls check 22401 app for this loan product!`
- Observed message or error code: `Not working day may be 1 or 2, please check 22401 app, 
                                       for product code:`

**Side Effects & Transaction Notes**

- Performs data modification in its observed body segment. Do not assume automatic rollback or commit; verify transaction ownership.
- **Operational caution:** Test with non-production data and approved transaction controls. Never execute examples against live financial records without authorization.

**Source Evidence:** Specification line 396; body declaration approximately line 5768.

[↑ Back to index](#navigation)

---

<a id="do_overdue_transit_operation"></a>

### `do_overdue_transit_operation` — PROCEDURE

**Purpose:** Processes overdue account transitions for eligible loans.

**Business Logic**

Processes overdue account transitions for eligible loans.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
The observed implementation modifies database records; this is **not** a read-only routine. Review transaction and rollback behavior before calling it.
Observed delegated calls include `LOAN_API.G_LOAN_ACCOUNTS_TAB`, `LOAN_API.G_ENTRIES_LIST_TAB`, `PP.URUN_KOD`, `LOAN_API.CREATE_ACCOUNT`, `LOAN_API.GET_ACC_TYPE_BY_STATUS`, `CL.LOAN_DOC_NO`, `CL.ACC_TYPE`, `CR.LOAN_DOC_NO`; additional calls omitted.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
Procedure do_overdue_transit_operation(p_min_id number default null,
p_max_id number default null,
p_doc_no in varchar2 default null,
p_date   in date default glbl.getsysdate);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_min_id` | IN | `number default null` | Lower bound of batch selection |
| `p_max_id` | IN | `number default null` | Upper bound of batch selection |
| `p_doc_no` | IN | `varchar2 default null` | Loan document reference |
| `p_date` | IN | `date default glbl.getsysdate` | Relevant calculation or operation date |

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- Observed reads: `CS_ACCOUNT`, `LOAN_OVERDUE_MAPPING`, `LOAN_OVERDUE_TRANSIT_QUEUE`, `LOAN_PAYMENT_PLAN`.
- Observed writes: `KRD_TEKLIF_DETAY`, `LOAN_OVERDUE_TRANSIT_QUEUE`, `LOAN_PAYMENT_PLAN`.

**Error Handling**

- Observed message or error code: `Loan product code not found in pkrd_turkod_pr table!`
- Observed message or error code: `Error encountered in overdue-transit operation for loan, doc_no: `

**Side Effects & Transaction Notes**

- Performs data modification in its observed body segment. Do not assume automatic rollback or commit; verify transaction ownership.
- **Operational caution:** Test with non-production data and approved transaction controls. Never execute examples against live financial records without authorization.

**Source Evidence:** Specification line 402; body declaration approximately line 4832.

[↑ Back to index](#navigation)

---

<a id="do_commission_recognition"></a>

### `do_commission_recognition` — PROCEDURE

**Purpose:** Recognizes loan-related commissions as of the supplied accounting date.

**Business Logic**

Recognizes loan-related commissions as of the supplied accounting date.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
The observed implementation modifies database records; this is **not** a read-only routine. Review transaction and rollback behavior before calling it.
Observed delegated calls include `GLBL_EOD.GETCALLERID`, `GLBL_TARIH.AYSONU`, `KRD_EOD.GET_GL_URUN_HESAP`, `KRD_EOD.M_FIS_KES`, `LOAN_API.DO_COM_SCHEDULE_ALLIGNMENT`.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
Procedure do_commission_recognition(Pdate In Date Default Glbl.Getsysdate);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `Pdate` | IN | `Date Default Glbl.Getsysdate` | Context-specific parameter; confirm accepted values with the owning developer. |

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- Observed reads: `KRD_KOM_EOD`, `KRD_KOM_PLAN_DETAY`, `KRD_TESIS`.
- Observed writes: `HISSESI`, `KRD_KOM_EOD`, `KRD_TESIS`.

**Error Handling**

- Observed message or error code: `This Program can run only last day of month!`

**Side Effects & Transaction Notes**

- Performs data modification in its observed body segment. Do not assume automatic rollback or commit; verify transaction ownership.
- **Operational caution:** Test with non-production data and approved transaction controls. Never execute examples against live financial records without authorization.

**Source Evidence:** Specification line 416; body declaration approximately line 6338.

[↑ Back to index](#navigation)

---

<a id="do_guarantee_out"></a>

### `do_guarantee_out` — PROCEDURE

**Purpose:** Processes guarantee-related release or settlement for selected account identifiers.

**Business Logic**

Processes guarantee-related release or settlement for selected account identifiers.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
Observed delegated calls include `GLBL_BAKIYE.REAL_BALANCE`, `APEX_KRD2220_0_API_P.INS_KRD2220_0`, `TRN_BROKER.STARTTX`, `KRD2220_0_API.JUSTDOIT`.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
Procedure do_guarantee_out(p_branch_id   In Number Default Null,
p_customer_no In Number Default Null,
p_loan_acc    In Number Default Null);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_branch_id` | IN | `Number Default Null` | Branch identifier |
| `p_customer_no` | IN | `Number Default Null` | Customer identifier |
| `p_loan_acc` | IN | `Number Default Null` | Context-specific parameter; confirm accepted values with the owning developer. |

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- Observed reads: `KRD_TESIS`.

**Error Handling**

- Observed message or error code: `Loan acc: `

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment; delegated operations may still modify data.
- **Operational caution:** Test with non-production data and approved transaction controls. Never execute examples against live financial records without authorization.

**Source Evidence:** Specification line 418; body declaration approximately line 6236.

[↑ Back to index](#navigation)

---

<a id="do_loan_close_with_collateral_out"></a>

### `do_Loan_Close_With_Collateral_Out` — PROCEDURE

**Purpose:** Closes a loan and coordinates collateral release.

**Business Logic**

Closes a loan and coordinates collateral release.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
The observed implementation modifies database records; this is **not** a read-only routine. Review transaction and rollback behavior before calling it.
Observed delegated calls include `GLBL_EOD.GETCALLERID`, `GLBL_HESAP.GET_ACCOUNT_PR`, `LOAN_API.G_ENTRIES_LIST_TAB`, `LOAN_API.DO_JOURNAL_ENTRY`, `LOAN_API.CREATE_LOAN_HISTORY`, `LOAN_API.CHANGE_ACCOUNT_STATUS`, `TRN_BROKER.REGISTER_EOD`, `TRN_BROKER.SETTXSTATE`.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
procedure do_Loan_Close_With_Collateral_Out(p_doc_no in varchar2);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_doc_no` | IN | `varchar2` | Loan document reference |

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- Observed reads: `LOAN_EOD_AUTO_CLOSE`, `LOAN_PORTFOLIO_LITE`, `LOAN_TRANCHE_LIMIT_CHANGES_HISTORY`.
- Observed writes: `KRD_TEKLIF_DETAY`, `LOAN_EOD_AUTO_CLOSE`.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- Performs data modification in its observed body segment. Do not assume automatic rollback or commit; verify transaction ownership.
- **Operational caution:** Test with non-production data and approved transaction controls. Never execute examples against live financial records without authorization.

**Source Evidence:** Specification line 422; body declaration approximately line 6594.

[↑ Back to index](#navigation)

---

<a id="do_non_cash_loan_close"></a>

### `do_non_cash_loan_close` — PROCEDURE

**Purpose:** Closes a non-cash loan in the supplied loan/date context.

**Business Logic**

Closes a non-cash loan in the supplied loan/date context.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
Observed delegated calls include `GLBL_BAKIYE.REAL_BALANCE`, `APEX_KRD2220_0_API_P.INS_KRD2220_0`, `TRN_BROKER.STARTTX`, `KRD2220_0_API.JUSTDOIT`.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
Procedure do_non_cash_loan_close(p_doc_no in varchar2,
p_Date   In Date Default Glbl.Getsysdate);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_doc_no` | IN | `varchar2` | Loan document reference |
| `p_Date` | IN | `Date Default Glbl.Getsysdate` | Relevant calculation or operation date |

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- Observed reads: `KRD_TESIS`.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment; delegated operations may still modify data.
- **Operational caution:** Test with non-production data and approved transaction controls. Never execute examples against live financial records without authorization.

**Source Evidence:** Specification line 424; body declaration approximately line 6756.

[↑ Back to index](#navigation)

---

<a id="do_journal_control"></a>

### `do_journal_control` — PROCEDURE

**Purpose:** Runs journal controls for the specified branch, customer and subaccount.

**Business Logic**

Runs journal controls for the specified branch, customer and subaccount.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
procedure do_journal_control(p_branch_id   IN Number,
p_customer_no IN Number,
p_account_sub IN Number);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_branch_id` | IN | `Number` | Branch identifier |
| `p_customer_no` | IN | `Number` | Customer identifier |
| `p_account_sub` | IN | `Number` | Context-specific parameter; confirm accepted values with the owning developer. |

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- Observed reads: `CS_ACCOUNT`.

**Error Handling**

- Observed message or error code: `???????? ?? ????. ?????? ????? ???? ?????? ?? ?????????? ?????? !!!`

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment; delegated operations may still modify data.
- **Operational caution:** Test with non-production data and approved transaction controls. Never execute examples against live financial records without authorization.

**Source Evidence:** Specification line 428; body declaration approximately line 6861.

[↑ Back to index](#navigation)

---

<a id="do_schedule_allignment"></a>

### `do_schedule_allignment` — PROCEDURE

**Purpose:** Aligns a payment schedule after a payment amount is applied.

**Business Logic**

Aligns a payment schedule after a payment amount is applied.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
The observed implementation modifies database records; this is **not** a read-only routine. Review transaction and rollback behavior before calling it.
Observed delegated calls include `GLOG.ASSERT#`.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
Procedure do_schedule_allignment(p_doc_no         In Varchar2,
p_payment_amount In Number,
p_acc_type       In Varchar2);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_doc_no` | IN | `Varchar2` | Loan document reference |
| `p_payment_amount` | IN | `Number` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_acc_type` | IN | `Varchar2` | Loan account type or account-type group |

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- Observed reads: `KRD_TEKLIF_DETAY`, `LOAN_PAYMENT_PLAN`.
- Observed writes: `LOAN_PAYMENT_PLAN`, `UPDATE`.

**Error Handling**

- Observed message or error code: `at [do_schedule_allignment] parametr [p_payment_amount] less than [0]`

**Side Effects & Transaction Notes**

- Performs data modification in its observed body segment. Do not assume automatic rollback or commit; verify transaction ownership.
- **Operational caution:** Test with non-production data and approved transaction controls. Never execute examples against live financial records without authorization.

**Source Evidence:** Specification line 438; body declaration approximately line 7116.

[↑ Back to index](#navigation)

---

<a id="do_com_schedule_allignment"></a>

### `do_com_schedule_allignment` — PROCEDURE

**Purpose:** Aligns a commission payment schedule using option, amount and plan type.

**Business Logic**

Aligns a commission payment schedule using option, amount and plan type.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
The observed implementation modifies database records; this is **not** a read-only routine. Review transaction and rollback behavior before calling it.
Observed delegated calls include `GLOG.ASSERT#`.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
Procedure do_com_schedule_allignment(p_doc_no      In Varchar2,
p_option_code In Varchar2,
p_amount      In Number,
p_plan_type   In Varchar2,
p_mig_status  In Number Default 0);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_doc_no` | IN | `Varchar2` | Loan document reference |
| `p_option_code` | IN | `Varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_amount` | IN | `Number` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_plan_type` | IN | `Varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_mig_status` | IN | `Number Default 0` | Context-specific parameter; confirm accepted values with the owning developer. |

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- Observed reads: `KRD_KOM_PLAN_DETAY`, `KRD_TESIS`.
- Observed writes: `KRD_KOM_PLAN_DETAY`.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- Performs data modification in its observed body segment. Do not assume automatic rollback or commit; verify transaction ownership.
- **Operational caution:** Test with non-production data and approved transaction controls. Never execute examples against live financial records without authorization.

**Source Evidence:** Specification line 443; body declaration approximately line 7190.

[↑ Back to index](#navigation)

---

<a id="do_loan_delay_int_rate_upd"></a>

### `do_Loan_Delay_Int_Rate_Upd` — PROCEDURE

**Purpose:** Updates loan delayed-interest rate information.

**Business Logic**

Updates loan delayed-interest rate information.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
The observed implementation modifies database records; this is **not** a read-only routine. Review transaction and rollback behavior before calling it.
Observed delegated calls include `LOAN_API.GET_DELAY_INT_RATE`.

**Business Rules / Preconditions**

- **Verify:** Accepted codes, required upstream states, and boundary conditions are not fully specified in the package specification.

**Public Signature**

```sql
Procedure do_Loan_Delay_Int_Rate_Upd;
```

**Parameters**

No parameters.

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- Observed reads: `KRD_TESIS`.
- Observed writes: `CS_ACCOUNT`, `OLUNUR`.

**Error Handling**

- Observed message or error code: `Gecikme Faizi 0-dan ferqli oldugu halda son gecikme faizi 0-dir!`
- Observed message or error code: `Kreditde sehv: `

**Side Effects & Transaction Notes**

- Performs data modification in its observed body segment. Do not assume automatic rollback or commit; verify transaction ownership.
- **Operational caution:** Test with non-production data and approved transaction controls. Never execute examples against live financial records without authorization.

**Source Evidence:** Specification line 450; body declaration approximately line 7310.

[↑ Back to index](#navigation)

---

<a id="change_account_status"></a>

### `change_account_status` — PROCEDURE

**Purpose:** Changes the operational status of a loan's associated accounts.

**Business Logic**

Changes the operational status of a loan's associated accounts.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
Observed delegated calls include `GLBL_HESAP.HESAPNO_AC`, `GLBL_HESAP.HESAPNO_KAPA`.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
procedure change_account_status(p_doc_no in varchar2,
p_status in varchar2);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_doc_no` | IN | `varchar2` | Loan document reference |
| `p_status` | IN | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- Observed reads: `CS_ACCOUNT`, `KRD_TESIS`.

**Error Handling**

- Observed message or error code: `Loan with doc_no: `
- Observed message or error code: `Error encountered in search of loan: `
- Observed message or error code: `Only followings p_status are accepted O-open, C-close!`

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment; delegated operations may still modify data.
- **Operational caution:** Test with non-production data and approved transaction controls. Never execute examples against live financial records without authorization.

**Source Evidence:** Specification line 453; body declaration approximately line 7351.

[↑ Back to index](#navigation)

---

<a id="stop_eod_task"></a>

### `stop_eod_task` — PROCEDURE

**Purpose:** Stops the EOD loan-task processing context.

**Business Logic**

Stops the EOD loan-task processing context.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.

**Business Rules / Preconditions**

- **Verify:** Accepted codes, required upstream states, and boundary conditions are not fully specified in the package specification.

**Public Signature**

```sql
procedure stop_eod_task;
```

**Parameters**

No parameters.

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- Observed reads: `EOD_TRANSACTION_ACTIVE`.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment; delegated operations may still modify data.

**Source Evidence:** Specification line 455; body declaration approximately line 7389.

[↑ Back to index](#navigation)

---

<a id="stop_loan_task"></a>

### `stop_loan_task` — PROCEDURE

**Purpose:** Stops the loan task(s) filtered by task code and/or type.

**Business Logic**

Stops the loan task(s) filtered by task code and/or type.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
Observed delegated calls include `DBMS_PARALLEL_EXECUTE.STOP_TASK`.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
procedure stop_loan_task(p_task_code in varchar2 default null,
p_task_type in varchar2 default null);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_task_code` | IN | `varchar2 default null` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_task_type` | IN | `varchar2 default null` | Context-specific parameter; confirm accepted values with the owning developer. |

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- Observed reads: `LOAN_TASKS_LIST`, `V$SESSION`.

**Error Handling**

- Observed message or error code: `E-task for EOD program, S-task for SOD program, X-any other program!`

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment; delegated operations may still modify data.

**Source Evidence:** Specification line 457; body declaration approximately line 7405.

[↑ Back to index](#navigation)

---

<a id="run_loan_task"></a>

### `run_loan_task` — PROCEDURE

**Purpose:** Runs a configured loan task, including parallelized task execution where implemented.

**Business Logic**

Runs a configured loan task, including parallelized task execution where implemented.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
Observed delegated calls include `DBMS_PARALLEL_EXECUTE.TASK_STATUS`, `DBMS_PARALLEL_EXECUTE.DROP_TASK`, `DBMS_PARALLEL_EXECUTE.CREATE_TASK`, `DBMS_PARALLEL_EXECUTE.CREATE_CHUNKS_BY_NUMBER_COL`, `DBMS_PARALLEL_EXECUTE.CREATE_CHUNKS_BY_ROWID`, `DBMS_PARALLEL_EXECUTE.CREATE_CHUNKS_BY_SQL`, `DBMS_PARALLEL_EXECUTE.RUN_TASK`.

**Business Rules / Preconditions**

- Task code/type select the configured background loan task.
- Task parallelization and scheduler state must be verified against deployment settings.

**Public Signature**

```sql
procedure run_loan_task(p_task_code in varchar2, p_task_type in varchar2);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_task_code` | IN | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_task_type` | IN | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- Observed reads: `DBA_PARALLEL_EXECUTE_CHUNKS`, `LOAN_TASKS_LIST`.

**Error Handling**

- Observed message or error code: `E-task for EOD program, S-task for SOD program, X-any other program!`
- Observed message or error code: `Error encountered in search of status of the task: `
- Observed message or error code: `CHUNKS BY COLUMN MUST BE COLUMN, ROWID, SQL TYPES!`

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment; delegated operations may still modify data.
- **Operational caution:** Test with non-production data and approved transaction controls. Never execute examples against live financial records without authorization.

**Source Evidence:** Specification line 460; body declaration approximately line 7442.

[↑ Back to index](#navigation)

---

<a id="calculate_xirr"></a>

### `calculate_xirr` — FUNCTION

**Purpose:** Computes a loan's XIRR or related rate metric for a chosen calculation type.

**Business Logic**

Computes a loan's XIRR or related rate metric for a chosen calculation type.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
The observed implementation modifies database records; this is **not** a read-only routine. Review transaction and rollback behavior before calling it.
Observed delegated calls include `LOAN_API.GET_MIN_FLOW_RATIO`, `PLOG.FATAL`.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
function calculate_xirr(p_doc_no  varchar2,
p_type    varchar2,
p_calc_as varchar2 default 'XIRR') return number;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_doc_no` | IN | `varchar2` | Loan document reference |
| `p_type` | IN | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_calc_as` | IN | `varchar2 default 'XIRR'` | Context-specific parameter; confirm accepted values with the owning developer. |

**Return Value:** `number`. Business interpretation: Computes a loan's XIRR or related rate metric for a chosen calculation type.

**Related Database Objects**

- Observed reads: `APEX_KRD2201_1_COLL_V`, `APEX_KRD2201_4_COLL_V`, `KRD_TEKLIF_DETAY`, `LOAN_PAYMENT_PLAN`, `XIRR_SCHEDULE_TMP`.
- Observed writes: `XIRR_SCHEDULE_TMP`.

**Error Handling**

- Observed message or error code: `Deyer yoxdu`
- Observed message or error code: `Basqa problem`

**Side Effects & Transaction Notes**

- Performs data modification in its observed body segment. Do not assume automatic rollback or commit; verify transaction ownership.

**Source Evidence:** Specification line 467; body declaration approximately line 7783.

[↑ Back to index](#navigation)

---

<a id="get_min_flow_ratio"></a>

### `get_min_flow_ratio` — FUNCTION

**Purpose:** Retrieves the minimum loan cash-flow ratio over an optional date range.

**Business Logic**

Retrieves the minimum loan cash-flow ratio over an optional date range.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
function get_min_flow_ratio(
p_doc_no     varchar2,
p_type       varchar2,
p_begin_date date default null,
p_end_date   date default null
) return number;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_doc_no` | IN | `varchar2` | Loan document reference |
| `p_type` | IN | `varchar2` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_begin_date` | IN | `date default null` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_end_date` | IN | `date default null` | Context-specific parameter; confirm accepted values with the owning developer. |

**Return Value:** `number`. Business interpretation: Retrieves the minimum loan cash-flow ratio over an optional date range.

**Related Database Objects**

- Observed reads: `APEX_KRD2201_6_COLL_V`, `LOAN_FLOW_RATIO_INFO`.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 475; body declaration approximately line 8072.

[↑ Back to index](#navigation)

---

<a id="get_flow_ratio_info"></a>

### `get_flow_ratio_info` — FUNCTION

**Purpose:** Returns loan cash-flow ratio information at a date.

**Business Logic**

Returns loan cash-flow ratio information at a date.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.

**Business Rules / Preconditions**

- **Verify:** Accepted codes, required upstream states, and boundary conditions are not fully specified in the package specification.

**Public Signature**

```sql
FUNCTION get_flow_ratio_info(p_doc_no    VARCHAR2,
p_date      DATE DEFAULT glbl.getsysdate,
p_full_info varchar2 default 'N')
RETURN LOAN_FLOW_RATE_TAB;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_doc_no` | IN | `VARCHAR2` | Loan document reference |
| `p_date` | IN | `DATE DEFAULT glbl.getsysdate` | Relevant calculation or operation date |
| `p_full_info` | IN | `varchar2 default 'N'` | Context-specific parameter; confirm accepted values with the owning developer. |

**Return Value:** `LOAN_FLOW_RATE_TAB`. Business interpretation: Returns loan cash-flow ratio information at a date.

**Related Database Objects**

- Observed reads: `LOAN_FLOW_RATIO_INFO`.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 499; body declaration approximately line 8115.

[↑ Back to index](#navigation)

---

<a id="get_stop_ratio_info"></a>

### `get_stop_ratio_info` — FUNCTION

**Purpose:** Returns stopped or suspended loan-rate information at a date.

**Business Logic**

Returns stopped or suspended loan-rate information at a date.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.

**Business Rules / Preconditions**

- **Verify:** Accepted codes, required upstream states, and boundary conditions are not fully specified in the package specification.

**Public Signature**

```sql
FUNCTION get_stop_ratio_info(p_doc_no    VARCHAR2,
p_date      DATE DEFAULT glbl.getsysdate,
p_full_info varchar2 default 'N',
p_info_type varchar2 default 'INT')
RETURN LOAN_STOP_RATE_TAB;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_doc_no` | IN | `VARCHAR2` | Loan document reference |
| `p_date` | IN | `DATE DEFAULT glbl.getsysdate` | Relevant calculation or operation date |
| `p_full_info` | IN | `varchar2 default 'N'` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_info_type` | IN | `varchar2 default 'INT'` | Context-specific parameter; confirm accepted values with the owning developer. |

**Return Value:** `LOAN_STOP_RATE_TAB`. Business interpretation: Returns stopped or suspended loan-rate information at a date.

**Related Database Objects**

- Observed reads: `LOAN_STOP_RATIO_INFO`.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 504; body declaration approximately line 8151.

[↑ Back to index](#navigation)

---

<a id="get_incorrect_days"></a>

### `get_incorrect_days` — FUNCTION

**Purpose:** Produces a pipelined collection of days marked as incorrect for processing.

**Business Logic**

Produces a pipelined collection of days marked as incorrect for processing.

**Business Rules / Preconditions**

- **Verify:** Accepted codes, required upstream states, and boundary conditions are not fully specified in the package specification.

**Public Signature**

```sql
function get_incorrect_days(p_date date) return NUMBER_TT
pipelined;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_date` | IN | `date` | Relevant calculation or operation date |

**Return Value:** `NUMBER_TT`. Business interpretation: Produces a pipelined collection of days marked as incorrect for processing.

**Related Database Objects**

- No direct static SQL dependencies identified in the isolated routine segment; dependencies may occur through called packages or dynamic SQL.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 510; body declaration approximately line 8179.

[↑ Back to index](#navigation)

---

<a id="get_incorrect_days_count"></a>

### `get_incorrect_days_count` — FUNCTION

**Purpose:** Counts the dates marked as incorrect for processing.

**Business Logic**

Counts the dates marked as incorrect for processing.

**Business Rules / Preconditions**

- **Verify:** Accepted codes, required upstream states, and boundary conditions are not fully specified in the package specification.

**Public Signature**

```sql
function get_incorrect_days_count(p_date date) return number;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_date` | IN | `date` | Relevant calculation or operation date |

**Return Value:** `number`. Business interpretation: Counts the dates marked as incorrect for processing.

**Related Database Objects**

- No direct static SQL dependencies identified in the isolated routine segment; dependencies may occur through called packages or dynamic SQL.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 513; body declaration approximately line 8218.

[↑ Back to index](#navigation)

---

<a id="get_schedule_from_memo"></a>

### `get_schedule_from_memo` — FUNCTION

**Purpose:** Builds a payment schedule derived from memorandum information.

**Business Logic**

Builds a payment schedule derived from memorandum information.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
Observed delegated calls include `GLBL_FAIZ.DAY_COUNT_BASIS_NEW`.

**Business Rules / Preconditions**

- **Verify:** Accepted codes, required upstream states, and boundary conditions are not fully specified in the package specification.

**Public Signature**

```sql
function get_schedule_from_memo(p_memorandum_id varchar2,
p_int_ratio     number,
p_int_calc_type varchar2,
p_int_amount    number) return SCHEDULE_TT
pipelined;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_memorandum_id` | IN | `varchar2` | Memorandum identifier |
| `p_int_ratio` | IN | `number` | Interest rate input |
| `p_int_calc_type` | IN | `varchar2` | Interest day-count/calculation convention |
| `p_int_amount` | IN | `number` | Context-specific parameter; confirm accepted values with the owning developer. |

**Return Value:** `SCHEDULE_TT`. Business interpretation: Builds a payment schedule derived from memorandum information.

**Related Database Objects**

- Observed reads: `KRD_SCOR_ODEME_PLAN`.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 515; body declaration approximately line 8225.

[↑ Back to index](#navigation)

---

<a id="get_standart_schedule"></a>

### `get_standart_schedule` — FUNCTION

**Purpose:** Generates a standard schedule with grace periods and optional rate/stop-rate inputs.

**Business Logic**

Generates a standard schedule with grace periods and optional rate/stop-rate inputs.

**Business Rules / Preconditions**

- **Verify:** Accepted codes, required upstream states, and boundary conditions are not fully specified in the package specification.

**Public Signature**

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
p_loan_stop_rate_tab LOAN_STOP_RATE_TAB default null)
return SCHEDULE_TT
pipelined;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_begin_date` | IN | `date default glbl.getsysdate` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_main_pymt_date` | IN | `date` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_int_pymt_date` | IN | `date` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_pymt_day` | IN | `number default null` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_end_date` | IN | `date` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_offer_amount` | IN | `number` | Loan/offer principal amount |
| `p_ovd_main_amount` | IN | `number default 0` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_int_calc_type` | IN | `varchar2` | Interest day-count/calculation convention |
| `p_main_grace_period` | IN | `varchar2 default null` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_int_grace_period` | IN | `varchar2 default null` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_remain_int_amount` | IN | `number default 0` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_min_main_pay_amount` | IN | `number default null` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_calc_int_in_grace` | IN | `varchar2 default 'Y'` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_work_days` | IN | `varchar2 default 'Y'` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_loan_flow_rate_tab` | IN | `LOAN_FLOW_RATE_TAB default null` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_loan_stop_rate_tab` | IN | `LOAN_STOP_RATE_TAB default null` | Context-specific parameter; confirm accepted values with the owning developer. |

**Return Value:** `SCHEDULE_TT`. Business interpretation: Generates a standard schedule with grace periods and optional rate/stop-rate inputs.

**Related Database Objects**

- No direct static SQL dependencies identified in the isolated routine segment; dependencies may occur through called packages or dynamic SQL.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 521; body declaration approximately line 8324.

[↑ Back to index](#navigation)

---

<a id="get_annuity_schedule"></a>

### `get_annuity_schedule` — FUNCTION

**Purpose:** Generates an annuity schedule with configured limits, grace periods and rate changes.

**Business Logic**

Generates an annuity schedule with configured limits, grace periods and rate changes.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
Observed delegated calls include `GLBL_TARIH.SONRAKI_ISGUNU_FOR_LOAN`, `GLBL_FAIZ.DAY_COUNT_BASIS_NEW`, `LOAN_API.GET_PLAN_MONTH_COUNT`, `LOAN_API.ADD_MONTHS_FOR_LOAN`.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

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
p_loan_flow_rate_tab LOAN_FLOW_RATE_TAB default null,
p_loan_stop_rate_tab LOAN_STOP_RATE_TAB default null)
return SCHEDULE_TT
pipelined;
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_begin_date` | IN | `date` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_main_pymt_date` | IN | `date` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_int_pymt_date` | IN | `date` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_pymt_day` | IN | `number default null` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_end_date` | IN | `date` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_offer_amount` | IN | `number` | Loan/offer principal amount |
| `p_ovd_main_amount` | IN | `number default 0` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_int_calc_type` | IN | `varchar2` | Interest day-count/calculation convention |
| `p_main_grace_period` | IN | `varchar2 default null` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_int_grace_period` | IN | `varchar2 default null` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_annuity_amount` | IN | `number default null` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_max_annuity_amount` | IN | `number default null` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_remain_int_amount` | IN | `number default 0` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_work_days` | IN | `varchar2 default 'Y'` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_own_annuity` | IN | `varchar2 default 'N'` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_calc_int_in_grace` | IN | `varchar2 default 'Y'` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_is_mortgage` | IN | `varchar2 default 'N'` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_max_iteration` | IN | `number default null` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_loan_flow_rate_tab` | IN | `LOAN_FLOW_RATE_TAB default null` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_loan_stop_rate_tab` | IN | `LOAN_STOP_RATE_TAB default null` | Context-specific parameter; confirm accepted values with the owning developer. |

**Return Value:** `SCHEDULE_TT`. Business interpretation: Generates an annuity schedule with configured limits, grace periods and rate changes.

**Related Database Objects**

- Observed reads: `ALL_DATES`, `INTERVALS`, `SORTED_DATES`.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment. Called routines and dynamic SQL have not been proven side-effect-free.

**Source Evidence:** Specification line 542; body declaration approximately line 8697.

[↑ Back to index](#navigation)

---

<a id="get_created_schedule"></a>

### `get_created_schedule` — PROCEDURE

**Purpose:** Loads or retrieves a previously created schedule by identifier.

**Business Logic**

Loads or retrieves a previously created schedule by identifier.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
Procedure get_created_schedule(p_fid number);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_fid` | IN | `number` | Context-specific parameter; confirm accepted values with the owning developer. |

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- Observed reads: `CREATE_SCHEDULE_PARAMETRS`.

**Error Handling**

- Observed message or error code: `No record found for fid = `

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment; delegated operations may still modify data.

**Source Evidence:** Specification line 570; body declaration approximately line 9306.

[↑ Back to index](#navigation)

---

<a id="create_schedule"></a>

### `create_schedule` — PROCEDURE

**Purpose:** Creates a schedule based on schedule type, dates, amount, rates, and context.

**Business Logic**

Creates a schedule based on schedule type, dates, amount, rates, and context.

**Business Rules / Preconditions**

- **Verify:** Accepted codes, required upstream states, and boundary conditions are not fully specified in the package specification.

**Public Signature**

```sql
procedure create_schedule(p_schedule_no         number,
p_coll_name           varchar2 default null,
p_fk_id               number default null,
p_doc_no              varchar2 default 'XXX',
p_memorandum_id       varchar2 default null,
p_customer_no         number default null,
p_tx_fid              number default null,
p_begin_date          date default glbl.getsysdate,
p_main_pymt_date      date,
p_int_pymt_date       date,
p_pymt_day            number default null,
p_end_date            date,
p_offer_amount        number,
p_ovd_main_amount     number default 0,
p_int_ratio           number,
p_int_calc_type       varchar2,
p_annuity_amount      number default null,
p_max_annuity_amount  number default null,
p_min_main_pay_amount number default null,
p_remain_int_amount   number default 0,
p_main_grace_period   varchar2 default null,
p_int_grace_period    varchar2 default null,
p_main_pymt_period    number default 1,
p_int_pymt_period     number default 1,
p_product_code        number default null,
p_same_annuity        varchar2 default 'N',
p_calc_int_in_grace   varchar2 default 'Y',
p_return_type         varchar2 default 'NO_ZERO',
p_loan_flow_rate_tab  LOAN_FLOW_RATE_TAB default null,
p_loan_stop_rate_tab  LOAN_STOP_RATE_TAB default null);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_schedule_no` | IN | `number` | Schedule type/configuration number |
| `p_coll_name` | IN | `varchar2 default null` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_fk_id` | IN | `number default null` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_doc_no` | IN | `varchar2 default 'XXX'` | Loan document reference |
| `p_memorandum_id` | IN | `varchar2 default null` | Memorandum identifier |
| `p_customer_no` | IN | `number default null` | Customer identifier |
| `p_tx_fid` | IN | `number default null` | Transaction identifier |
| `p_begin_date` | IN | `date default glbl.getsysdate` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_main_pymt_date` | IN | `date` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_int_pymt_date` | IN | `date` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_pymt_day` | IN | `number default null` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_end_date` | IN | `date` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_offer_amount` | IN | `number` | Loan/offer principal amount |
| `p_ovd_main_amount` | IN | `number default 0` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_int_ratio` | IN | `number` | Interest rate input |
| `p_int_calc_type` | IN | `varchar2` | Interest day-count/calculation convention |
| `p_annuity_amount` | IN | `number default null` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_max_annuity_amount` | IN | `number default null` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_min_main_pay_amount` | IN | `number default null` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_remain_int_amount` | IN | `number default 0` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_main_grace_period` | IN | `varchar2 default null` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_int_grace_period` | IN | `varchar2 default null` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_main_pymt_period` | IN | `number default 1` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_int_pymt_period` | IN | `number default 1` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_product_code` | IN | `number default null` | Loan product code |
| `p_same_annuity` | IN | `varchar2 default 'N'` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_calc_int_in_grace` | IN | `varchar2 default 'Y'` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_return_type` | IN | `varchar2 default 'NO_ZERO'` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_loan_flow_rate_tab` | IN | `LOAN_FLOW_RATE_TAB default null` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_loan_stop_rate_tab` | IN | `LOAN_STOP_RATE_TAB default null` | Context-specific parameter; confirm accepted values with the owning developer. |

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- No direct static SQL dependencies identified in the isolated routine segment; dependencies may occur through called packages or dynamic SQL.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment; delegated operations may still modify data.
- **Operational caution:** Test with non-production data and approved transaction controls. Never execute examples against live financial records without authorization.

**Source Evidence:** Specification line 574; body declaration approximately line 9392.

[↑ Back to index](#navigation)

---

<a id="do_loan_control--overload-1"></a>

### `do_loan_control` — PROCEDURE (overload 1)

**Purpose:** Performs loan controls for a requested operation and date.

**Business Logic**

Performs loan controls for a requested operation and date.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
Observed delegated calls include `GNI_UTILITY.RUN_TASK`.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
procedure do_loan_control(p_oper_type varchar2 default null,
p_date      date default glbl.getsysdate);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_oper_type` | IN | `varchar2 default null` | Operation code used for routing or validation |
| `p_date` | IN | `date default glbl.getsysdate` | Relevant calculation or operation date |

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- Observed reads: `LOAN_EOD_CONTROL`.

**Error Handling**

- Observed message or error code: `Errors detected after operation [`

**Side Effects & Transaction Notes**

- No direct DML detected in the isolated implementation segment; delegated operations may still modify data.
- **Operational caution:** Test with non-production data and approved transaction controls. Never execute examples against live financial records without authorization.

**Source Evidence:** Specification line 604; body declaration approximately line 9907.

[↑ Back to index](#navigation)

---

<a id="do_loan_control--overload-2"></a>

### `do_loan_control` — PROCEDURE (overload 2)

**Purpose:** Performs loan controls over a constrained ROWID range for segmented processing.

**Business Logic**

Performs loan controls over a constrained ROWID range for segmented processing.
The observed implementation reads configuration, loan records, payment schedules, or related data as applicable to this operation. Refer to the database objects below for the directly observed tables.
The observed implementation modifies database records; this is **not** a read-only routine. Review transaction and rollback behavior before calling it.
Observed delegated calls include `LOAN_API.GET_PLAN_ERROR`.

**Business Rules / Preconditions**

- The implementation contains conditional processing and validation; confirm product-specific conditions and boundary cases with the owning developer.

**Public Signature**

```sql
procedure do_loan_control(p_oper_type varchar2 default null,
p_date      date default glbl.getsysdate,
p_min_rowid rowid,
p_max_rowid rowid);
```

**Parameters**

| Parameter | Direction | Type / default | Meaning |
|---|---|---|---|
| `p_oper_type` | IN | `varchar2 default null` | Operation code used for routing or validation |
| `p_date` | IN | `date default glbl.getsysdate` | Relevant calculation or operation date |
| `p_min_rowid` | IN | `rowid` | Context-specific parameter; confirm accepted values with the owning developer. |
| `p_max_rowid` | IN | `rowid` | Context-specific parameter; confirm accepted values with the owning developer. |

**Outputs:** No OUT parameters in the published signature.

**Related Database Objects**

- Observed reads: `KRD_TEKLIF_DETAY`, `LOAN_OPERATION_HISTORY`.
- Observed writes: `LOAN_EOD_CONTROL`.

**Error Handling**

- Refer to called packages, assertions and database constraints for errors. The exact contract is **not guaranteed** by the public signature alone.

**Side Effects & Transaction Notes**

- Performs data modification in its observed body segment. Do not assume automatic rollback or commit; verify transaction ownership.
- **Operational caution:** Test with non-production data and approved transaction controls. Never execute examples against live financial records without authorization.

**Source Evidence:** Specification line 607; body declaration approximately line 9929.

[↑ Back to index](#navigation)

---

