# Auto Label

Reusable GitHub Action for auto-labeling pull requests and issues based on commits, files, and changes.

## Usage

```yaml
name: Auto Label

on:
  pull_request:
    types: [opened, synchronize, reopened]
  issues:
    types: [opened]

jobs:
  label:
    runs-on: ubuntu-latest
    permissions:
      pull-requests: write
      issues: write
    steps:
      - uses: libnudget/auto-label@v1
```

## What it does

**For PRs:**
- **Bump labels**: `major` (BREAKING CHANGE), `minor` (feat), `patch` (fix)
- **Area labels**: `ci` (.github changes), `docs` (docs changes), `test` (test changes)
- **Size labels**: `size/s` (<50 lines), `size/m` (<200), `size/l` (<500), `size/xl` (500+)

**For Issues:**
- **Type labels**: `bug`, `enhancement`, `security`, `docs`, `test` based on title and body content
- **Emoji reactions**: 🎉 (enhancement), 👀 (security), 😕 (question) based on title and body content

## Requirements

- Repository must have labels: `major`, `minor`, `patch`, `ci`, `docs`, `test`, `size/s`, `size/m`, `size/l`, `size/xl`, `bug`, `enhancement`, `security`
