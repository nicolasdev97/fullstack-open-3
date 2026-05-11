# 11.6 Fixing the Code

In this exercise, I fixed the linting errors detected by the GitHub Actions pipeline.

I learned how to debug workflow failures by reading the logs generated in GitHub Actions.

Main issues fixed:

## Node.js environment errors

Errors like:

```bash
'module' is not defined
'require' is not defined
```

were fixed by configuring ESLint to use the Node.js environment.

I updated the ESLint configuration:

```json
{
  "env": {
    "browser": true,
    "es2021": true,
    "node": true
  }
}
```

## Console log errors

ESLint complained about `console.log` statements.

Instead of removing them, I disabled the rule for specific lines:

```js
// eslint-disable-next-line no-console
console.log("message");
```

## Automatic fixes

I used:

```bash
npm run eslint -- --fix
```

to automatically fix:

- quotes
- indentation
- semicolons
- trailing spaces

## Unused variables

I removed unused imports such as `Router` from `App.jsx`.

Main takeaway:
CI pipelines help automatically detect code quality issues, while ESLint helps enforce consistent coding standards.
