# 11.12 Health Checks

In this exercise, I added a health check endpoint to the backend application and configured Render to use it during deployments.

## Health endpoint

I added the following route to the Express server:

```js
app.get("/health", (req, res) => {
  res.send("ok");
});
```

This endpoint allows Render to verify that the application is running correctly after deployment.

## Render health check configuration

Inside the Render dashboard, I configured the Health Check Path as:

```text
/health
```

Render now checks this endpoint before marking a deployment as successful.

## Simulating a failed deployment

To test the health check system, I intentionally broke the endpoint:

```js
app.get("/health", (req, res) => {
  if (true) throw "error...";
  res.send("ok");
});
```

After pushing the changes, Render detected that the application was unhealthy and prevented the broken version from replacing the previous deployment.

## Main takeaway

This exercise helped me understand how health checks improve deployment reliability and how platforms like Render can prevent broken applications from going live.
