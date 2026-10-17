# Bug Report: Search Functionality is Strictly Case-Sensitive

- **Bug ID:** BUG-07
- **Severity:** Medium
- **Priority:** Medium
- **Component:** Back-End / Database Query
- **Environment:** Web Application (ShadowBank Frontend - Local)
- **Feature:** Search Users

---

### Summary
The user search query is strictly case-sensitive. Inputting a valid username with mismatched letter casing (e.g., `SHADY1997` instead of `shady1997`) fails to retrieve the user record.

---

### Steps to Reproduce
1. Ensure a user with username `shady1997` exists.
2. Type `SHADY1997` (uppercase) into the "Search by username" field.
3. Click the **Search** button.

---

### Expected Result
The search query should be case-insensitive (e.g., converting inputs to lowercase or using `ILIKE`), returning `shady1997`.

---

### Actual Result
The system returns a "User not found" error message due to letter case mismatch.

---

### Technical Impact
Reduces usability and leads to false "Not Found" errors for users inputting varied casing on web forms.
