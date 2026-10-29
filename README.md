# newstart-gitops

Desired state for the NewStart EKS platform, reconciled by **Argo CD** (pull-based GitOps).

| Folder | Purpose |
|---|---|
| `bootstrap/argocd` | Argo CD Helm values + root app (installed once by hand) |
| `clusters/<env>` | Argo CD Applications for each environment (app-of-apps) |
| `platform/` | Cluster add-on configuration (Karpenter NodePools, etc.) |
| `apps/newstart` | NewStart manifests: Kustomize `base` + `overlays/<env>` |

Rules: no secrets in this repo (External Secrets reads AWS Secrets Manager);
every change goes through a pull request; CI only bumps image tags.

Related repos: [newstart-app](https://github.com/mahamatmbodou33/newstart-app) ·
[newstart-infra](https://github.com/mahamatmbodou33/newstart-infra)
