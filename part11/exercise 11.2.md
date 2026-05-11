# 11.2 The Example Project

In this exercise, I forked the example Pokedex repository from Full Stack Open and cloned it to my local machine.

Important thing learned:
The Pokedex project should be kept as an independent Git repository and not inside my main Full Stack Open repository, because GitHub Actions and CI/CD workflows work better with separate repositories.

I also learned that this project requires Node.js version 16 because the project is relatively old.

Commands used:

```bash
npm install
npm test
npm run eslint
npm run build
```

The project contains:

- frontend
- backend
- tests
- webpack configuration

I noticed that some tests and linting errors already exist intentionally and should not be fixed yet.

Main takeaway:
Before configuring CI/CD pipelines, it is important to understand the project structure and available npm scripts.
