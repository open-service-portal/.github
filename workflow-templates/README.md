# Workflow Templates

GitHub workflow templates that appear in the "New workflow" interface for all repositories in the Open Service Portal organization.

## Available Templates

### 1. Crossplane Package Release (`crossplane-package-release.yml`)

Complete workflow for releasing Crossplane packages with automated catalog updates.

**What it does:**
1. Gathers environment information (registry, org, package name, version)
2. Builds and pushes package using the reusable build workflow
3. Updates catalog via pull request (tag pushes only)
4. Creates GitHub release with installation instructions

**When to use:**
- You have a Crossplane template repository
- You want automated releases on tag push
- You need catalog integration

**Key Features:**
- Manual testing via `workflow_dispatch`
- Automatic pre-release detection
- Catalog PR linking in release notes
- Multi-architecture builds

**Usage:**
1. Go to Actions → New workflow
2. Select "Crossplane Package Release"
3. No customization needed - uses repository name and owner automatically

### 2. Sync Organization Labels (`sync-labels.yml`)

Synchronizes repository labels with organization standards.

**What it does:**
- Pulls label configuration from organization's `.github` repository
- Updates repository labels to match organization standards
- Runs weekly or on-demand
- Preserves repository-specific labels

**When to use:**
- You want consistent labels across repositories
- You need to align with organization standards
- You're setting up a new repository

**Schedule:**
- Weekly: Sundays at midnight
- Manual: Via workflow dispatch
- On change: When workflow file is modified

**Configuration:**
- Labels defined in: `open-service-portal/.github` repository
- Non-destructive: Won't delete repository-specific labels

## Template Properties Files

Each workflow template has a corresponding `.properties.json` file that controls:
- **name**: Display name in GitHub UI
- **description**: Help text for users
- **iconName**: Visual icon (e.g., "package", "sync")
- **categories**: Grouping in the template selector
- **filePatterns**: When to suggest this template

## How Templates Work

1. **Discovery**: GitHub scans the `workflow-templates/` directory
2. **Display**: Templates appear in "New workflow" for all org repositories  
3. **Adoption**: Users select and commit the workflow
4. **Customization**: Workflows auto-adapt using repository context

## Adding New Templates

1. Create `workflow-name.yml` in this directory
2. Create `workflow-name.properties.json` with metadata
3. Use repository context variables for auto-configuration:
   - `${{ github.repository_owner }}` - Organization name
   - `${{ github.event.repository.name }}` - Repository name
   - `${{ github.ref_name }}` - Tag/branch name

## Best Practices

1. **Self-configuring**: Use context variables instead of hardcoded values
2. **Documentation**: Include comments explaining each section
3. **Flexibility**: Support both automated and manual triggers
4. **Minimal configuration**: Work out-of-the-box without changes