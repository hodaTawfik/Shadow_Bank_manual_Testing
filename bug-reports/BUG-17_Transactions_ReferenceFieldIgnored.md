# Bug Report: Transaction Reference Field Discards User Input and Auto-Generates Random IDs

- **Bug ID:** BUG-17
- **Severity:** High
- **Priority:** High
- **Component:** Back-End / Transaction Processing Logic
- **Environment:** Web Application (ShadowBank Frontend - Local)
- **Feature:** Create Transaction

---

### Summary
The `Transaction Reference` input field fails to persist the unique reference string provided by the user. The application completely discards the custom input and auto-generates random reference numbers for the transaction records.

---

### Steps to Reproduce
1. Navigate to the **Create Transaction** section.
2. Enter a specific unique string into the **Transaction Reference** field (e.g., `REF-TEST-2026`).
3. Complete the remaining fields (From Account, Type, Amount) and click **Create Transaction**.
4. Inspect the newly created record in the **Transactions List** table.

---

### Expected Result
The system should store and display the exact unique reference string entered by the user to maintain accurate audit trails.

---

### Actual Result
The system ignores the user-provided reference and assigns an arbitrary or random reference ID instead.

---

### Technical Impact
Breaks unique transaction tracking and prevents users or administrators from referencing specific external transaction IDs.
