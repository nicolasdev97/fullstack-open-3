# 11.20 Own deployment pipeline

In this exercise I created a CI/CD pipeline for one of my own full stack applications.

I used a Phonebook application with a React frontend and an Express backend.

I created a new repository and restructured the application into a monorepo format where both frontend and backend are stored in the same repository.

I configured:

- ESLint
- automated tests
- GitHub Actions workflows
- automatic deployment to Render
- health checks
- pull request checks
- version tagging

The pipeline automatically runs linting, tests, build steps, and deployment when changes are pushed to the main branch.

I also configured periodic health checks and protected the main branch with pull request requirements.
