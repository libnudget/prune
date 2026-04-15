# PRune

Normalize PR descriptions to paragraph style.

## What it does

- Converts bullet points in `## Summary` to sentences
- Wraps file names in backticks (`action.yml`, `Cargo.toml`)
- Adds available bot commands

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

**Before:**
```
## Summary
- add new feature
- fix bug in utils

## Testing
- tested locally
```

**After:**
```
add new feature. fix bug in utils. Pre-commit covered the changes.

<details>
<summary>Available Bot Commands</summary>

**Cancel Runs:**
- `/cancel-runs`
- `/cancel-runs help`

**Rust Auto-Fix:**
- `/rust-fix fmt`
- `/rust-fix clippy`
- `/rust-fix all`

</details>
```

## License

MIT