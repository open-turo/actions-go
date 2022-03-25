# GitHub Action Test

GitHub Action that runs unit tests present within a go based GitHub repository
and report test coverage metrics.

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

Note: by default, this action will perform actions/checkout as its first step.

## Test

It will run to detect and execute all unit tests in the top level of the
repository and all subdirectories.

```shell
go test -cover ./...
```
