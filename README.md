# PRune

Normalize PR descriptions to paragraph style.

## What it does

- Converts bullet points in `## Summary` to sentences
- Wraps file names in backticks (`action.yml`, `Cargo.toml`)
- Adds available bot commands

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

## License

MIT