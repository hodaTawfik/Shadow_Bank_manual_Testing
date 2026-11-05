# Bug Report: Account Number Field Ignores User Input, Accepts Special Characters, and Generates Invalid Negative IDs

- **Bug ID:** BUG-14
- **Severity:** High
- **Priority:** High
- **Component:** Back-End (Account Generation Logic) & Front-End
- **Environment:** Web Application (ShadowBank Frontend - Local)
- **Feature:** Create Account

---

### Summary
The `Account Number` input field exhibits erratic behavior. It accepts any arbitrary data type (digits, alphabets, and symbols) of unlimited length, completely ignores the user-provided input, and auto-generates random account numbers that occasionally contain invalid negative values without sequential logic.

---

### Steps to Reproduce
1. Navigate to the **Create Account** section.
2. Input arbitrary strings containing letters, symbols, or massive digit lengths into the **Account Number** field (or leave it blank, as it's non-mandatory).
3. Fill in other required fields and submit the form.
4. Observe the generated account number in the accounts list.

---

### Expected Result
1. If the account number is system-generated, the input field should be read-only or hidden.
2. If user-input is allowed, it must enforce strict formatting (e.g., unique positive numeric strings) and reject invalid characters/symbols.
3. System-generated IDs must strictly follow a positive sequential or UUID pattern without negative integers.

---

### Actual Result
The system completely discards user inputs, accepts any chaotic strings (symbols/letters), and assigns random account IDs that sometimes result in invalid negative numbers.

---

### Technical Impact
Corrupts financial data integrity and creates invalid account identifiers containing negative signs.
<img width="1107" height="389" alt="image" src="https://github.com/user-attachments/assets/4a7658d0-a5ce-4902-a4a6-d4002ac38f10" />
<img width="504" height="303" alt="image" src="https://github.com/user-attachments/assets/ba1bac1d-38ae-460a-ac6e-17089b6a9a30" />
