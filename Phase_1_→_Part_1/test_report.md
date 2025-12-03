# Penetration Testing Report – Phase 1 / Part 1 (User Registration)

System: Booking System – User Registration  
Tester: Mohaimenul  
Method: Manual testing + OWASP ZAP automated scan  
Approach: White-hat, gray-box

---

## 1️⃣ Introduction

**Tester(s)**  
- Name: Mohaimenul

**Purpose**  
- Identify anomalies, vulnerabilities, and privacy issues in the user registration flow of the Booking System (Phase 1).

**Scope**

- **Tested components**
  - `/register` endpoint
  - Registration form fields: username (email), password, birthdate
  - Server responses and validation messages
  - Basic security headers on `http://localhost:8000` and `/register`
  - OWASP ZAP scan against the registration page

- **Exclusions**
  - Login and logout functionality
  - Reservation and admin features
  - Denial-of-Service or network-level attacks
  - Source code review

**Test approach**  
- Gray-box web application testing (limited knowledge, access only via browser and Docker lab environment).

**Test environment & dates**

- **Environment**
  - OS: Windows 11 (local laptop)
  - Runtime: Docker Desktop, Booking System lab stack via `docker compose up -d`
  - Database: PostgreSQL in Docker (default configuration from course compose file)
  - Browser: Google Chrome
  - Target URL: `http://localhost:8000` and `http://localhost:8000/register`

- **Dates**
  - Start of testing: 27.11.2025  
  - End of testing: 27.11.2025  

**Assumptions & constraints**

- Test system is an intentionally vulnerable lab environment (not production).
- Only test accounts and dummy data were used (no real personal data).
- Time for testing was limited, so not all possible attack vectors were covered.
- No changes were made directly to server configuration or source code.

---

## 2️⃣ Executive Summary

**Short summary (1–2 sentences)**  
The first penetration test round focused on the registration page of the Booking System. No critical vulnerabilities were found, but several medium-risk logic and security-header issues were identified (age check, duplicate accounts, missing CSRF and security headers) that should be fixed before moving to later phases.

**Overall risk level:** **Medium**

**Top 5 immediate actions**

1. Enforce the “over 15 years old” age rule on the server side and block underage registrations.
2. Enforce unique email/username values so the same email cannot be registered multiple times.
3. Add CSRF protection to the registration form (anti-CSRF token and server-side validation).
4. Add recommended security headers (CSP, X-Frame-Options or `frame-ancestors`, HSTS, X-Content-Type-Options).
5. Review caching and information-disclosure related headers (Cache-Control, Server, timestamps) and harden configuration.

---

## 3️⃣ Severity scale & definitions

| Severity Level | Description                                                                                         | Recommended Action                 |
|----------------|-----------------------------------------------------------------------------------------------------|------------------------------------|
| 🔴 **High**    | Serious vulnerability that can lead to full system compromise or data breach (e.g. SQLi, RCE).     | Immediate fix required             |
| 🟠 **Medium**  | Significant issue that may require some conditions or user interaction (e.g. XSS, CSRF, logic).    | Fix as soon as possible            |
| 🟡 **Low**     | Minor issue or configuration weakness (e.g. version disclosure).                                    | Fix in normal maintenance cycle    |
| 🔵 **Info**    | No direct risk, but useful for hardening (e.g. missing headers, generic information).              | Monitor and fix when convenient    |

---

## 4️⃣ Findings

(One row per main finding from manual tests and ZAP scan.)

| ID   | Severity | Finding                                   | Description                                                                                      | Evidence / Proof |
|------|----------|-------------------------------------------|--------------------------------------------------------------------------------------------------|------------------|
| F-01 | 🟠 Medium | Underage registration accepted           | Registration allows users younger than 15 to register, which breaks the stated age rule and may cause GDPR/privacy issues with minors. | Manual test: birthdate < 15 years old was accepted; registration succeeded (screenshot from `/register`). |
| F-02 | 🟠 Medium | Duplicate email registration allowed      | The same email/username can be registered more than once, which may cause account confusion and make account takeover easier. | Manual test: same email registered twice without error message (screenshot evidence). |
| F-03 | 🟠 Medium | No CSRF protection on registration form   | ZAP reported missing anti-CSRF token on the registration form, so an attacker could try to create accounts on behalf of logged-in users. | ZAP alert: “Absence of Anti-CSRF Tokens” on `http://localhost:8000/register`. |
| F-04 | 🟡 Low    | Missing key security headers              | Several important headers are missing, such as CSP, X-Frame-Options, HSTS, and X-Content-Type-Options, increasing risk of clickjacking and content injection. | ZAP alerts: “Content Security Policy Header Not Set”, “Missing Anti-clickjacking Header”, “Strict-Transport-Security Header Not Set”, “X-Content-Type-Options Header Missing”. |
| F-05 | 🔵 Info   | Caching & minor information disclosure    | Some responses are cacheable and expose timestamps or server information; risk is low but hardening is recommended. | ZAP alerts: “Re-examine Cache-control Directives”, “Timestamp Disclosure – Unix”, “Server Leaks Version Information”. |

---

## 5️⃣ OWASP ZAP Test Report (Attachment)

**Purpose**

- Provide detailed results from the automated scan of the Booking System registration page.
- Support the manual findings and highlight missing security headers and CSRF protection.

**File**

- The full ZAP report for the first round is saved as:  
  `zap_report_round1.md` (same folder as this report).

The report contains:
- Scan target and scope (localhost:8000)
- Summary of alert counts by risk level
- Detailed description of each alert type and affected URLs.
