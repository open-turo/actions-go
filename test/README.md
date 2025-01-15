# GitHub Action Test

<!-- prettier-ignore-start -->
<!-- action-docs-description source="action.yaml" -->
## Description

GitHub Action that executes unit tests present anywhere within a golang based GitHub repository and reports results including coverage metrics
<!-- action-docs-description source="action.yaml" -->
## Description

GitHub Action that executes unit tests present anywhere within a golang based GitHub repository and reports results including coverage metrics
<!-- action-docs-description -->
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
<!-- action-docs-inputs source="action.yaml" -->
## Inputs

| name | description | required | default |
| --- | --- | --- | --- |
| `checkout-repo` | <p>Perform checkout as first step of action</p> | `false` | `true` |
| `github-token` | <p>GitHub token that can checkout the consumer repository. e.g. 'secrets.GITHUB_TOKEN'</p> | `true` | `""` |
| `coverage-file` | <p>File to write coverage report to (coverprofile option in go test)</p> | `false` | `covprofile` |
<!-- action-docs-inputs source="action.yaml" -->
## Inputs

| --- | --- | --- | --- |
| checkout-repo | Perform checkout as first step of action | `false` | true |
| github-token | GitHub token that can checkout the consumer repository. e.g. 'secrets.GITHUB_TOKEN' | `true` |  |
<!-- action-docs-inputs -->

<!-- action-docs-outputs source="action.yaml" -->

<!-- action-docs-outputs source="action.yaml" -->

<!-- action-docs-outputs -->

<!-- action-docs-runs source="action.yaml" -->
## Runs

This action is a `composite` action.
<!-- action-docs-runs source="action.yaml" -->
## Runs

This action is a `composite` action.
<!-- action-docs-runs -->

<!-- action-docs-usage source="action.yaml" -->
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
    # GitHub token that can checkout the consumer repository. e.g. 'secrets.GITHUB_TOKEN'
    #
    # Required: true
    # Default: ""

    coverage-file:
    # File to write coverage report to (coverprofile option in go test)
    #
    # Required: false
    # Default: covprofile
```
<!-- action-docs-usage source="action.yaml" -->
<!-- action-docs-usage -->
<!-- prettier-ignore-end -->
