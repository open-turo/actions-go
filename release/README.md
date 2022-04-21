# GitHub Action Release

## Description

GitHub Action that produces a new Release of a golang based repository.

## Configuration

### Step1: Set any [Semantic Release Configuration](https://github.com/semantic-release/semantic-release/blob/master/docs/usage/configuration.md#configuration) in the consumer repository.

### Step2: [Add Secrets](https://help.github.com/en/actions/configuring-and-managing-workflows/creating-and-storing-encrypted-secrets) in the consumer repository for the [Semantic Release Authentication](https://github.com/semantic-release/semantic-release/blob/master/docs/usage/ci-configuration.md#authentication) Environment Variables.

### Step3: Add a [Workflow File](https://help.github.com/en/articles/workflow-syntax-for-github-actions) to the consumer repository to create custom automated processes.

## Usage

```yaml
steps:
  - name: Release
    uses: open-turo/actions-go/release@v1
    with:
      ## example value for github-token provided below
      github-token: ${{ secrets.GITHUB_TOKEN }}
```

**IMPORTANT**: `GITHUB_TOKEN` does not have the required permissions to operate on protected branches.
If you are using this action for protected branches, replace `GITHUB_TOKEN` with [Personal Access Token](https://help.github.com/en/github/authenticating-to-github/creating-a-personal-access-token-for-the-command-line). If using the `@semantic-release/git` plugin for protected branches, avoid persisting credentials as part of `actions/checkout@v3` by setting the parameter `persist-credentials: false`. This credential does not have the required permission to operate on protected branches.

## Inputs

| parameter     | description                                                                                                                    | required | default |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------ | -------- | ------- |
| checkout-repo | Perform checkout as first step of action                                                                                       | `false`  | true    |
| github-token  | GitHub token that can checkout the consumer repository as well as create tags/releases against it. e.g. 'secrets.GITHUB_TOKEN' | `true`   |         |
| go-version    | Go version to use for building                                                                                                 | `true`   | 1.17.3  |

## Outputs

| parameter | description            |
| --------- | ---------------------- |
| version   | Version of the project |

## Runs

This action is an `composite` action.

## Additional Examples

### using output parameters example

```yaml
jobs:
  build:
    steps:
      - name: Release
        uses: open-turo/actions-go/release@v1
        id: release # Need an `id` for output variables
        with:
          github-token: ${{ secrets.GITHUB_TOKEN }}
      - name: Do something when a new release published
        if: steps.release.outputs.new-release-published == 'true'
        run: |
          echo ${{ steps.semantic.outputs.new-release-version }}
          echo ${{ steps.semantic.outputs.new-release-major-version }}
```

## Notes

- By default, this action will perform actions/checkout as its first step.
