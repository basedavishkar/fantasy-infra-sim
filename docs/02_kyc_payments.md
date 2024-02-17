# 🔐 KYC + 💸 Payments dump

### KYC flow dump (semi-working as of now)
- PAN OCR → NSDL check
- Aadhaar eSign (digio maybe?) — fallback = selfie + consent checkbox
- max 3 fails → manual review
- store KYC status in user.profile.state.kyc

### Payments (Razorpay 1st, Cashfree fallback?)
- razorpay deposit + withdraw flow (2 endpoints per)
- webhook: verify sig → queue task → poll until success
- exponential retry (5x max?) on failures
- log txn_id + status → audit table

// todo: maybe build a /kyc/status endpoint for support team?
