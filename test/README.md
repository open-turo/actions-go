# GitHub Action Test

## Description

GitHub Action that executes unit tests present anywhere within a golang based GitHub repository and reports results including coverage metrics

## Usage

```yaml
jobs:
  test:
    steps:
      - name: Test
        uses: open-turo/actions-go/test@v1
        with:
          ## example value for github-token provided below
          github-token: ${{ secrets.GITHUB_TOKEN }}
```

## Inputs

| parameter     | description                                                                         | required | default |
| ------------- | ----------------------------------------------------------------------------------- | -------- | ------- |
| checkout-repo | Perform checkout as first step of action                                            | `false`  | true    |
| github-token  | GitHub token that can checkout the consumer repository. e.g. 'secrets.GITHUB_TOKEN' | `true`   |         |

## Runs

This action is an `composite` action.

## Test command used

```shell
go test -cover ./...
```

## Notes

- By default, this action will perform actions/checkout as its first step.
