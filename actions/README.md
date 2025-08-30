# Composite Actions

This directory contains composite actions organized by topic.

## Available Actions

### Versioning (`versioning/`)

- **semver-bump** - Calculate next semantic version based on commit message prefixes

### Deployment (`deployment/`)

_Coming soon_

### Testing (`testing/`)

_Coming soon_

### Security (`security/`)

_Coming soon_

### Docker (`docker/`)

_Coming soon_

### Notifications (`notifications/`)

_Coming soon_

## Usage

Reference actions using the full path:

```yaml
- uses: marotodiego/github-actions/actions/category/action-name@main
```

For example:

```yaml
- uses: marotodiego/github-actions/actions/versioning/semver-bump@main
```
