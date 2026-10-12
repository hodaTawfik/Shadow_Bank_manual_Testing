# Bug Title: Raw SQL Queries and Database Stack Trace Exposed on UI during 500 Internal Server Error

- **Bug ID:** BUG-06
- **Severity:** Critical (Security Vulnerability & Data Leak)
- **Priority:** High
- **Environment:** Web Application (ShadowBank Frontend - Local | Browser: Microsoft Edge)
- **Feature:** Global Error Handling / Database Persistence & Security

---

### Summary
When an internal server error occurs (such as an idle-time database connection drop in the in-memory H2 DB), the application leaks raw SQL statements, internal database schema details, and table structures directly on the user interface. Additionally, the in-memory database drops active tables during inactivity, disrupting application functionality.

---

### Steps to Reproduce
1. Navigate to the application: `http://localhost:5173/`
2. Leave the application running and idle for an extended period (or simulate a database connection failure).
3. Perform any feature action that initiates a backend database query (e.g., Create Account or Search Users).
4. Observe the red error banner displayed at the top of the UI screen.

---

### Expected Result
1. **UI Handling:** The system should handle 500 errors gracefully, displaying a safe, user-friendly error message (e.g., *"An unexpected error occurred. Please try again later."*) without revealing sensitive backend schema or SQL code.
2. **Database Persistence:** The database connection and tables should remain persistent and accessible without dropping connection/tables during idle times.

---

### Actual Result
The UI displays an unhandled raw JSON 500 error exposing internal infrastructure details:
`Table "USERS" not found (this database is empty); SQL statement: select u1_0.id from users...`

---

### Business & Technical Impact
- **Security Information Disclosure (CWE-209):** Exposing raw SQL statements and table names allows malicious actors to map the database structure and craft targeted SQL Injection attacks.
- **System Reliability:** Loss of database persistence during idle time forces manual application restarts, causing service degradation.

<img width="1193" height="623" alt="Image" src="https://github.com/user-attachments/assets/a4421afe-9ee3-44e7-83b7-5008ce3461e6" />
