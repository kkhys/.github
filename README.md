# .github

Shared defaults for [@kkhys](https://github.com/kkhys) repositories.

## Labels

[`.github/labels.yml`](./.github/labels.yml) is the shared base label set, managed declaratively with [gh-labeler](https://github.com/kkhys/gh-labeler) and applied by [gh-labeler-actions](https://github.com/kkhys/gh-labeler-actions).

Each repository inherits the base from its own `.github/labels.yml`:

```yaml
extends: kkhys/.github

labels:
  # Repository-specific labels; an entry with the same name as an
  # inherited label overrides it, and `delete: true` cancels one.
  - name: "type: submodule"
    description: "Submodule update"
    color: "#f2edfc"
```

Changes to the base propagate when each repository's sync workflow next runs (on its own config changes, on schedule, or manually via `workflow_dispatch`).
