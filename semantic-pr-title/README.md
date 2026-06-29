# semantic-pr-title

Validate that pull request titles follow the [Conventional Commits](https://www.conventionalcommits.org/) specification.

## Usage

```yaml
name: Lint Pull Request

on:
  pull_request:
    types: [opened, edited, synchronize]

permissions:
  pull-requests: read

jobs:
  pr-title:
    name: Validate PR Title
    runs-on: ubuntu-latest
    steps:
      - name: Check PR Title
        uses: chawyehsu/actions/semantic-pr-title@main
```

## Inputs

| Input | Required | Default | Description |
| --- | --- | --- | --- |
| `types` | No | `feat,fix,docs,style,refactor,perf,test,build,ci,chore,revert` | Allowed commit types (comma separated) |

## Examples

### Custom types

```yaml
- name: Check PR Title
  uses: chawyehsu/actions/semantic-pr-title@main
  with:
    types: "feat,fix,docs,chore"
```

## Valid title formats

```plain
feat: add new feature
fix(api): resolve timeout issue
docs: update README
feat!: breaking change
fix(auth)!: remove deprecated login endpoint
```
