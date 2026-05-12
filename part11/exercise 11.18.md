# 11.18 Build Success and Failure Notifications

In this exercise, I integrated Discord notifications into the GitHub Actions workflow.

## Discord webhook

I added the Discord webhook URL as a GitHub secret:

```text
DISCORD_WEBHOOK
```

This keeps the webhook private and prevents it from being exposed in the repository.

## Success notification

I added a notification step that runs after successful deployments:

```yaml
if: ${{ success() && github.event_name == 'push' && !contains(join(github.event.commits.*.message), '#skip') }}
```

The notification sends a success message to Discord when a new version is deployed successfully.

## Failure notification

I also added a failure notification step:

```yaml
if: ${{ failure() }}
```

The failure notification includes:

- commit SHA
- commit message
- author

This helps identify the exact commit that caused the failure.

## Testing

I tested both scenarios:

- successful deployment
- intentionally broken build

Both notifications were delivered correctly to Discord.

## Main takeaway

This exercise helped me understand how CI/CD pipelines can communicate deployment and build status automatically using external messaging services like Discord.
