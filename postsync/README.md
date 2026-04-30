# postsync/

ArgoCD PostSync hook manifests and smoke-test Jobs rendered after workload cluster sync completes.

Each file is a `.yaml.tmpl` template rendered from `config.Config`.

Migrated from `internal/capi/postsync/postsync.go`.

## Contents

| File | Purpose |
|---|---|
| `proxmox-csi-smoke.yaml.tmpl` | Proxmox CSI smoke-test PVC + Pod |
| `argocd-redis-secret.yaml.tmpl` | ArgoCD Redis Secret post-install hook |
