
# Bug Report: Missing Input Length Limit on Username and Password Fields

- **Bug ID:** BUG-04
- **Severity:** Medium
- **Priority:** Medium
- **Environment:** Web Application (ShadowBank Frontend - Local)
- **Feature:** User Authentication / Login

---

### Summary
The Username and Password fields do not enforce maximum length restrictions, accepting strings up to 5,000+ characters. This lack of client/backend sanitization exposes the system to potential UI responsiveness issues and buffer overflow/DoS vulnerabilities.

---

### Steps to Reproduce
1. Navigate to the Login page.
2. Paste a string of 1,000+ characters into the **Username** field.
3. Paste a string of 1,000+ characters into the **Password** field.
4. Observe field behavior, UI layout, and click **Login**.

---

### Expected Result
Fields should enforce a strict maximum character limit (e.g., 50–100 characters for Username), truncate excess input, or display a validation error prohibiting excessively long input.

---

### Actual Result
The Username and Password fields accept inputs of 5,000+ characters without any restriction, validation error, or truncation.

---

### Business & Technical Impact
- **UI/UX Breakdown:** Long text strings can cause UI misalignment or rendering issues.
- **Performance/Security Risk:** Unchecked long string inputs consume excessive memory and can lead to Client-side Denial of Service (DoS) or database overflow if sent to the backend.
