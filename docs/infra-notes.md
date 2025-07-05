# Infra Notes (messy)

- Used ECS Fargate — didn't want to fight k8s for v0
- Terraform used but not cleanly modular
- Secrets stored in SSM Param Store, rotated manually (yes, bad)
- No staging — deployed straight to prod via GitHub Actions
- Redis used for queue/pubsub, but no real observability

