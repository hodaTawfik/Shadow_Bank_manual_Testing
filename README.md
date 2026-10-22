# Banking Web Application - Exploratory & Manual QA Testing

![Status](https://img.shields.io/badge/Status-In%20Progress%20%2F%20Active%20Testing-blue)

Welcome to the Quality Assurance documentation for the Local Banking Web Application project (**ShadowBank**). This repository contains test deliverables, including exploratory scenarios, test cases execution, bug reports, and testing summary reports.

---

## Project Status
> **Note:** This testing suite is currently **Active & Under Continuous Development**. Test cases, automation integration, and defect documentation are being systematically updated.

---

## Project Overview
The objective of this project is to perform end-to-end manual, exploratory, and security testing on a full-stack Banking Web Application running in a local environment.

- **Target Features:** Authentication, User Management, Account Creation, and Transaction Operations.
- **Testing Types Covered:** Functional, Boundary Value Analysis, Negative Testing, UI/UX Validation, Session Management, and Client-Side Security.

---

## Original Source Repositories
The application architecture is divided into two separate repositories managed by the course instructor:
- **Frontend Repository:** [ShadowBank React Frontend](https://github.com/Shady1997/shadow_Bank_Frontend_React)
- **Backend Repository:** [ShadowBank RESTful API](https://github.com/Shady1997/-Mobile_Bank_API_RestFul)

---

## Repository Structure & Deliverables
- `test-cases/`: Comprehensive Test Cases covering functional, UI, and edge-case scenarios (.csv / .xlsx / Google Sheets).
- `bug-reports/`: Detailed markdown documentation of identified functional, logical, and security defects.
- `test-reports/`: Test Execution Summary Report including pass/fail metrics and coverage *(In Progress)*.

---

## Key Findings & Critical Vulnerabilities

During testing, several high-severity architectural, security, and logical issues were identified:

- 🚨 **[Critical] Client-Side Only Authentication:** Login logic is handled purely on the front-end without network requests or secure session management. [View Report](./bug-reports/BUG-04_Login_ClientSideAuthenticationOnly.md)
- 🚨 **[Critical] Data & Schema Exposure:** 500 server errors leak raw SQL statements and H2 internal database schema directly on the UI. [View Report](./bug-reports/BUG-05_CreateAccount_RawSqlDataLeakOnServerError.md)
- ⚠️ **[High] Missing Rate Limiting:** Unlimited failed login attempts allowed without temporary lockout or throttling. [View Report](./bug-reports/BUG-02_Login_MissingRateLimiting.md)

📂 **[Browse All Bug Reports Folder](./bug-reports/)** — *Check the full directory for functional, UI, and edge-case bug reports.*

---

## 🛠 Tools & Technologies Used
- **Test Management:** Google Sheets
- **Environment & Developer Tools:** Chrome DevTools, DevTools Network & Storage Tabs
- **API Testing:** Postman
- **Defect Tracking & Version Control:** Git, GitHub Issues, Markdown Documentation

---

**Tested & Documented by:** Hoda Tawfik  
**Role:** Software Quality Assurance Engineer  
**Contact:** [Email](mailto:hodaa.tawfik11@gmail.com) | [LinkedIn](https://linkedin.com)
