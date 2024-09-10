# GitHub Action Release

<!-- prettier-ignore-start -->
<!-- action-docs-description source="release/action.yaml" -->
## Description

GitHub Action that produces a new Release of a golang based repository.
<!-- action-docs-description source="release/action.yaml" -->
## Description

GitHub Action that produces a new Release of a golang based repository.
<!-- action-docs-description -->
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
<!-- action-docs-inputs source="release/action.yaml" -->
## Inputs

| name | description | required | default |
| --- | --- | --- | --- |
| `checkout-repo` | <p>Perform checkout as first step of action</p> | `false` | `true` |
| `github-token` | <p>GitHub token that can checkout the consumer repository as well as create tags/releases against it. e.g. 'secrets.GITHUB_TOKEN'</p> | `true` | `""` |
| `go-version` | <p>Go version to use for building</p> | `true` | `1.17.3` |
<!-- action-docs-inputs source="release/action.yaml" -->
## Inputs

| parameter | description | required | default |
| --- | --- | --- | --- |
| checkout-repo | Perform checkout as first step of action | `false` | true |
| github-token | GitHub token that can checkout the consumer repository as well as create tags/releases against it. e.g. 'secrets.GITHUB_TOKEN' | `true` |  |
| go-version | Go version to use for building | `true` | 1.17.3 |
<!-- action-docs-inputs -->

<!-- action-docs-outputs source="release/action.yaml" -->
## Outputs

| name | description |
| --- | --- |
| `version` | <p>Version of the project</p> |
<!-- action-docs-outputs source="release/action.yaml" -->
## Outputs

| parameter | description |
| --- | --- |
| version | Version of the project |
<!-- action-docs-outputs -->

<!-- action-docs-runs source="release/action.yaml" -->
## Runs

This action is a `composite` action.
<!-- action-docs-runs source="release/action.yaml" -->
## Runs

This action is a `composite` action.
<!-- action-docs-runs -->

<!-- action-docs-usage source="release/action.yaml" -->
## Usage

```yaml
- uses: @
  with:
    checkout-repo:
    # Perform checkout as first step of action
    #
    # Required: false
    # Default: true

    github-token:
    # GitHub token that can checkout the consumer repository as well as create tags/releases against it. e.g. 'secrets.GITHUB_TOKEN'
    #
    # Required: true
    # Default: ""

    go-version:
    # Go version to use for building
    #
    # Required: true
    # Default: 1.17.3
```
<!-- action-docs-usage source="release/action.yaml" -->
<!-- action-docs-usage -->
<!-- prettier-ignore-end -->
