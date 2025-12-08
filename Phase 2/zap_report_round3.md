# ZAP Report – Round 3 (Phase 2)
## Tester: Mohaimenul  
## Date: 08.12.2025

Target: http://localhost:8002  
Scan type: Baseline + Active Scan  
System: Booking System Phase 2

-----

## 1. Summary of Alerts

| Severity | Count |
|---------|-------|
| High | 0 |
| Medium | 3 |
| Low | 4 |
| Informational | 1 |

(Same alerts as Phase 1 because Phase 2 UI changed but backend security headers still missing.)

-----

## 2. Medium Risk Alerts

### 2.1 Missing Anti-CSRF Tokens
- Registration and login forms have no CSRF tokens.
- Fix: Add CSRF middleware & hidden token.

### 2.2 Content Security Policy Not Set
- No CSP header in responses.
- Fix: Add CSP rules.

### 2.3 Missing Anti-clickjacking Header
- No X-Frame-Options / frame-ancestors in CSP.
- Fix: Add header to block framing.

-----

## 3. Low-level Alerts
- Strict-Transport-Security missing  
- X-Content-Type-Options missing  
- Cache-control issues  
- Server header leaking version  

-----

## 4. Conclusion
Phase 2 same security weaknesses remain from Phase 1.  
No critical vulnerabilities, but several important headers missing.
