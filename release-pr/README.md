# release-pr

## Usage

Prepare a private key and add it to the repository secrets as `RELEASE_MAID_PRIVATE_KEY`. Then, add the following workflow to the repository.

```yaml
# release-pr.yml
name: Release Please

on:
  push:
    branches: [main]

permissions: {}

jobs:
  release-please:
    runs-on: ubuntu-latest
    steps:
      - name: Run Release PR
        uses: chawyehsu/actions/release-pr@main
        with:
          private-key: ${{ secrets.RELEASE_MAID_PRIVATE_KEY }}
```
