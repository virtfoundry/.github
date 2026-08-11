# VirtFoundry

**Kubernetes-native private cloud** — multi-tenant IaaS on [KubeVirt](https://kubevirt.io/).

Tenants, VPCs, VMs, volumes, snapshots, IAM, and a web UI. Built for people leaving **Proxmox** (or avoiding raw KubeVirt YAML) who already run Kubernetes.

## Start here

| | |
|--|--|
| **Docs (front door)** | https://virtfoundry.github.io/helm-charts/docs/ |
| **Quickstart (< 30 min)** | https://virtfoundry.github.io/helm-charts/docs/guide/quickstart/ |
| **Why VirtFoundry** | https://github.com/virtfoundry/core/blob/main/docs/WHY.md |
| **Discussions** | https://github.com/virtfoundry/core/discussions |
| **Traction board** | https://github.com/orgs/virtfoundry/projects/1 |

```bash
helm repo add virtfoundry https://virtfoundry.github.io/helm-charts
helm install virtfoundry virtfoundry/virtfoundry \
  -n virtfoundry-system --create-namespace \
  --set secrets.rootPassword='change-me' \
  --set secrets.jwtSecret='change-me'
```

## Repositories

| Repo | Role |
|------|------|
| [core](https://github.com/virtfoundry/core) | API, worker, UI |
| [helm-charts](https://github.com/virtfoundry/helm-charts) | Helm chart + documentation site |
| [terraform-provider-virtfoundry](https://github.com/virtfoundry/terraform-provider-virtfoundry) | Terraform provider |

Apache 2.0 · Maintained by the VirtFoundry org
