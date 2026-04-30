# yage-manifests

GitOps YAML templates for [yage](https://github.com/lpasquali/yage) — cluster manifests, Helm values, ArgoCD Applications, and PostSync hooks.

All templates use Go `text/template` syntax (`.yaml.tmpl` files). yage clones this repo at a pinned tag and renders templates in-process — no YAML generation inside the yage binary.

## Repository layout

```
yage-manifests/
├── cluster/      # CAPI workload cluster manifests, per provider
├── addons/       # Helm values + ArgoCD Application YAMLs, per add-on
├── csi/          # Per-driver Helm values (one directory per CSI driver)
└── postsync/     # ArgoCD PostSync hook manifests
```

## Usage

yage selects the pinned ref via `YAGE_MANIFESTS_REF` (default: latest stable tag). Templates receive a `*config.Config` struct as the template data — use `{{ .FieldName }}` to reference any config field.

To preview a rendered template locally:

```bash
# Using Go text/template directly — requires a config JSON fixture
go run github.com/lpasquali/yage/tools/render-template \
  --template cluster/proxmox/cluster.yaml.tmpl \
  --config my-config.json
```

## Versioning

Tagged with semver (`v0.1.0`, `v0.2.0`, …). Breaking template changes bump the minor version until v1.0.0. yage pins via `YAGE_MANIFESTS_REF`.

## Contributing

Each template must:
- Be valid YAML when rendered with any valid `config.Config`.
- Use only fields present in `config.Config` (no undocumented keys).
- Include a `# yage-manifests/<path>` header comment.
- Have a corresponding entry in the directory README.
