# create-release

## Usage

```yaml
# release.yml
name: Release

on:
  push:
    tags:
      - v*

permissions:
  contents: write

jobs:
  release:
    name: Create Release
    runs-on: ubuntu-latest
    steps:
      - name: Draft Release
        uses: chawyehsu/actions/create-release@main
```
