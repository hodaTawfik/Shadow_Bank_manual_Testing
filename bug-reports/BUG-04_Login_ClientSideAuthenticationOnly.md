
# Bug Report: Client-Side Only Authentication and Lack of Secure Session Management

- **Severity:** Critical (Architectural Security Vulnerability)
- **Priority:** High
- **Environment:** Web Application (ShadowBank Frontend - Local)
- **Feature:** User Authentication / Session Management

---

### Summary
The application performs authentication entirely on the client-side without initiating network requests to a backend server. No secure HTTP-Only cookies, JWT tokens, or session identifiers are generated, allowing access validation via hardcoded logic or local scripts.

---

### Steps to Reproduce
1. Open the browser's Developer Tools (F12) and switch to the **Network** tab.
2. Enter valid or test credentials in the Login form and click **Login**.
3. Inspect network traffic during and after form submission.
4. Check Storage/Cookies for generated session tokens or HTTP-Only cookies.

---

### Expected Result
1. Login triggers a secure `POST` request to the backend API (`/api/v1/auth/login`).
2. Backend authenticates credentials and returns a secure response (`200 OK`) containing an HTTP-Only cookie or session identifier (e.g., JWT).
3. Authorization state relies strictly on server-side token validation.

---

### Actual Result
No HTTP authentication requests are transmitted to a backend API upon login. Authentication relies purely on static client-side/hardcoded logic, and no secure session cookies or authorization tokens are generated or saved.

---

### Business & Technical Impact
- **High Security Risk:** Client-side authentication logic can easily be bypassed, inspected, or manipulated via browser developer tools.
- **Broken Access Control:** Without server-validated session tokens, protected application routes cannot enforce actual access control.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/7eca9236-1683-4000-8080-1186451c2e1b" />
