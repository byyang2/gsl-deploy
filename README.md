# gsl-deploy

Central reusable workflow for AKS deployments. It is the only workflow the shared managed identity
`uami-gsl-aks-deploy-dev` trusts (one federated credential, subject pinned to this file on `main`).

- App repos call `.github/workflows/deploy-to-aks.yml@main`; see any app repo's `deploy.yml`.
- Onboarding an app = run `Add-GslApp.ps1` + add its name to `ALLOWED_APPS` here (pull request).
- Anyone who can merge to `main` controls what every app deploys: protect it.
