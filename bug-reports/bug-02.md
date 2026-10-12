# Bug Title: Missing Rate-Limiting and Account Lockout on Multiple Failed Login Attempts

- **Severity:** High / Critical (Security Vulnerability)
- **Priority:** High
- **Environment:** Web Application (ShadowBank Frontend - Local)
- **Feature:** User Authentication / Login

---

### discribtion
The system lacks rate-limiting mechanisms, CAPTCHA integration, or temporary account lockout controls, allowing unlimited consecutive failed login attempts with valid credentials and incorrect passwords. This exposes the application to Brute-Force attacks.

---

### Steps to Reproduce
1. Navigate to the Login page.
2. Enter a valid **Username** and an incorrect **Password**.
3. Click the **Login** button consecutively 5 to 10+ times.
4. Observe system response and security controls.

---

### Expected Result
After a maximum of 3–5 failed attempts, the system should enforce rate-limiting, trigger a CAPTCHA challenge, or temporarily lock out the account to prevent unauthorized automated access.

---

### Actual Result
The system accepts unlimited failed login attempts without triggering rate-limiting, temporary account lockout, or any security verification (e.g., CAPTCHA).

---

### Security Risk / Business Impact
- **Vulnerability:** Unrestricted Authentication Rate-Limiting (OWASP Top 10).
- **Impact:** Attackers can automate dictionary or brute-force attacks to compromise user accounts without detection or throttling.
