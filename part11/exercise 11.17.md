# 11.17 Protecting the Main Branch

In this exercise, I added branch protection rules to the `main` branch in GitHub.

## Branch protection configuration

I created a protection rule for the `main` branch and enabled the following settings:

- Require pull requests before merging
- Require at least one approval before merging
- Require status checks to pass before merging

I also enabled the option:

- Require branches to be up to date before merging

## Status checks

I selected the GitHub Actions workflow jobs as required checks. This means that:

- linting
- tests
- e2e tests
- deployment pipeline

must all pass successfully before a pull request can be merged.

## Result

After enabling branch protection:

- direct pushes to `main` are restricted
- pull requests must pass CI checks
- pull requests require approval before merging

## Main takeaway

This exercise helped me understand how protected branches improve code quality and prevent broken code from reaching production. It also showed how CI/CD pipelines integrate with GitHub branch protection rules in professional development workflows.
