# GitHub Action Lint

GitHub Action that runs lint on a go based GitHub repository.

## Usage

```yaml
jobs:
  build:
    steps:
      - name: Action lint
        uses: open-turo/actions-go/lint@v1
        with:
          ## example value for github-token provided below
          github-token: ${{ secrets.GITHUB_TOKEN }}
```

Note: by default, this action will perform actions/checkout as its first step.

## Lint Checks

This action runs the following lint checks:

- [action-pre-commit](https://github.com/open-turo/action-pre-commit)

## Notes

- If the repository has a `package-lock.json`:
  - It will execute `npm ci` before running the `pre-commit` step.
- `actionlint` must be installed and in the path to ensure that https://github.com/rhysd/actionlint can be run directly.
- This expects that `.commitlintrc.yaml` will be present to enforce [`conventional-commit`](https://github.com/wagoid/commitlint-github-action).
- Checkout must have history to ensure that commit message linting works.
