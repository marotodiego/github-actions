# Semver Bump Action

A composite action that calculates the next semantic version based on commit message prefixes following conventional commits.

## Usage

```yaml
- name: Calculate next version
  id: version
  uses: marotodiego/github-actions/actions/versioning/semver-bump@main
  with:
    current-version: "1.2.3" # Optional, defaults to latest git tag
    default-bump: "patch" # Optional, defaults to 'patch'

- name: Use the version
  run: echo "Next version will be ${{ steps.version.outputs.version }}"
```

## Inputs

| Input             | Description                                            | Required | Default                   |
| ----------------- | ------------------------------------------------------ | -------- | ------------------------- |
| `current-version` | Current version (if not provided, gets latest git tag) | No       | Latest git tag or `0.0.0` |
| `default-bump`    | Default bump type when no prefix matches               | No       | `patch`                   |

## Outputs

| Output      | Description                                    |
| ----------- | ---------------------------------------------- |
| `version`   | The new semantic version                       |
| `bump-type` | The type of bump applied (patch, minor, major) |

## Commit Message Prefixes

The action recognizes these conventional commit prefixes:

- **Major bump**: `feat!:`, `feature!:`, `BREAKING CHANGE`, or any commit with `!` after type
- **Minor bump**: `feat:`, `feature:`
- **Patch bump**: `fix:`, `bugfix:`, `patch:`, `docs:`, `chore:`, `style:`, `refactor:`, `perf:`, `test:`

## Examples

| Commit Message           | Current Version | Next Version | Bump Type |
| ------------------------ | --------------- | ------------ | --------- |
| `feat: add new feature`  | `1.2.3`         | `1.3.0`      | `minor`   |
| `fix: resolve bug`       | `1.2.3`         | `1.2.4`      | `patch`   |
| `feat!: breaking change` | `1.2.3`         | `2.0.0`      | `major`   |
| `chore: update deps`     | `1.2.3`         | `1.2.4`      | `patch`   |
