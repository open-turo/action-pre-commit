# `open-turo/action-pre-commit`

GitHub Action for running pre-commit hooks against the consumer repository. Conditionally installs tools needed for the Action to be able to perform its duties such as `npm`, `pre-commit`, etc.

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
      - uses: open-turo/action-pre-commit@v1
```

Overriding defaults:

```yaml
jobs:
  lint:
    steps:
      - uses: actions/checkout@v3
        with:
          fetch-depth: 0
      - uses: open-turo/action-pre-commit@v1
        with:
          # Override the config file used by default
          config-file: .commitlintrc.yaml
          # Don't include `@turo/conventional-commit` configuration
          turo-conventional-commit: false
          # Only run pre-commit against changed files, instead of all files
          only-changed: true
```

## Inputs

| parameter                | description                                                                                    | required | default            |
| ------------------------ | ---------------------------------------------------------------------------------------------- | -------- | ------------------ |
| config-file              | The config file to present to commitlint-github-action                                         | `true`   | .commitlintrc.yaml |
| turo-conventional-commit | Set this to "false" to customize conventional commit configuration                             | `true`   | true               |
| only-changed             | Set this to "true" to only run pre-commit against changed files, and not the entire repository | `false`  |                    |

## Runs

This action is an `composite` action.

## Get Help

Please review Issues, post new Issues against this repository as needed.

## Contributions

Please see [here](https://github.com/open-turo/contributions) for guidelines on how to contribute to this project.
