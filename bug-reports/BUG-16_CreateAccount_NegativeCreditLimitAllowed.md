# Bug Report: Credit Limit Field Accepts Negative Numeric Values

- **Bug ID:** BUG-16
- **Severity:** Medium
- **Priority:** Medium
- **Component:** Front-End & Back-End (Input Validation)
- **Environment:** Web Application (ShadowBank Frontend - Local)
- **Feature:** Create Account

---

### Summary
The `Credit Limit` input field lacks range validation, allowing users to input and submit negative values (e.g., `-5000`) for account limits.

---

### Steps to Reproduce
1. Navigate to the **Create Account** section.
2. Enter a negative numerical value (e.g., `-1000`) into the **Credit Limit** field.
3. Fill in other valid parameters and submit the form.

---

### Expected Result
The system should enforce validation rules restricting credit limits to positive numerical values greater than zero (`> 0`), displaying an appropriate validation error message.

---

### Actual Result
The application accepts negative numbers without restriction and persists them as the account's credit limit.

---

### Technical Impact
Permits illogical financial states and potential calculation errors in transaction authorizations.
<img width="1081" height="283" alt="image" src="https://github.com/user-attachments/assets/bc3f7dcc-0deb-486f-97a3-095914aa7b16" />

