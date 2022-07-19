# `open-turo/action-pre-commit`

GitHub Action for running pre-commit hooks against the consumer repository. Conditionally installs tools needed for the Action to be able to perform its duties such as `npm`, `pre-commit`, etc.

## Usage

```yaml
jobs:
  lint:
    steps:
      - uses: actions/checkout@v3
        with:
          fetch-depth: 0
      - uses: open-turo/action-pre-commit@v1
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
