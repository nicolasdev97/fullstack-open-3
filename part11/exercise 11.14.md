# 11.14 Running Deployments Only for the Main Branch

In this exercise, I updated the deployment step so that deployments only happen when code is pushed to the `main` branch.

## The problem

Previously, the deployment step also ran for pull requests. This is dangerous because unfinished or experimental code could accidentally be deployed to production.

## Solution

I added a condition to the deployment step:

```yaml
- name: Trigger Render deployment
  if: ${{ github.event_name == 'push' }}
  run: curl https://api.render.com/deploy/srv-${{ secrets.RENDER_SERVICE_ID }}?key=${{ secrets.RENDER_API_KEY }}
```

## Result

Now the workflow behaves correctly:

- Pull requests run CI checks only
- Deployments happen only after merging to `main`

When testing the pull request workflow, the deployment step appeared as “Skipped”, which confirmed the condition worked correctly.

After merging the pull request into `main`, the deployment step executed successfully and Render deployed the new version of the application.

## Main takeaway

This exercise helped me understand how production deployments should only happen from stable branches and how GitHub Actions conditions can be used to control workflow behavior safely.
