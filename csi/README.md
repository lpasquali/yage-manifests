# csi/

Helm values templates for each CSI driver registered in yage's CSI driver registry.

Each subdirectory contains:
- `values.yaml.tmpl` — Helm values rendered from `config.Config`, replacing each driver's `RenderValues()` Go method

Migrated from `internal/csi/*/RenderValues()` across all 14 driver packages.

## Drivers

| Directory | Driver | Default for |
|---|---|---|
| `proxmox-csi/` | Proxmox CSI Plugin | proxmox |
| `aws-ebs/` | AWS EBS CSI Driver | aws |
| `azure-disk/` | Azure Disk CSI Driver | azure |
| `gcp-pd/` | GCP Persistent Disk CSI | gcp |
| `hcloud/` | Hetzner Cloud Volumes CSI | hetzner |
| `do-block-storage/` | DigitalOcean Block Storage | digitalocean |
| `oci-block-storage/` | OCI Block Volume CSI | oci |
| `linode-block-storage/` | Linode Block Storage CSI | linode |
| `openstack-cinder/` | OpenStack Cinder CSI | openstack |
| `vsphere-csi/` | vSphere CSI Driver | vsphere |
| `ibm-vpc-block/` | IBM VPC Block CSI | ibmcloud |
| `longhorn/` | Longhorn | opt-in |
| `rook-ceph/` | Rook-Ceph | opt-in |
| `openebs/` | OpenEBS (hostpath) | opt-in |
