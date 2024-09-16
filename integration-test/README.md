# GitHub Action Integration-Test

<!-- prettier-ignore-start -->
<!-- action-docs-description source="action.yaml" -->
## Description

Conditionally executes golang integration tests via docker, if docker compose file is found
<!-- action-docs-description source="action.yaml" -->

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
    # GitHub token for docker compose. e.g. 'secrets.GITHUB_TOKEN'.
    #
    # Required: true
    # Default: ""

    docker-compose-file:
    # Relative or absolute path to docker-compose.yaml file
    #
    # Required: false
    # Default: ./docker-compose.yaml

    full-compose-output:
    # Set this to true to log all container output from docker-compose
    #
    # Required: false
    # Default: false
```
<!-- action-docs-usage source="action.yaml" -->

## Usage

```yaml
jobs:
  integration-test:
    name: Test / Integration
    steps:
      - uses: open-turo/actions-go/integration-test@v1
        with:
          ## example value for github-token provided below
          github-token: ${{ secrets.GITHUB_TOKEN }}
```

Note: by default, this action will perform actions/checkout as its first step.

## Integration-Test

If the docker compose file is present, the action will run:

```shell
docker-compose up --build --exit-code-from test test
docker-compose down
```
<!-- prettier-ignore-end -->
