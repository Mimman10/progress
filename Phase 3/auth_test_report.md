# Authorization Test Report – Booking System (Phase 3)

## Test Environment
- Application: Booking System – Phase 3
- URL: http://localhost:8003
- Roles tested:
  - Guest (not logged in)
  - Reserver
  - Administrator
- Testing methods:
  - Browser-based manual testing
  - URL manipulation
  - Role switching
  - OWASP ZAP
  - Functional verification against specifications

---

##  Guest (Not Logged In)

###  Can do
- Can access home page `/`
- Can view booked resources list without reserver identity
- Can access login page `/login`
- Can access registration page `/register`
- Can view privacy policy and terms links

###  Cannot do
- Cannot access `/reservation` → redirected to login
- Cannot add resources
- Cannot create reservations
- Cannot access any admin pages
- Cannot access manage reservation pages
- Cannot access API endpoints directly

 Behavior matches specification

---

##  Reserver

###  Can do
- Can register with valid age (>15 years)
- Can log in successfully
- Can add new reservations
- Can view booked resources
- Can update own reservations
- Can delete own reservations
- Can log out successfully

###  Cannot do
- Cannot delete other users
- Cannot manage other users
- Cannot access admin-only user management
- Cannot bypass role restrictions via URL manipulation
- Cannot access admin API endpoints

✔️ Behavior matches specification  
✔️ Backend authorization enforced correctly

---

##  Administrator

###  Can do
- Can log in as administrator
- Can add new resources
- Can modify resources
- Can delete resources
- Can create reservations
- Can update and delete any reservation
- Can view reserver identity
- Can fully manage system data

###  Cannot do
- No unnecessary restricted actions detected

 Administrator has full control as specified  
 No over-privileged exposure detected

---

##  Hidden Pages & Endpoint Testing
- No unauthorized hidden endpoints accessible
- No IDOR issues detected
- URL manipulation attempts correctly blocked
- ZAP did not discover unprotected admin endpoints

---

##  Final Evaluation
- Authorization rules correctly enforced
- Role separation implemented properly
- Backend authorization checks present
- System complies with Principle of Least Privilege (PoLP)

**Result: PASS**
