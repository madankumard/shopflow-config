# shopflow-config

Per-environment settings for [ShopFlow](https://github.com/madankumard/shopflow), served to the
running apps by the Spring Cloud Config Server in each cluster.

| File | Applies to |
|---|---|
| `backend.yml` | The backend in every environment |
| `backend-dev.yml` | dev only |
| `backend-qa.yml` | QA only |
| `backend-preprod.yml` | pre-prod only |
| `backend-prod.yml` | prod only |

An environment file overrides the shared file.

## Rules

- **No secrets here.** This repository is public. Passwords and keys live in Vault.
- A pushed change is served immediately, but an app reads its settings only at start-up.
  To apply a change, restart the backend in that environment from the ShopFlow repo:
  `.\infra\reload-config.ps1 -Environment qa`