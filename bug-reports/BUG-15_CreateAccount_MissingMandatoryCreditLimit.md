# Bug Report: Credit Limit Field is Optional for Credit Account Types

- **Bug ID:** BUG-15
- **Severity:** High
- **Priority:** High
- **Component:** Business Logic / Validation
- **Environment:** Web Application (ShadowBank Frontend - Local)
- **Feature:** Create Account / Account Types

---

### Summary
When creating a `Credit` account type, the `Credit Limit` field is treated as optional. The system allows users to successfully create credit accounts without specifying a credit limit boundary.

---

### Steps to Reproduce
1. Navigate to the **Create Account** section.
2. Select **Credit** from the account type dropdown (Saving / Checking / Credit).
3. Leave the **Credit Limit** field completely empty.
4. Fill in other required fields and click **Create Account**.

---

### Expected Result
For financial compliance and security, selecting the **Credit** account type must enforce that the **Credit Limit** field is mandatory (*Required*), preventing submission if left blank.

---

### Actual Result
The system successfully creates a Credit account without requiring a Credit Limit value.

---

### Technical Impact
Violates core financial business logic, allowing credit accounts to exist infinitely without predefined spending limits.
<img width="1132" height="305" alt="image" src="https://github.com/user-attachments/assets/037a0a39-2051-488f-8cb8-718a3f24e0c1" />
