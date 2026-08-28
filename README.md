# 🏦 Banking Web Application - Exploratory & Manual QA Testing

Welcome to the Quality Assurance documentation for the Local Banking Web Application project. This repository contains the complete test artifact deliverables, including exploratory scenarios, test cases execution, bug reports, and testing summary reports.

## 📌 Project Overview
The objective of this project is to perform end-to-end manual, exploratory, and basic security testing on a full-stack Banking Web Application running in a local environment.

* Target Feature: Authentication, Login System, create users, create accounts, create transactions 
* Testing Types Covered: Functional, Boundary Value Analysis, Negative Testing, UI Validation, Session Management, and Client-Side Security.

---

## 🔗 Original Source Repositories
The application architecture is divided into two separate repositories managed by the instructor:
* Frontend Repository: [(https://github.com/Shady1997/shadow_Bank_Frontend_React)]
* Backend Repository: [https://github.com/Shady1997/-Mobile_Bank_API_RestFul]


## 📑 Repository Structure & Documentation
* Test-Cases/: Contains 20+ comprehensive Test Cases covering functional, security, and edge-case scenarios (.csv / .xlsx).
* Test-Reports/: Detailed Test Execution Summary Report including pass/fail metrics and test coverage.
* Bug-Reports/: Detailed documentation of identified critical security and logical defects.

---

## 🚨 Key Testing Findings & Critical Bugs
During the exploratory testing phase of the Login feature, several high-severity security and architectural issues were identified:

1. [Critical] Client-Side Only Authentication:
   * Login logic is handled statically on the UI layer. No HTTP authorization requests are sent to the backend server, and no session cookies/JWT tokens are maintained.
2. [Medium] Multi-Tab Session Synchronization Failure:
   * Logging out from one browser tab leaves active user sessions functional in other open tabs.
3. [Medium] Missing Rate Limiting:
   * Unlimited failed login attempts allowed without temporary lockout or rate throttling.

---

## 🐞 Tracked Issues & Bug Reports
Links to the reported issues on the original application repositories / documented bug tickets:
* 🔗 [Issue #12: Client-side Authentication Bypass & Static Login Logic](Insert Link or Local Markdown path)
* 🔗 [Issue #15: Missing Character Length Constraints on Input Fields](Insert Link or Local Markdown path)

---

## 🛠 Tools Used
* Test Management: Google Sheets
* Developer Tools: Chrome DevTools (Network Tab, Application Memory & Storage)
* API Testing: Postman
* Issue Tracking: GitHub Issues

---

Tested & Documented by: Hoda Tawfik  
Role: Quality Assurance Engineer
