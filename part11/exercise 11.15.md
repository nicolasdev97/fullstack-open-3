# 11.15 Adding Versioning

In this exercise, I extended the GitHub Actions workflow to automatically create version tags after successful deployments.

## Workflow structure

I separated the workflow into two jobs:

- `simple_deployment_pipeline`
- `tag_release`

The second job depends on the first one:

```yaml
tag_release:
  needs: [simple_deployment_pipeline]
```

This ensures that version tags are only created if all checks, tests, and deployments succeed.

## Automatic version bumping

I used the GitHub Action:

```yaml
uses: anothrNick/github-tag-action@1.71.0
```

I configured the action like this:

```yaml
env:
  GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
  DEFAULT_BUMP: patch
```

The `patch` configuration increases the last number of the version automatically.

Example:

```text
v1.0.0 → v1.0.1
```

## Running only on main branch

I also added a condition so version tags are not created for pull requests:

```yaml
if: ${{ github.event_name == 'push' }}
```

## Result

After merging changes into the `main` branch, GitHub Actions automatically created a new version tag in the repository.

## Main takeaway

This exercise helped me understand how automated versioning works in CI/CD pipelines and why release tagging is useful in professional software development workflows.
