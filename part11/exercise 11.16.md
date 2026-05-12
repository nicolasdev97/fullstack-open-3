# 11.16 Skipping Deployments and Tagging

In this exercise, I modified the GitHub Actions workflow so deployments and version tagging can be skipped using `#skip` in commit messages.

## Goal

Sometimes not every commit should trigger a deployment or a new version tag. For example:

- documentation updates
- debugging changes
- temporary commits

To solve this, I added conditions to the deployment and tagging steps.

## Deployment condition

I updated the deployment step with this condition:

```yaml
if: ${{ github.event_name == 'push' && !contains(join(github.event.commits.*.message), '#skip') }}
```

## Tagging condition

I also updated the version tagging step with the same condition.

## How it works

The workflow:

1. Checks if the event is a push to the main branch
2. Reads all commit messages
3. Searches for `#skip`
4. Skips deployment and tagging if the keyword exists

## Testing

I tested the workflow with a commit message containing:

```text
#skip
```

The CI pipeline still ran tests successfully, but:

- deployment was skipped
- version tagging was skipped

Then I tested another commit without `#skip`, and the deployment and tagging worked normally.

## Main takeaway

This exercise helped me understand how workflow conditions and GitHub context data can be used to create smarter and more flexible CI/CD pipelines.
