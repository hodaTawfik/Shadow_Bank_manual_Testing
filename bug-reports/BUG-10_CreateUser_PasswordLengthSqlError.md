# Bug Report: Raw SQL Exception on Password Field Overflow during User Creation

- **Bug ID:** BUG-10
- **Severity:** High / Critical (Security Information Disclosure)
- **Priority:** High
- **Component:** Front-End & Back-End (Validation & Error Handling)
- **Environment:** Web Application (ShadowBank Frontend - Local)
- **Feature:** Create User

---

### Summary
The Password field in the Create User form lacks client-side character length restrictions (`maxlength`). Inputting 500+ characters causes the backend to throw an unhandled HTTP 500 Internal Server Error, exposing raw database exception details: `Value too long for column "PASSWORD CHARACTER VARYING(255)"`.

---

### Steps to Reproduce
1. Navigate to the **Create User** section.
2. Fill in valid details for Username, Email, and Phone.
3. Paste a 500+ character string into the **Password** field.
4. Click **Create User**.

---

### Expected Result
1. **Front-End:** The field should enforce a maximum character limit (e.g., max 64 or 128 characters).
2. **Back-End:** The API should sanitize input and respond gracefully with a 400 Bad Request error message without leaking SQL column constraints.

---

### Actual Result
The system attempts to insert the long payload into the database, throwing a raw 500 SQL error containing schema details: `Value too long for column "PASSWORD CHARACTER VARYING(255)"`.

---

### Technical Impact
Exposes internal database column constraints (`PASSWORD CHARACTER VARYING(255)`) to the client-side, posing an Information Disclosure vulnerability (CWE-209).
<img width="1117" height="557" alt="image" src="https://github.com/user-attachments/assets/cbbdfacb-6ff0-4f01-9d23-473d0a803ee8" />
