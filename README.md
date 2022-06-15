# GitHub Actions - Auto-release on tag

Create a new release any time a new semver-compatible tag is pushed to a repository.

If there is already a release for that tag (for example if a release was created manually through the Github UI) a new release is _not_ created.

## Usage

This action has no configuration or inputs - just add the following workflow verbatim.

**.github/workflows/auto-release-on-tag.yml**
```yml
on:
  push:
    tags:
      - '*.*.*'
jobs:
  auto-tag:
    name: Auto-release-on-tag
    runs-on: ubuntu-latest
    steps:
      - name: Auto-release-on-tag
        uses: silverstripe/gha-auto-release-on-tag@main
```
