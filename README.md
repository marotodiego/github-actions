# GitHub Actions Repository

This repository contains reusable GitHub Actions workflows and composite actions designed to be used across our organization.

## Structure

### Composite Actions (`actions/`)

Actions are organized by topic for better maintainability:

- `actions/versioning/` - Version management and semantic versioning
- `actions/deployment/` - Deployment and release automation
- `actions/testing/` - Testing, linting, and code quality
- `actions/security/` - Security scanning and vulnerability checks
- `actions/docker/` - Docker build, push, and container operations
- `actions/notifications/` - Slack, email, and other notifications

### Reusable Workflows (`.github/workflows/`)

Complete workflow templates that can be called from other repositories.

## Usage

### Composite Actions

Reference composite actions from this repository in your workflow files:

```yaml
- uses: marotodiego/github-actions/actions/versioning/semver-bump@main
```

### Reusable Workflows (coming soon)

Call reusable workflows from your repository's workflow files:

```yaml
jobs:
  call-workflow:
    uses: marotodiego/github-actions/.github/workflows/workflow-name.yml@main
```

## Contributing

When adding new actions or workflows:

1. Follow existing naming conventions
2. Include proper documentation
3. Test thoroughly before merging
4. Use semantic versioning for releases

## Support

For questions or issues with these shared GitHub Actions, please create an issue in this repository.
