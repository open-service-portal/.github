# Reusable Workflows

Centralized workflows that can be called from any repository in the Open Service Portal organization.

## build-crossplane-package.yaml

Standardized workflow for building and publishing Crossplane packages to GitHub Container Registry.

### Conventions

This workflow enforces the following conventions:

- **Package structure**: Must be in `configuration/` directory
- **Required files**: `configuration/crossplane.yaml` must exist
- **Build platforms**: Always `linux/amd64,linux/arm64`
- **Latest tag**: Automatically applied to stable releases (no `-` in version)
- **Version label**: Applied only to XRD (`configuration/xrd.yaml`)

### Required Package Structure

```
your-template/
├── configuration/
│   ├── crossplane.yaml
│   ├── xrd.yaml
│   └── composition.yaml
├── examples/
└── README.md
```

### Inputs

| Input | Type | Required | Default | Description |
|-------|------|----------|---------|-------------|
| `package-name` | string | ✅ | - | Package identifier (e.g., `template-dns-record`) |
| `version` | string | ✅ | - | Version tag (e.g., `v1.0.0`) |
| `registry` | string | ❌ | `ghcr.io` | Container registry URL |
| `organisation` | string | ✅ | - | Organization owning the package |

### Outputs

| Output | Description |
|--------|-------------|
| `package-path` | Full registry path (e.g., `ghcr.io/org/package`) |

### Usage Example

```yaml
name: Release

on:
  push:
    tags: ['v*']

jobs:
  build:
    uses: open-service-portal/github-org-settings/.github/workflows/build-crossplane-package.yaml@main
    with:
      package-name: ${{ github.event.repository.name }}
      version: ${{ github.ref_name }}
      organisation: ${{ github.repository_owner }}
    permissions:
      contents: read
      packages: write
    secrets: inherit
```

### Version Tagging Behavior

| Version | Published Tags | Description |
|---------|---------------|-------------|
| `v1.0.0` | `v1.0.0`, `latest` | Stable release |
| `v1.0.0-rc1` | `v1.0.0-rc1` | Pre-release (no latest) |
| `v2.3.4` | `v2.3.4`, `latest` | Updates latest to v2.3.4 |
| `v0.1.0-beta` | `v0.1.0-beta` | Beta (no latest) |

### What the Workflow Does

1. **Validates** package structure (configuration/ directory required)
2. **Labels** XRD with version (if xrd.yaml exists)
3. **Builds** multi-arch package (amd64 + arm64)
4. **Pushes** to registry with version tag
5. **Updates** latest tag (stable releases only)
6. **Reports** summary in GitHub Actions UI

### Troubleshooting

#### "configuration/crossplane.yaml not found"
Your package must follow the standard structure with files in the `configuration/` directory.

#### "Permission denied" pushing to registry
Ensure your job has `packages: write` permission:
```yaml
permissions:
  contents: read
  packages: write
```

#### "Unable to find reusable workflow"
The workflow must exist in the `main` branch of the github-org-settings repository.

### Migration from Flexible Structure

If your packages use root directory structure, migrate them:
```bash
# Create configuration directory
mkdir -p configuration

# Move package files
mv crossplane.yaml xrd.yaml composition.yaml configuration/

# Update any references in your files
git add -A
git commit -m "chore: migrate to standard package structure"
```