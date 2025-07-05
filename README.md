# fantasy-infra-sim

Simulated backend infra and service notes for a real-money fantasy sports app (Jan 2024 – June 2025). This repo documents the architecture, service boundaries, and ops patterns used in production, but all code and configs here are sanitized or illustrative only.

## System Overview

- **API & Services:** FastAPI microservices (auth, wallet, scoring, payments)
- **Infra:** AWS ECS Fargate for container orchestration, Terraform for IaC
- **Data:** PostgreSQL (RDS) for core data, S3 for snapshots, Redis for cache/pubsub
- **Async:** Celery for background jobs (scoring, payouts)
- **Payments:** Razorpay (primary), Cashfree (fallback)
- **KYC:** PAN/Aadhaar checks, manual review fallback
- **Ops:** GitHub Actions for deploys, basic cron for scheduled jobs

## Folder Structure

- `docs/` — Architecture diagrams, flow notes, service/integration docs
- `services/` — Service-level notes for auth, wallet, scoring, payments
- `infra/` — Terraform stubs and infra planning
- `adr/` — Architecture decision records (ADRs)
- `cron/` — Notes on scheduled jobs and cron logic
- `experiments/` — Abandoned or experimental refactors
- `notes/` — Miscellaneous design and onboarding thoughts
- `postmortem.md` — Incident writeups and lessons learned

## Limitations

- No runnable code or deployable infra — this is documentation and architecture only
- Not production-ready, not a template — for reference and internal knowledge sharing
- Some details are redacted or simulated for NDA reasons

## References

- [System Architecture](docs/architecture.md)
- [Postmortem: 1.2L Refund Incident](postmortem.md)

---
