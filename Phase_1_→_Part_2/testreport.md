# Phase 1 / Part 2 — Manual Test Report  
**Author:** Mohaimenul  
**Date:** 27/11/2025  

The following 5 manual tests were performed on the updated Booking System (Phase 1 / Part 2) running on **http://localhost:8001**.  
The focus was on registration validation, security improvements, and functionality fixes.

---

##  Test Case 1: Invalid Email Format Blocking  
**Objective:** Ensure invalid email formats are rejected.  
**Steps:**  
1. Enter invalid email such as: `mimma@@gmail`.  
2. Fill password, birthdate, role.  
3. Click Register.

**Expected Result:** Browser or backend should block registration.  
**Actual Result:** System blocked invalid email with validation message.  
**Status:** **PASS**  

---

## Test Case 2: Registration Without Password  
**Objective:** Check if password field validation is enforced.  
**Steps:**  
1. Enter valid email.  
2. Leave password empty.  
3. Fill birthdate and role.  
4. Submit.

**Expected:** Should show "Please fill in this field".  
**Actual:** Browser validated and blocked submission.  
**Status:** **PASS**  

---

## Test Case 3: Underage User Registration (Age < 15)  
**Objective:** Verify age restriction enforcement.  
**Steps:**  
1. Enter valid email + password.  
2. Birthdate = a recent year (example: 05/11/2025).  
3. Role = Reserver.  
4. Submit.

**Expected:** System should reject user under 15 years old.  
**Actual:** System **accepted the registration** (user underage allowed).  
**Status:** **FAIL**  
**Vulnerability Type:** Broken Business Logic  
**Impact:** Violates client requirement and GDPR (collecting child data).  

---

## Test Case 4: XSS Attempt in Email Field  
**Objective:** Test sanitization of potentially malicious input.  
**Steps:**  
1. Enter `<script>alert(1)</script>` in email.  
2. Fill other fields.  
3. Submit.

**Expected:** Input should be rejected.  
**Actual:** Browser rejected because email format invalid.  
**Status:** **PASS** (front-end prevented XSS payload)

---

## Test Case 5: Duplicate Email Registration  
**Objective:** Ensure duplicate accounts cannot be created.  
**Steps:**  
1. Register user with email A.  
2. Try registering again with same email.

**Expected:** Should show error "Email already in use".  
**Actual:** System shows proper error page.  
**Status:** **PASS**

---

#  Summary  

| Test | Description | Status |
|------|-------------|--------|
| TC1 | Invalid email blocked | PASS |
| TC2 | Missing password | PASS |
| TC3 | Underage user allowed |  FAIL |
| TC4 | XSS via email field | PASS |
| TC5 | Duplicate email | PASS |

---

#  Critical Issue (Requires Fix)
### **Underage user registration still allowed → NOT FIXED**
- Business rule requires users to be **over 15 years**.  
- Application still accepts users younger than 15.  
- High impact: GDPR non-compliance.

---

#  Evidence
Screenshots stored in:  
`Phase_1_→_Part_2/screenshots/`

---

#  Conclusion
Phase 1 / Part 2 introduced several improvements, but **age validation remains unfixed** and needs developer attention immediately.
