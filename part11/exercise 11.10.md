# 11.10 Deploying the Application to Render

In this exercise, I deployed the Pokédex application to Render.

The project contains both frontend and backend code in the same repository, so the deployment process required building the React frontend and serving the production files using Express.

## Render configuration

### Build command

```bash
npm install && npm run build
```

This installs dependencies and creates the production frontend build inside the `dist` folder.

### Start command

```bash
npm run start-prod
```

This starts the Express server in production mode.

## Important considerations

The project requires Node.js 16, so I added a `.node-version` file containing:

```text
16
```

I also disabled automatic deploys because future exercises will use GitHub Actions to control deployments.

## Main takeaway

This exercise helped me understand how frontend and backend applications can be deployed together in the same Node.js service and how production builds are served using Express.
