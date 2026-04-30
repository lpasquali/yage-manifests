# addons/

Helm values overrides and ArgoCD Application manifests for each platform add-on yage installs on the workload cluster.

Each subdirectory contains:
- `values.yaml.tmpl` — Helm values rendered from `config.Config`
- `application.yaml.tmpl` — ArgoCD Application resource (where applicable)

Migrated from `internal/capi/helmvalues/`, `internal/capi/wlargocd/render.go`, and `internal/capi/caaph/`.

## Add-ons

| Directory | Add-on |
|---|---|
| `cilium/` | Cilium CNI (LB-IPAM, kube-proxy replacement, Hubble) |
| `argocd/` | ArgoCD Operator + ArgoCD CR |
| `argocd-apps/` | CAAPH HelmChartProxy for argocd-apps |
| `metrics-server/` | Kubernetes metrics-server |
| `observability/` | VictoriaMetrics + Grafana stack |
| `cert-manager/` | cert-manager + ClusterIssuer |
| `kyverno/` | Kyverno policy engine |
| `crossplane/` | Crossplane |
| `cloudnativepg/` | CloudNativePG operator |
| `external-secrets/` | External Secrets Operator |
| `infisical/` | Infisical secrets manager |
| `spire/` | SPIRE SPIFFE identity |
| `opentelemetry/` | OpenTelemetry Collector |
| `keycloak/` | Keycloak identity provider |
