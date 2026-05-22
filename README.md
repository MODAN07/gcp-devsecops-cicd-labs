# GCP DevSecOps & CI/CD Engineering Labs ⚙️

> Hands-on labs covering Docker hardening, GKE Kubernetes deployments, Cloud Run, Terraform IaC, GitHub Actions automation, and cloud security hardening on Google Cloud Platform.

![GCP](https://img.shields.io/badge/Cloud-GCP-4285F4?style=flat&logo=googlecloud)
![GKE](https://img.shields.io/badge/Kubernetes-GKE-326CE5?style=flat&logo=kubernetes)
![Terraform](https://img.shields.io/badge/IaC-Terraform-7B42BC?style=flat&logo=terraform)
![GitHub Actions](https://img.shields.io/badge/CI/CD-GitHub_Actions-2088FF?style=flat&logo=githubactions)

---

## 🧪 Lab Modules

### Lab 1 — Docker Containerisation
- Hardened images: non-root user, distroless base, multi-stage builds
- Pushed to Artifact Registry with vulnerability scanning enabled
- Deployed to Cloud Run and GCE

### Lab 2 — GKE Security
- Autopilot cluster via Terraform
- RBAC — namespace-scoped service accounts
- Network Policies — deny-all default, explicit allow
- Workload Identity for pod-level GCP auth
- Resource requests/limits on all pods

### Lab 3 — Cloud Run
- IAM — no unauthenticated access
- Workload Identity for downstream GCP services
- Traffic splitting for zero-downtime deploys
- VPC connector for private Cloud SQL access

### Lab 4 — Terraform IaC
- Full GCP environment via modular Terraform
- Remote state: Cloud Storage with versioning + locking
- Checkov IaC scanning in CI pipeline

### Lab 5 — GitHub Actions CI/CD
- OIDC authentication — no service account keys stored
- Stages: lint → test → build → push → deploy
- Checkov gates deployment on policy violations
- Auto-rollback on failed health checks post-deploy

```yaml
- name: Authenticate to GCP via OIDC
  uses: google-github-actions/auth@v2
  with:
    workload_identity_provider: ${{ secrets.WIF_PROVIDER }}
    service_account: ${{ secrets.SA_EMAIL }}
    # No keys. No secrets. Pure OIDC token exchange.
```

### Lab 6 — Security Hardening
- Org Policy constraints (disable serial port, require OS Login, restrict public IPs)
- Security Command Center findings remediation
- VPC Service Controls perimeter
- Binary Authorization — signed images only in GKE

---

## 👤 Author

**Moses Gnamisan Daniel** — Cloud Security & DevSecOps Engineer

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin)](https://www.linkedin.com/in/moses-daniel-a8a80861/)
