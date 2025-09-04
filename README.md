# GitHub Organization Settings

This repository contains centralized configuration, workflows, and templates for the Open Service Portal GitHub organization.

## Repository Structure

```
github-org-settings/
├── .github/
│   └── workflows/                              # Reusable workflows
│       └── build-crossplane-package.yaml       # Crossplane package builder
├── workflow-templates/                         # GitHub workflow templates
│   ├── crossplane-package-release.yml          # Complete release workflow
│   └── sync-labels.yml                         # Organization label sync
├── images/                                     # Organization branding
└── profile/                                    # Organization profile
    └── README.md
```

## Components

### Reusable Workflows (`.github/workflows/`)
Centralized workflows that can be called from any repository in the organization. These provide standardized processes for common tasks like building Crossplane packages.

[View Documentation](.github/workflows/README.md)

### Workflow Templates (`workflow-templates/`)
Ready-to-use workflow templates that appear in GitHub's "New workflow" interface. Teams can quickly adopt these standardized workflows without writing them from scratch.

[View Documentation](workflow-templates/README.md)

### Organization Profile (`profile/`)
The public-facing README that appears on the organization's GitHub profile page.

## Contributing

When adding new workflows or templates:
1. Place reusable workflows in `.github/workflows/`
2. Place templates in `workflow-templates/` with a `.properties.json` file
3. Update the relevant README.md with documentation
4. Test thoroughly before merging to main