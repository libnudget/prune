# PRune

Write PR descriptions from the actual PR diff.

## What it does

- Shows the base branch SHA before the PR
- Shows the head branch SHA after the PR
- Lists changed files with status and line counts
- Links to the GitHub compare view

## Trigger

Automatically on PR: `opened`, `edited`, `ready_for_review`

## Usage

```yaml
name: Normalize PR

on:
  pull_request_target:
    types: [opened, edited, ready_for_review]

jobs:
  normalize:
    runs-on: ubuntu-latest
    steps:
      - uses: libnudget/prune@v1
```

## Example

**Output:**
```
## Before
`main` at `abc1234`

## After
`fix/example` at `def5678`

## Changed
- `action.yml` modified (+12/-4)
- `README.md` modified (+8/-20)

## Compare
https://github.com/owner/repo/compare/abc1234...def5678
```

## License

MIT
