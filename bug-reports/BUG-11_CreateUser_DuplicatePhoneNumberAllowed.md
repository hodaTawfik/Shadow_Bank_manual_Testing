# Bug Report: System Allows Registration with Duplicate Phone Numbers

- **Bug ID:** BUG-11
- **Severity:** High
- **Priority:** High
- **Component:** Back-End (Database Unique Constraint)
- **Environment:** Web Application (ShadowBank Frontend - Local)
- **Feature:** Create User

---

### Summary
The system accepts duplicate phone numbers during user creation. Multiple user accounts can be registered using the exact same phone number without triggering a uniqueness validation check or error.

---

### Steps to Reproduce
1. Create a new user with a valid phone number (e.g., `+201234567890`).
2. Submit the form to successfully save User A.
3. Attempt to create User B using a different username and email, but inputting the **same phone number** (`+201234567890`).
4. Click **Create User**.

---

### Expected Result
The backend should validate phone number uniqueness and reject the request with an error message: *"Phone number is already registered"*.

---

### Actual Result
The system successfully creates User B with the duplicate phone number, saving duplicate entries in the database.

---

### Technical Impact
Breaks database integrity and affects account recovery or SMS notification features that rely on phone numbers as unique identifiers.
<img width="1053" height="312" alt="image" src="https://github.com/user-attachments/assets/3885be31-ed04-4ef4-b82c-cede4be611c4" />

