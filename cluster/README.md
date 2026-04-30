# cluster/

CAPI workload cluster manifests, one subdirectory per infrastructure provider.

Each subdirectory contains:
- `cluster.yaml.tmpl` — full multi-document YAML for the workload cluster (Cluster, InfraCluster, KubeadmControlPlane, MachineDeployment, etc.)
- `k3s.yaml.tmpl` — K3s variant where applicable

Migrated from `internal/capi/manifest/generate.go` and `internal/capi/manifest/k3s.go`.

## Providers

| Directory | Provider |
|---|---|
| `proxmox/` | Proxmox VE (CAPMOX) |
| `aws/` | AWS (CAPA) |
| `azure/` | Azure (CAPZ) |
| `gcp/` | GCP (CAPG) |
| `hetzner/` | Hetzner Cloud (CAPHV) |
| `openstack/` | OpenStack (CAPO) |
| `vsphere/` | vSphere (CAPV) |
| `digitalocean/` | DigitalOcean (CAPDO) |
| `linode/` | Linode (CAPL) |
| `oci/` | OCI (CAPOCI) |
| `ibmcloud/` | IBM Cloud (CAPIBM) |
| `capd/` | Docker/CAPD (local dev) |
