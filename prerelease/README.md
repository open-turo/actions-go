# GitHub Action Pre-release

<!-- prettier-ignore-start -->
<!-- action-docs-description source="action.yaml" -->
## Description

GitHub Action that produces a new pre-release (snapshot) of a golang based repository.
<!-- action-docs-description source="action.yaml" -->
<!-- prettier-ignore-end -->

<!-- prettier-ignore-start -->
<!-- action-docs-inputs source="action.yaml" -->
## Inputs

| name | description | required | default |
| --- | --- | --- | --- |
| `checkout-repo` | <p>Perform checkout as first step of action</p> | `false` | `true` |
| `checkout-fetch-depth` | <p>The number of commits to fetch. 0 indicates all history for all branches and tags</p> | `false` | `0` |
| `create-prerelease` | <p>Whether semantic-release should create a prerelease or do a dry run. This can be useful to set to true when a prerelease requires pushing artifacts semantic-release is in charge of generating</p> | `false` | `false` |
| `github-token` | <p>GitHub token that can checkout the consumer repository as well as create tags/releases against it. e.g. 'secrets.GITHUB_TOKEN'</p> | `true` | `""` |
| `docker-username` | <p>Docker username to push the prerelease image to the registry</p> | `false` | `""` |
| `docker-password` | <p>Docker password to push the prerelease image to the registry</p> | `false` | `""` |
| `extra-plugins` | <p>Extra plugins for pre-install. You can also specify specifying version range for the extra plugins if you prefer.  Defaults to install @open-turo/semantic-release-config.</p> | `false` | `@open-turo/semantic-release-config ` |
| `post-status-comment` | <p>Whether to post a status comment on the PR with the new version and docker image. Defaults to true.</p> | `false` | `true` |
<!-- action-docs-inputs source="action.yaml" -->

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

<!-- action-docs-runs source="action.yaml -->
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
