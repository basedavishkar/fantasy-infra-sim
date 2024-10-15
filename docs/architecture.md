# System Architecture Overview

This backend infra simulated the real-money fantasy app I consulted for.

## Diagram

Mermaid diagram for infra components:

\`\`\`mermaid
graph TD
  subgraph User
    A[User] --> B[Frontend App]
  end

  B --> C[API Gateway]
  C --> D[Auth Service]
  C --> E[KYC & Onboarding]
  C --> F[Wallet Service]
  C --> G[Match Ingestion]
  C --> H[Scoring Service]
  C --> I[Payment Handler]

  F --> J[(PostgreSQL)]
  G --> K[(S3)]
  H --> J
  I --> L[(Cashfree, Razorpay)]
\`\`\`

## Notes

- All services were containerized (ECS)
- Event-driven parts used Redis pub/sub
- Scoring relied on post-match CSVs → ingested via signed S3 uploads
- Payouts used async task queues (via Celery back then)
