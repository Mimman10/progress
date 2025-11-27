Penetration Testing Report – Phase 1 (User Registration)

System: Booking System – User Registration
Tester: Mohaimenul
Method: Manual Testing + Automated Scan (ZAP)
Approach: White-Hat, Gray-Box

1. Introduction

This report documents the penetration testing performed on the user registration module of the Booking System (Phase 1).
The goal was to identify anomalies, vulnerabilities, and privacy issues.

Testing focused on:

Input validation

Authentication logic

Basic security controls

GDPR & Privacy by Design (PbD) principles

2. Scope
In Scope

/register endpoint

Registration form: email / password / birthdate

Server responses and validation

Security headers

Automated scanning (ZAP)

Out of Scope

Login

Reservations

Admin functionality

DoS & network-level attacks

3. Methodology

Manual testing

ZAP by Checkmarx scanning

OWASP Top 10 guidelines

Observation of browser behavior & error messages

No exploitation of real user data

Testing done locally via Docker

4. Manual Test Cases & Findings
### Test Case 1 – Invalid Email Input

Objective: Check validation for incorrect email format
Steps: Enter email: test123
Expected: Reject invalid email
Actual Result: PASS
System showed “Insert valid email” and did not allow registration.
Status: ✔️ Pass
Notes: Email validation is correctly implemented.

Test Case 2 – Underage User Registration

Objective: Verify age rule (>15 years old required)
Steps: Use birthdate < 15 years old
Expected: System rejects registration
Actual Result: ❌ System accepted the underage user
Status: ❌ Fail
Vulnerability: Business Logic Flaw
Impact: Minors can access system → GDPR risk

Test Case 3 – Missing Password

Objective: Ensure password is mandatory
Steps: Leave password empty
Expected: System blocks registration
Actual Result: ✔️ System prevented registration
Status: Pass
Notes: Password validation works.

Test Case 4 – XSS Attempt in Email Field

Objective: Test input sanitization
Payload: <script>alert('XSS')</script>
Expected: Reject XSS payload
Actual Result: ✔️ System blocked input
Displayed “Insert valid email”.
Status: Pass
Notes: XSS NOT possible through email field.

Test Case 5 – Duplicate Email Registration

Objective: Check if email uniqueness enforced
Steps: Register same email twice
Expected: Reject duplicate
Actual Result: ❌ System allowed same email again
Status: Fail
Vulnerability: Duplicate accounts allowed
Impact: Account confusion & potential takeover