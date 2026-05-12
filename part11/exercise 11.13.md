# 11.13 Pull Requests

In this exercise, I updated the GitHub Actions workflow so that it also runs for pull requests targeting the main branch.

## Workflow trigger

I modified the workflow configuration:

```yaml
on:
  push:
    branches:
      - main

  pull_request:
    branches: [main]
```

This allows the CI pipeline to run automatically whenever a pull request is opened or updated.

## Creating a pull request

I created a new branch:

```bash
git checkout -b exercise-11-13
```

Then I committed my changes and pushed the branch to GitHub.

After that, I opened a pull request targeting my own repository’s `main` branch.

## CI checks

When the pull request was created, GitHub Actions automatically started running all checks:

- ESLint
- Build
- Unit tests
- E2E tests
- Deployment

Once all checks passed, the pull request showed a successful status.

## Main takeaway

This exercise helped me understand why pull requests are important in professional development workflows. Running CI before merging changes helps prevent broken code from reaching the main branch.
