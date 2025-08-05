# `open-turo/action-pre-commit`

<!-- prettier-ignore-start -->
<!-- action-docs-description -->
## Description

GitHub Action for running pre-commit hooks against the repository. Conditionally installs tools needed for the Action to be able to perform its duties such as `npm`, `pre-commit`, etc.
<!-- action-docs-description -->
<!-- prettier-ignore-end -->

[![Release](https://img.shields.io/github/v/release/open-turo/action-pre-commit)](https://github.com/open-turo/action-pre-commit/releases/)
[![Tests pass/fail](https://img.shields.io/github/workflow/status/open-turo/action-pre-commit/CI)](https://github.com/open-turo/action-pre-commit/actions/)
[![License](https://img.shields.io/github/license/open-turo/action-pre-commit)](./LICENSE)
[![Contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg)](https://github.com/dwyl/esta/issues)
![CI](https://github.com/open-turo/action-pre-commit/actions/workflows/release.yaml/badge.svg)
[![semantic-release: angular](https://img.shields.io/badge/semantic--release-angular-e10079?logo=semantic-release)](https://github.com/semantic-release/semantic-release)
[![Conventional commits](https://img.shields.io/badge/conventional%20commits-1.0.2-%23FE5196?logo=conventionalcommits&logoColor=white)](https://conventionalcommits.org)
[![Join us!](https://img.shields.io/badge/Turo-Join%20us%21-593CFB.svg)](https://turo.com/jobs)

## Usage

Basic usage with default options:

```yaml
jobs:
  lint:
    steps:
      - uses: actions/checkout@v3
        with:
          fetch-depth: 0
      - uses: open-turo/action-pre-commit@v2
```

Overriding defaults:

```yaml
jobs:
  lint:
    steps:
      - uses: actions/checkout@v3
        with:
          fetch-depth: 0
      - uses: open-turo/action-pre-commit@v2
        with:
          # Override the config file used by default
          config-file: .commitlintrc.yaml
          # Don't include `@turo/conventional-commit` configuration
          turo-conventional-commit: false
          # Only run pre-commit against changed files, instead of all files
          only-changed: true
```

<!-- prettier-ignore-start -->
<!-- action-docs-inputs -->
## Inputs

| parameter | description | required | default |
| --- | --- | --- | --- |
| config-file | The config file to present to commitlint-github-action | `true` | .commitlintrc.yaml |
| turo-conventional-commit | Set this to "false" to customize conventional commit configuration | `true` | true |
| only-changed | Set this to "true" to only run pre-commit against changed files, and not the entire repository | `false` |  |
| s3-bucket-name | S3 bucket name to cache node_modules to speed up dependency installation. | `false` |  |
| s3-bucket-region | S3 bucket region to cache node_modules to speed up dependency installation. | `false` |  |
| github-token | Sets a GitHub token that allows pre-commit to fetch private repos | `false` |  |
<!-- action-docs-inputs -->

<!-- action-docs-outputs -->
## Outputs

| parameter | description |
| --- | --- |
| cache-hit | Whether the cache was hit when installing dependencies |
<!-- action-docs-outputs -->

<!-- action-docs-runs -->
## Runs

This action is a `composite` action.
<!-- action-docs-runs -->
<!-- prettier-ignore-end -->

## Get Help

Please review Issues, post new Issues against this repository as needed.

## Contributions

Please see [here](https://github.com/open-turo/contributions) for guidelines on how to contribute to this project.
