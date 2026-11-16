# Bug Report: System Approves Self-Transfer (From Account equals To Account) Displaying False Success Without Balance Updates

- **Bug ID:** BUG-18
- **Severity:** Critical
- **Priority:** High
- **Component:** Business Logic / Transaction Validation & State Management
- **Environment:** Web Application (ShadowBank Frontend - Local)
- **Feature:** Create Transaction (Transfer Type)

---

### Summary
When creating a `Transfer` transaction where the `From Account ID` and `To Account ID` are set to the exact same account, the system incorrectly processes the transaction, displays a success message, and logs it in the table, while leaving the account balances completely unchanged.

---

### Steps to Reproduce
1. Navigate to the **Create Transaction** section.
2. Select **Transfer** as the transaction type.
3. Input the exact same Account ID into both the **From Account ID** and **To Account ID** fields (e.g., `123`).
4. Enter a valid amount and click **Create Transaction**.

---

### Expected Result
The system must validate that the source and destination accounts are distinct, rejecting self-transfers with an appropriate validation error message before execution.

---

### Actual Result
The application falsely reports transaction success and logs the entry, but account balances remain completely static (neither deducted nor credited).

---

### Technical Impact
Misleads the user with a false "Success" status for an invalid logical operation and indicates weak server-side boundary validation.
