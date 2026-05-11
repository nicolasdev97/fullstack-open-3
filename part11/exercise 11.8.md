# 11.8 Back to Green

In this exercise, I investigated failing tests in the CI pipeline and fixed the application code without modifying the tests.

At first, the workflow output showed many `console.warn` messages related to React Router future flags.

However, the actual failing test was:

```text
Expected href="/pokemon/vaporeon"
Received href="/pokemon/ditto"
```

This helped me understand that warnings are not always the real problem.

## Main issue fixed

The navigation logic inside `PokemonPage.jsx` was incorrect.

The "Next" link was pointing to the current Pokémon instead of the next Pokémon.

I updated the component to use the correct next Pokémon value.

## Console logs

I also removed unnecessary `console.log` statements from the component.

## Testing

After fixing the code, all tests passed successfully both locally and in GitHub Actions.

Commands used:

```bash
npm test
npm run eslint
```

Main takeaway:
CI pipelines and automated tests help detect application bugs early, while reading logs carefully is essential to identify the real source of failures.
