# GitHub Action Release

<!-- prettier-ignore-start -->
<!-- action-docs-description -->
## Description

GitHub Action that produces a new pre-release (snapshot) of a golang based repository.
<!-- action-docs-description -->
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
<!-- action-docs-inputs -->
## Inputs

| parameter | description | required | default |
| --- | --- | --- | --- |
| checkout-repo | Perform checkout as first step of action | `false` | true |
| github-token | GitHub token that can checkout the consumer repository as well as create tags/releases against it. e.g. 'secrets.GITHUB_TOKEN' | `true` |  |
| go-version | Go version to use for building | `true` | 1.17.3 |
<!-- action-docs-inputs -->

<!-- action-docs-outputs -->
## Outputs

| parameter | description |
| --- | --- |
| version | Version of the project |
<!-- action-docs-outputs -->

<!-- action-docs-runs -->
## Runs

This action is a `composite` action.
<!-- action-docs-runs -->

<!-- action-docs-usage  -->
<!-- action-docs-usage -->
<!-- prettier-ignore-end -->
