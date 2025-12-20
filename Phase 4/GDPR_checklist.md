# GDPR Compliance Checklist – Booking System (Phase 4)

## Personal data mapping and minimization
✅ All personal data identified (email, role, birthdate).
✅ Only necessary data is collected (email, role, age verification).
✅ User age is collected to verify users are over 15 years old.

## User registration and management
✅ Registration includes acceptance of Terms of Service.
⚠️ Users can view personal data, but cannot edit or delete account themselves.
✅ Administrator can delete users (right to be forgotten).
✅ Underage users (under 15) cannot register or book resources.

## Booking visibility
✅ Bookings are visible publicly without login.
✅ No personal data is exposed to non-logged-in users.
⚠️ Reserver email is visible only to logged-in admin and reserver.

## Access control and authorization
✅ Only administrators can add, modify, and delete resources.
✅ Role-based access control is implemented (reserver / administrator).
⚠️ Admin access exists but no misuse of data observed.

## Privacy by Design principles
✅ Minimal personal data collected by default.
⚠️ Logs exist but do not appear to store excessive personal data.
✅ Forms are designed with limited and necessary fields.

## Data security
⚠️ Protection against XSS, CSRF, SQLi assumed but not fully verifiable.
⚠️ Passwords are hashed (algorithm not explicitly documented).
⚠️ Backup and recovery processes are not documented.
⚠️ Data location (EU storage) is not explicitly stated.

## Data anonymization and pseudonymization
⚠️ Data is pseudonymized (email used as identifier).
❌ No full anonymization mechanism implemented.

## Data subject rights
❌ Users cannot download their personal data.
⚠️ Users cannot request deletion directly (admin only).
⚠️ Consent withdrawal mechanism is limited.

## Documentation and communication
✅ Privacy policy is accessible from the footer.
✅ Terms of Service are available and must be accepted.
❌ No documented data breach response process.

---

**Legend:**  
✅ Pass  
⚠️ Attention required  
❌ Missing / Not implemented
