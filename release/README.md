# GitHub Action Release

<!-- prettier-ignore-start -->
<!-- action-docs-description source="action.yaml" -->
## Description

GitHub Action that produces a new Release of a golang based repository.
<!-- action-docs-description source="action.yaml" -->
## Description

GitHub Action that produces a new Release of a golang based repository.
<!-- action-docs-description -->
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
<!-- action-docs-inputs source="action.yaml" -->
## Inputs

| name | description | required | default |
| --- | --- | --- | --- |
| `checkout-repo` | <p>Perform checkout as first step of action</p> | `false` | `true` |
| `checkout-fetch-depth` | <p>The number of commits to fetch. 0 indicates all history for all branches and tags</p> | `false` | `0` |
| `github-token` | <p>GitHub token that can checkout the consumer repository as well as create tags/releases against it. e.g. 'secrets.GITHUB_TOKEN'</p> | `true` | `""` |
| `dry-run` | <p>Whether to run semantic release in <code>dry-run</code> mode. It will override the <code>dryRun</code> attribute in your configuration file</p> | `false` | `false` |
| `extra-plugins` | <p>Extra plugins for pre-install. You can also specify specifying version range for the extra plugins if you prefer.  Defaults to install @open-turo/semantic-release-config.</p> | `false` | `@open-turo/semantic-release-config ` |
| `docker-username` | <p>Docker username to push the release image to the registry</p> | `false` | `""` |
| `docker-password` | <p>Docker password to push the release image to the registry</p> | `false` | `""` |
<!-- action-docs-inputs source="action.yaml" -->
## Inputs

| parameter | description | required | default |
| --- | --- | --- | --- |
| checkout-repo | Perform checkout as first step of action | `false` | true |
| github-token | GitHub token that can checkout the consumer repository as well as create tags/releases against it. e.g. 'secrets.GITHUB_TOKEN' | `true` |  |
| go-version | Go version to use for building | `true` | 1.17.3 |
<!-- action-docs-inputs -->

<!-- action-docs-outputs source="action.yaml" -->
## Outputs

| name | description |
| --- | --- |
| `version` | <p>Version of the project</p> |
<!-- action-docs-outputs source="action.yaml" -->
## Outputs

| parameter | description |
| --- | --- |
| version | Version of the project |
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

    checkout-fetch-depth:
    # The number of commits to fetch. 0 indicates all history for all branches and tags
    #
    # Required: false
    # Default: 0

    github-token:
    # GitHub token that can checkout the consumer repository as well as create tags/releases against it. e.g. 'secrets.GITHUB_TOKEN'
    #
    # Required: true
    # Default: ""

    dry-run:
    # Whether to run semantic release in `dry-run` mode. It will override the `dryRun` attribute in your configuration file
    #
    # Required: false
    # Default: false

    extra-plugins:
    # Extra plugins for pre-install. You can also specify specifying version range for the extra plugins if you prefer.  Defaults to install @open-turo/semantic-release-config.
    #
    # Required: false
    # Default: @open-turo/semantic-release-config 

    docker-username:
    # Docker username to push the release image to the registry
    #
    # Required: false
    # Default: ""

    docker-password:
    # Docker password to push the release image to the registry
    #
    # Required: false
    # Default: ""
```
<!-- action-docs-usage source="action.yaml" -->
<!-- action-docs-usage -->
<!-- prettier-ignore-end -->
