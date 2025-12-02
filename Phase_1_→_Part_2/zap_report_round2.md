# ZAP Round 2 Scan Report  
**Date:** 27/11/2025  
**Target:** http://localhost:8001  
**Scanner:** OWASP ZAP by Checkmarx  

---

##  Summary of Alerts

| Risk Level | Count |
|-----------|-------|
| High | 0 |
| Medium | 2 |
| Low | 4 |
| Informational | 1 |

Compared to Round 1, some issues improved but several headers are still missing.

---

##  Medium Severity Issues

### **1. Missing Content-Security-Policy (CSP) Header**
- **Instances:** Multiple  
- **Impact:** XSS attack surface increases.  
- **Status:** **NOT FIXED**  

---

### **2. Missing Anti-Clickjacking Header**
- **Instances:** All main routes  
- **Impact:** Page can be embedded into an iframe + clickjacking attack  
- **Status:** **NOT FIXED**

---

##  Low Severity Issues

### 1. Missing Strict-Transport-Security (HSTS)  
- HTTPS is not enforced.

### 2. X-Content-Type-Options Missing  
- Browser MIME sniffing possible.

### 3. Timestamp Disclosure  
- Static timestamps leaked in response.

### 4. Re-examine Cache-control  
- Some resources cached publicly.

All of these remain **NOT FIXED** from Round 1.

---

## ℹ Informational Issue
### Cache-Control  
- Public caching on some assets (JS, CSS).

---

#  Comparison With Round 1  
| Finding | Round 1 | Round 2 | Status |
|---------|---------|---------|--------|
| CSP Header Missing | Yes | Yes |  Not fixed |
| X-Frame-Options Missing | Yes | Yes |  Not fixed |
| HSTS | Yes | Yes |  Not fixed |
| X-Content-Type-Options | Yes | Yes |  Not fixed |
| Timestamp Disclosure | Yes | Yes |  Not fixed |
| CSRF Token Missing | Was present in Round 1 | Not tested here | – |

---

#  Conclusion
The application improved input validation, but **security headers remain missing**, making the system vulnerable to clickjacking and XSS vectors. No high-risk findings, but medium and low risks remain unresolved.

