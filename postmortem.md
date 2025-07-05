# Postmortem: ₹1.2L Refund Incident (July 2024)

- Bug in contest lock timing — wallet deducted funds too early
- Scoring delay >5s triggered multiple refund flows
- ~₹1.2L refunded incorrectly to users
- Hotfix patched in prod; long-term fix requires queue-based locking
- Added audit logs for payout retries + manual overrides
