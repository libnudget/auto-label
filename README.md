# Auto Label PRs

Reusable GitHub Action for auto-labeling pull requests based on commits, files, and changes.

## Usage

```yaml
name: Auto Label PRs

on:
  pull_request:
    types: [opened, synchronize, reopened]

jobs:
  label:
    runs-on: ubuntu-latest
    permissions:
      pull-requests: write
    steps:
      - uses: libnudget/auto-label@v1
```

## What it does

- **Bump labels**: `major` (BREAKING CHANGE), `minor` (feat), `patch` (fix)
- **Area labels**: `ci` (.github changes), `docs` (docs changes), `test` (test changes)
- **Size labels**: `size/s` (<50 lines), `size/m` (<200), `size/l` (<500), `size/xl` (500+)

## Requirements

- Repository must have labels: `major`, `minor`, `patch`, `ci`, `docs`, `test`, `size/s`, `size/m`, `size/l`, `size/xl`
