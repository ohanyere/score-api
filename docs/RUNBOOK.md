# Runbook

## Service

- Name: `score-api`
- Team: `Commerce`
- Owner: `mooref068@gmail.com`
- Cost center: `commerce`

## First Checks

```bash
kubectl get rollout score-api -n score-api-dev
kubectl get pods -l app.kubernetes.io/name=score-api -n score-api-dev
kubectl logs -l app.kubernetes.io/name=score-api -n score-api-dev
```

## Health

```bash
curl https://score-api.dev.platform.ohanyere.internal/healthz
curl https://score-api.dev.platform.ohanyere.internal/readyz
curl https://score-api.dev.platform.ohanyere.internal/livez
```

## Rollback

```bash
kubectl argo rollouts undo score-api -n score-api-dev
```

Escalate to `Commerce` through `mooref068@gmail.com` if rollback does not restore service.
