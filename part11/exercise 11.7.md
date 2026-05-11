# 11.7 Build and Test Workflow

In this exercise, I expanded the GitHub Actions pipeline by adding build and test steps.

Updated workflow:

```yaml
name: Pokedex Pipeline

on:
  push:

jobs:
  pipeline:
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

      - name: Build project
        run: npm run build

      - name: Run tests
        run: npm test
```

Main concepts learned:

## Build step

The build step creates a production version of the application.

It verifies that:

- the application compiles correctly
- imports are valid
- dependencies exist

## Test step

The test step executes automated tests using Jest.

Tests help verify that the application behaves correctly.

I also learned that CI pipelines often fail intentionally when tests contain errors.

This is useful because developers can detect problems early before deployment.

Main takeaway:
CI pipelines automate not only code quality checks, but also application compilation and automated testing.
