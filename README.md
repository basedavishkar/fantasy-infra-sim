# fantasy-infra-sim

Simulation of core backend infrastructure for a real-money fantasy sports app, developed and maintained between Jan 2024 and Jun 2025. This repo serves as internal documentation for the system’s architecture, service boundaries, and ops workflows. Code and configs are illustrative or redacted.

> This is not a runnable project — it’s a simulated reconstruction of the real infra used during consulting work for a fantasy sports client.

---

## 🧠 Overview

- **Services:** FastAPI microservices for Auth, Wallet, Scoring, Payments, KYC
- **Infra:** AWS ECS (Fargate), Terraform (stubs), GitHub Actions, Redis, S3
- **Data:** PostgreSQL (core), Redis (cache/pubsub), S3 (match snapshots)
- **Async:** Celery for scoring, payouts, webhook handling
- **Payments:** Razorpay (primary), Cashfree (fallback)
- **KYC:** PAN OCR, Aadhaar eSign, fallback to selfie + manual review

---

## 📁 Structure

| Folder            | Purpose                                                    |
|-------------------|------------------------------------------------------------|
| `docs/`           | Architecture diagrams, flows, system notes                 |
| `services/`       | Per-service readmes (auth, wallet, scoring, etc.)          |
| `infra/terraform/`| Infra planning stubs (networking, services, storage)       |
| `cron/`           | Notes on cron jobs (e.g., match ingestion)                 |
| `adr/`            | Architecture Decision Records (bootstrap + tradeoffs)      |
| `experiments/`    | Abandoned or in-progress ideas                             |
| `notes/`          | Raw notes from dev onboarding, edge cases, and flows       |
| `postmortem.md`   | War stories and incident reports (e.g., accidental refunds)|

---

## 🧪 Simulation Constraints

- ❌ No code, no deployable infra
- ✅ Service boundaries, flows, edge case notes
- 🔒 Some sections anonymized or redacted (NDA context)
- 🧾 All infra and service files were written during/after active work

---

## 🧭 Start Here

- [`docs/architecture.md`](docs/architecture.md) — System architecture sketch (mermaid)
- [`postmortem.md`](postmortem.md) — Incident writeups from production bugs
- [`docs/02_kyc_payments.md`](docs/02_kyc_payments.md) — KYC + Payments integration notes

---

## 🙋🏻‍♂️ Why This Exists

I worked as an infra/backend consultant on a real-money fantasy sports product between Jan 2024 and Jun 2025. The actual code is proprietary, but this repo simulates the infra, notes, and service thinking behind that work — cleaned up just enough for open-source.

