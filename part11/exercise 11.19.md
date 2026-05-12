# 11.19 Periodic health check

In this exercise I created a separate GitHub Actions workflow for periodically checking the health of the deployed application.

I created a new workflow file called `health-check.yml` inside `.github/workflows`.

The workflow uses the `jtalk/url-health-check-action` action to send HTTP requests to the `/health` endpoint of the Render application.

The workflow runs:

- on pushes to the main branch
- once every day using a cron schedule

I also tested the workflow by intentionally breaking the `/health` endpoint. After deploying the broken version, the workflow failed correctly, proving that the health check works.

Finally, I restored the endpoint and confirmed that the workflow succeeded again.
