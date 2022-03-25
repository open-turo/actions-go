# GitHub Action Integration-Test

GitHub Action that conditionally executes integration tests via docker compose if the docker compose file is present.

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
