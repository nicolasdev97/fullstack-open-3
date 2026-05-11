# 11.11 Automatic Deployments

In this exercise, I configured automatic deployments from GitHub Actions to Render.

Instead of deploying manually, the application is now automatically deployed whenever the CI pipeline finishes successfully.

## Render Deploy Hook

I used Render Deploy Hooks because they are simpler and more reliable than some custom GitHub Actions.

The deployment step was added at the end of the workflow:

```yaml
- name: Trigger Render deployment
  run: curl https://api.render.com/deploy/srv-${{ secrets.RENDER_SERVICE_ID }}?key=${{ secrets.RENDER_API_KEY }}
```

## GitHub Secrets

I created two repository secrets:

- `RENDER_SERVICE_ID`
- `RENDER_API_KEY`

This prevents sensitive information from being exposed in the repository.

## Deployment flow

Now the pipeline works like this:

1. Install dependencies
2. Run ESLint
3. Build the project
4. Run tests
5. Run E2E tests
6. Trigger automatic deployment to Render

## Main takeaway

This exercise helped me understand how continuous deployment works in real projects and how CI/CD pipelines can automate the entire deployment process safely.
