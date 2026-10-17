# Bug Report: UI Retains Stale Search Results in Table Upon Subsequent Search Failures

- **Bug ID:** BUG-10
- **Severity:** Medium
- **Priority:** High
- **Component:** Front-End (State Management / UI Refresh)
- **Environment:** Web Application (ShadowBank Frontend - Local)
- **Feature:** Search Users / Users List Table

---

### Summary
When a subsequent search fails or returns an error, the application displays an error message toast/banner but fails to clear or update the "Users List" table. Consequently, previous search results persist in the UI, creating misleading data state for the user.

---

### Steps to Reproduce
1. Search for a valid user (e.g., `shady1997`) so that the table populates with results.
2. Enter a non-existing or invalid username into the search box (e.g., `invalid_user`).
3. Click **Search**.
4. Observe the error message and the contents of the "Users List" table.

---

### Expected Result
Upon receiving an error response, the front-end state should clear the table or display an empty state ("No users found") to reflect the status of the latest search query.

---

### Actual Result
The top error banner appears, but the table continues to display the stale user records from the previous successful search.

---

### Technical Impact
**Misleading Data / Broken State Management:** Users may mistakenly assume the displayed table records correspond to the newly searched query.
