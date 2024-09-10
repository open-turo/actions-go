# GitHub Action Pre-release

<!-- prettier-ignore-start -->
<!-- action-docs-description source="prerelease/action.yaml" -->
## Description

GitHub Action that produces a new pre-release (snapshot) of a golang based repository.
<!-- action-docs-description source="prerelease/action.yaml" -->
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
<!-- action-docs-inputs source="prerelease/action.yaml" -->
## Inputs

| name | description | required | default |
| --- | --- | --- | --- |
| `checkout-repo` | <p>Perform checkout as first step of action</p> | `false` | `true` |
| `github-token` | <p>GitHub token that can checkout the consumer repository as well as create tags/releases against it. e.g. 'secrets.GITHUB_TOKEN'</p> | `true` | `""` |
| `go-version` | <p>Go version to use for building</p> | `true` | `1.17.3` |
| `push-docker-snapshot` | <p>If a docker snapshot image is generated, push it to the to the registry</p> | `false` | `false` |
| `docker-username` | <p>Docker username to push the snapshot image to the registry</p> | `false` | `""` |
| `docker-password` | <p>Docker password to push the snapshot image to the registry</p> | `false` | `""` |
<!-- action-docs-inputs source="prerelease/action.yaml" -->

<!-- action-docs-outputs source="prerelease/action.yaml" -->
## Outputs

| name | description |
| --- | --- |
| `version` | <p>Version of the project</p> |
<!-- action-docs-outputs source="prerelease/action.yaml" -->
## Outputs

| parameter | description |
| --- | --- |
| version | Version of the project |
<!-- action-docs-outputs -->

<!-- action-docs-runs source="prerelease/action.yaml -->
## Runs

This action is a `composite` action.
<!-- action-docs-runs -->

## Usage

```yaml
name: Prerelease

on:
  pull_request:
    types:
      - opened
      - labeled
      - synchronize

jobs:
  prerelease:
    name: Build and push pre-release image
    if: contains(github.event.pull_request.labels.*.name, 'prerelease')
    steps:
      - name: Pre-release
        uses: open-turo/actions-go/prerelease@v2
        with:
          github-token: ${{ secrets.GITHUB_TOKEN }}
          push-docker-snapshot: true
          docker-username: ${{ secrets.DOCKER_USERNAME }}
          docker-password: ${{ secrets.DOCKER_PASSWORD }}
```
<!-- prettier-ignore-end -->
