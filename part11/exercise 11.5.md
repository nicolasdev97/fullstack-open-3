# 11.5 Static Analysis Workflow

In this exercise, I created my first real CI pipeline using GitHub Actions.

The workflow was added inside:

```bash
.github/workflows/pipeline.yml
```

Workflow content:

```yaml
name: Pokedex Pipeline

on:
  push:

jobs:
  lint:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Use Node.js
        uses: actions/setup-node@v4
        with:
          node-version: "16"

      - name: Install dependencies
        run: npm install

      - name: Run ESLint
        run: npm run eslint
```

Main concepts learned:

- `actions/checkout`
  Downloads the repository into the GitHub Actions virtual machine.

- `actions/setup-node`
  Installs a specific Node.js version.

- `npm install`
  Installs project dependencies inside the workflow environment.

- `npm run eslint`
  Executes static code analysis automatically.

I also learned that workflows can fail intentionally if the project contains linting errors.

This is useful because CI pipelines help detect problems automatically before deploying or merging code.

Main takeaway:
CI/CD pipelines automate quality checks and ensure code consistency across environments.
