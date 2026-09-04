# VirtFoundry

**Kubernetes-native private cloud** — multi-tenant IaaS on [KubeVirt](https://kubevirt.io/) with a CloudStack-like API and UI.

Built for teams leaving **Proxmox** (or avoiding raw KubeVirt YAML) who already run Kubernetes.

## What you get

| Layer | Technology |
|-------|------------|
| **Control plane** | Go REST API + React UI |
| **Source of truth** | [`virtfoundry.io`](https://github.com/virtfoundry/operator) CRDs + [operator](https://github.com/virtfoundry/operator) |
| **Hypervisor** | KubeVirt |
| **Networking** | Multus, tenant VPCs, optional MetalLB VIPs |
| **GitOps** | Helm + Argo CD · CRD store (no MySQL) |

Homelab E2E suite covers VM lifecycle, volumes, snapshots, tenant IAM, and L4 load balancers on the CR store.

## Start here

| | |
|--|--|
| **Documentation** | https://virtfoundry.github.io/helm-charts/docs/ |
| **Prerequisites** | https://virtfoundry.github.io/helm-charts/docs/guide/prerequisites/ |
| **Quickstart (< 30 min)** | https://virtfoundry.github.io/helm-charts/docs/guide/quickstart/ |
| **Why VirtFoundry** | https://virtfoundry.github.io/helm-charts/docs/guide/why/ |
| **Adopters** | https://github.com/virtfoundry/core/blob/main/ADOPTERS.md |
| **CNCF readiness** | https://github.com/virtfoundry/core/blob/main/docs/CNCF-CHECKLIST.md |
| **Discussions** | https://github.com/virtfoundry/core/discussions |

Current release: **0.7.1** (pin both charts).

```bash
helm repo add virtfoundry https://virtfoundry.github.io/helm-charts
helm repo update

helm install virtfoundry-operator virtfoundry/virtfoundry-operator \
  --version 0.7.1 \
  -n virtfoundry-system --create-namespace

helm install virtfoundry virtfoundry/virtfoundry \
  --version 0.7.1 \
  -n virtfoundry-system \
  --set secrets.rootPassword='change-me' \
  --set secrets.jwtSecret='change-me'
```

## Repositories

| Repo | Role |
|------|------|
| [core](https://github.com/virtfoundry/core) | REST API, UI, kubernetes store client |
| [operator](https://github.com/virtfoundry/operator) | CRDs + controllers (Tenant, Instance, …) |
| [helm-charts](https://github.com/virtfoundry/helm-charts) | Helm charts + documentation site |
| [terraform-provider-virtfoundry](https://github.com/virtfoundry/terraform-provider-virtfoundry) | Terraform provider |

## Adopters

| Who | Type |
|-----|------|
| [Matheus Thurler](https://github.com/Matheus-Thurler) | Homelab / maintainer |
| [Weslei Paulo Pereira](https://github.com/wesleip) | Homelab / maintainer |
| [Rodrigo Gonçalves](https://github.com/RodrigoGoncalves-dev) | Homelab / maintainer |

[Add your homelab or PoC →](https://github.com/virtfoundry/core/blob/main/ADOPTERS.md)

## Maintainers

| Name | GitHub | Company | Role |
|------|--------|---------|------|
| Matheus Thurler | [@Matheus-Thurler](https://github.com/Matheus-Thurler) | CI&T | Lead — DevOps / SRE |
| Weslei Paulo Pereira | [@wesleip](https://github.com/wesleip) | CI&T | Maintainer — DevOps / SRE |
| Rodrigo Gonçalves | [@RodrigoGoncalves-dev](https://github.com/RodrigoGoncalves-dev) | SYS MANAGER INFORMATICA LTDA | Maintainer — full-stack |

Canonical: [MAINTAINERS.md](https://github.com/virtfoundry/core/blob/main/MAINTAINERS.md) · [GOVERNANCE](https://github.com/virtfoundry/core/blob/main/GOVERNANCE.md) · [CONTRIBUTING](https://github.com/virtfoundry/core/blob/main/CONTRIBUTING.md) · [SECURITY](https://github.com/virtfoundry/core/blob/main/SECURITY.md)

Apache 2.0 · [CNCF Code of Conduct](https://github.com/virtfoundry/core/blob/main/CODE_OF_CONDUCT.md)
