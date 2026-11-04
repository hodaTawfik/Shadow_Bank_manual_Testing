# Bug Report: Full Name Field Accepts Digits and Special Characters

- **Bug ID:** BUG-12
- **Severity:** Medium
- **Priority:** Medium
- **Component:** Front-End / Back-End (Input Validation)
- **Environment:** Web Application (ShadowBank Frontend - Local)
- **Feature:** Create User

---

### Summary
The Full Name input field lacks regex validation, allowing numbers, mathematical operators, and special symbols (e.g., `John123 @#$%`) to be submitted and saved as valid names.

---

### Steps to Reproduce
1. Navigate to the **Create User** section.
2. In the **Full Name** field, enter invalid string characters such as `Test User 123 !@#$`.
3. Complete remaining mandatory fields with valid data and click **Create User**.

---

### Expected Result
The form should validate that the Full Name field contains alphabetic characters and spaces only, triggering a validation error for invalid characters.

---

### Actual Result
The form accepts digits and special symbols without any error, persisting the invalid string to the user record.

---

### Technical Impact
Leads to corrupted user data storage and potential HTML/XSS injection risk if raw names are rendered unescaped on administrative UI pages.
<img width="1157" height="342" alt="image" src="https://github.com/user-attachments/assets/a8d384e6-d062-4b7c-9531-a67b9645f54d" />
