# ADR 0001: Infra Bootstrap Strategy

## Status
Accepted

## Context
We needed a basic starting point for spinning up backend infrastructure for a fantasy platform MVP.
The infra had to support:

- microservices with isolated scaling
- scheduled jobs (match ingestion, scoring)
- managed DB + blob storage
- fast redeploys and easy teardown for devs

## Decision
Use:

- AWS ECS Fargate for services
- RDS Postgres
- S3 for media & snapshots
- Terraform for infra-as-code
- GitHub Actions for deploys (triggered on push to main)

No Kubernetes for now — too heavy for v0.

## Consequences
- Easier for junior devs to onboard
- Can run entire stack with 2 services + 1 cron job
- May outgrow ECS if traffic spikes — revisit later
