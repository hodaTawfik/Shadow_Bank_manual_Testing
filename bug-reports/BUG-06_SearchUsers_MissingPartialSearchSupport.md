# Bug Report: User Search Fails to Support Partial Username Matching

- **Bug ID:** BUG-06
- **Severity:** Medium
- **Priority:** Medium
- **Component:** Back-End (Database Query Logic)
- **Environment:** Web Application (ShadowBank Frontend - Local)
- **Feature:** Search Users

---

### Summary
The search feature requires an exact match of the complete username string. Searching using partial substrings (e.g., searching `shady` for `shady1997`) fails to return matching users and triggers a "User not found" error.

---

### Steps to Reproduce
1. Ensure a user with username `shady1997` exists in the system.
2. Navigate to the **Search Users** section.
3. Enter a partial substring (`shady`) into the "Search by username" field.
4. Click the **Search** button.

---

### Expected Result
The system performs a fuzzy/wildcard search (e.g., `LIKE %shady%`) and returns all users whose usernames contain the substring `shady`.

---

### Actual Result
The search fails to return partial matches and displays a "User not found" error message.

---

### Technical Impact
Restricts user search usability by forcing users to know and input exact complete usernames.
