# Phase 2 – Penetration & Functionality Test Report
## Tester: Mohaimenul  
## System: Booking System – Phase 2  
## Date: 08.12.2025

-----

## 1. Scope of Testing
Phase 2 updated application was tested. Testing included:
- User registration
- User login
- Resource management
- Reservation creation
- Logout behaviour
- Basic security behaviour checks

Phase 2 must fix/extend issues from Phase 1.

-----

## 2. Registration Tests

### ✔ Test 1 – New user registration  
**Result:** PASS  
New users can register normally.

### ✔ Test 2 – Underage user  
**Result:** PASS  
Birthdate set to < 15 years → Registration rejected.

### ✔ Test 3 – Duplicate email  
**Result:** PASS  
Existing email → “Email already in use!” message shown.

### ✔ Test 4 – Empty inputs  
**Result:** PASS  
Browser validation blocks empty submission.

### ✔ Test 5 – Wrong formats  
**Result:** PASS  
Invalid email format → validation message shown.

-----

## 3. Login Tests

### ✔ Test 6 – Wrong password  
**Result:** PASS  
Correct error message shown.

### ✔ Test 7 – Invalid email format  
**Result:** PASS  
Browser validation works.

### ✔ Test 8 – Correct login  
**Result:** PASS  
System shows “User logged in successfully!”

⚠ **Issue Found:**  
After login, UI does NOT show:
- Logout button  
- Add resource  
- Add reservation  
This prevents further manual functionality testing.

-----

## 4. Resource Tests

### ✖ Test 9 – Add a new resource
**Result:** FAIL  
After login → No option appears to add a resource.

### ✖ Test 10 – Resource list update
**Result:** FAIL  
No UI element available.

### ✖ Test 11 – Empty resource validation  
**Result:** FAIL  
Feature inaccessible → cannot test.

-----

## 5. Reservation Tests

### ✖ Test 12 – Add reservation page visible?
**Result:** FAIL  
Add reservation option missing.

### ✖ Test 13 – Invalid time rejection  
**Result:** NOT TESTABLE

### ✖ Test 14 – Past reservation  
**Result:** NOT TESTABLE

### ✖ Test 15 – Overlapping reservation  
**Result:** NOT TESTABLE

-----

## 6. Logout Test

### ✖ Test 16 – Logout available?
**Result:** FAIL  
Logout button does not exist in UI.

-----

## 7. Summary of Findings (Phase 2)

| Area | Result |
|------|--------|
| Registration | ✔ Passed |
| Login | ✔ Passed |
| Resource Management | ❌ Failed |
| Reservation | ❌ Failed |
| Logout | ❌ Failed |
| Security checks | Basic Tests Passed |

**Final Result:** Application incomplete → core features missing.

-----

## 8. Recommendations
- Add missing UI buttons (Add resource, Add reservation, Logout)
- Ensure login session state updates homepage
- Fix broken Phase 2 routing
- Re-test resource & reservation flow after fixes
