# OWASP ZAP Report – Phase 1 / Part 1 (First Round)

Target: `http://localhost:8000` (Booking System – registration page)  
Scan type: Baseline / active scan against public pages and `/register`  
Date: 27.11.2025  
Tester: Mohaimenul

---

## 1️⃣ Summary of Alerts

| Risk Level     | Number of Alerts |
|----------------|------------------|
| High           | 0                |
| Medium         | 3                |
| Low            | 4                |
| Informational  | 1                |

---

## 2️⃣ Alerts (overview)

| Name                                                         | Risk Level | Instances |
|--------------------------------------------------------------|-----------:|----------:|
| Absence of Anti-CSRF Tokens                                  | Medium     | 1         |
| Content Security Policy (CSP) Header Not Set                 | Medium     | 12        |
| Missing Anti-clickjacking Header (X-Frame-Options / CSP)     | Medium     | 12        |
| Server Leaks Version Information via `Server` Header         | Low        | 1         |
| Strict-Transport-Security Header Not Set                     | Low        | 17        |
| Timestamp Disclosure – Unix                                  | Low        | 8         |
| X-Content-Type-Options Header Missing                        | Low        | 16        |
| Re-examine Cache-Control Directives                          | Info       | 10        |

---

## 3️⃣ Key Alert Details

### 3.1 Absence of Anti-CSRF Tokens – Medium

- **URL:** `http://localhost:8000/register`  
- **Description:** Registration form (`<form action="/register" method="POST">`) does not include a recognised anti-CSRF token field.  
- **Impact:** Attacker could try to trigger unwanted registration requests from a victim’s browser.  
- **Recommendation:** Add a unique CSRF token to the form and validate it server-side (see OWASP CSRF Prevention Cheat Sheet).

---

### 3.2 Content Security Policy (CSP) Header Not Set – Medium

- **URLs:** `http://localhost:8000/`, `/register`, and static resources.  
- **Description:** No `Content-Security-Policy` header is present in responses.  
- **Impact:** Higher risk of XSS and content injection if other weaknesses exist.  
- **Recommendation:** Configure a CSP header that restricts allowed script, style, image, and frame sources.

---

### 3.3 Missing Anti-clickjacking Header – Medium

- **URLs:** `http://localhost:8000/`, `/register`, `/static/footer.html`, etc.  
- **Description:** No `X-Frame-Options` or CSP `frame-ancestors` directive set.  
- **Impact:** Application pages can be framed by external sites, enabling clickjacking attacks.  
- **Recommendation:** Add `X-Frame-Options: DENY` (or `SAMEORIGIN`) or use `Content-Security-Policy: frame-ancestors 'none';`.

---

### 3.4 Strict-Transport-Security Header Not Set – Low

- **Description:** HTTPS responses from related services do not include `Strict-Transport-Security`.  
- **Impact:** Browsers may still allow HTTP downgrade or insecure connections.  
- **Recommendation:** When the application is served over HTTPS, configure `Strict-Transport-Security` with an appropriate `max-age`.

---

### 3.5 X-Content-Type-Options Header Missing – Low

- **URLs:** `http://localhost:8000/`, `/register`, and static JS/CSS.  
- **Description:** `X-Content-Type-Options` is not set to `nosniff`.  
- **Impact:** Some browsers might MIME-sniff content and interpret it as a different type.  
- **Recommendation:** Add `X-Content-Type-Options: nosniff` to all responses.

---

### 3.6 Server & Timestamp Information Disclosure – Low / Info

- **Description:** Some external responses leak server version information (`Server` header) and Unix timestamps.  
- **Impact:** Low; could help an attacker fingerprint versions and behaviour.  
- **Recommendation:**  
  - Suppress or generalise `Server` headers where possible.  
  - Verify that exposed timestamps and cache settings do not reveal sensitive information.

---

## 4️⃣ Conclusion

The ZAP scan did not find any critical (High) vulnerabilities, but it highlighted several missing security headers and the lack of CSRF protection on the registration form. These results support the manual findings and should be addressed in the next iteration before the second test round.

