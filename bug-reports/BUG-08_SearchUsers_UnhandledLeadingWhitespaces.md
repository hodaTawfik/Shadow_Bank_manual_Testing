# Bug Report: Search Query Fails to Trim Leading Whitespaces

- **Bug ID:** BUG-08
- **Severity:** Low / Medium
- **Priority:** Medium
- **Component:** Front-End (Input Sanitization)
- **Environment:** Web Application (ShadowBank Frontend - Local)
- **Feature:** Search Users

---

### Summary
While the search input field successfully trims trailing spaces, it fails to trim leading spaces (e.g., `" shady1997"`), causing the backend lookup to treat spaces as part of the username string and fail.

---

### Steps to Reproduce
1. Ensure user `shady1997` exists.
2. Enter `" shady1997"` (with a space before the username) into the search field.
3. Click **Search**.

---

### Expected Result
Front-end input handler should trim both leading and trailing spaces (`.trim()`) before dispatching the search request, returning the matching user.

---

### Actual Result
Leading spaces are retained in the request string, resulting in a "User not found" error.

---

### Technical Impact
Inconsistent input sanitization causing search failures on accidental leading spaces (common during copy-pasting).
