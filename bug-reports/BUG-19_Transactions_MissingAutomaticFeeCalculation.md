# Bug Report: Deposit Transaction Fails to Automatically Apply Off-Hours and Standard Transaction Fees

- **Bug ID:** BUG-19
- **Severity:** High
- **Priority:** High
- **Component:** Back-End (Fee Calculation Engine)
- **Environment:** Web Application (ShadowBank Frontend - Local)
- **Feature:** Create Transaction (Deposit)

---

### Summary
The system fails to automatically calculate and apply transaction fees (such as the 0.1% general fee or the +5 EGP off-hours deposit fee). It relies entirely on manual user input in the optional fee field, violating the required business rules.

---

### Steps to Reproduce
1. Note the system time is outside working hours (e.g., 8:00 PM).
2. Navigate to the **Create Transaction** section.
3. Select **Deposit** and enter a valid amount (e.g., `1000`) into the source account.
4. Leave the manual **Fee (optional)** field blank or at default `0`.
5. Click **Create Transaction**.

---

### Expected Result
The backend business logic should automatically detect the deposit timing (off-hours) and calculate/add the mandatory +5 EGP fee to the transaction record without requiring manual user entry.

---

### Actual Result
The system processes the transaction with `0` fees unless the user manually types a fee into the form.

---

### Technical Impact
Violates automated banking compliance and fee collection rules, resulting in revenue loss or manual calculation discrepancies.
