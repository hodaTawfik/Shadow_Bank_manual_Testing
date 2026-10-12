**Title**
Unhandled 500 Server Error exposes raw SQL queries and H2 Database details on UI
**Description:**
When the backend encounters an internal error (such as a database disconnection or missing in-memory tables after inactivity), the system exposes raw SQL queries, table names (USERS), and stack traces directly on the UI. Additionally, the in-memory database loses its tables after idle time, forcing a manual server restart.

**Steps to Reproduce:**
1. open website: http://localhost:5173/
2.  Leave the application running and idle for an extended period (or trigger a database connectivity failure).
3. Perform any action that queries the database (e.g., create user or searching users).
4. Observe the red error massage displayed on the top of the UI screen.

Environment:
Windows 11
Browser: Microsoft edge

**Severity:** Critical

**Expected Result:**
UI Handling: The system should catch 500 errors gracefully and show a user-friendly error message without leaking sensitive SQL or DB schema information.
Database Persistence: The database schema and tables should remain persistent and accessible without dropping connection/tables during idle times.

**Actual Result:**
The UI displays a raw JSON 500 response exposing: Table "USERS" not found (this database is empty); SQL statement: select u1_0.id from users..., revealing database infrastructure to the client.

<img width="1193" height="623" alt="Image" src="https://github.com/user-attachments/assets/a4421afe-9ee3-44e7-83b7-5008ce3461e6" />
