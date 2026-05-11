# 11.9 Simple End-to-End Tests

In this exercise, I added end-to-end (E2E) testing using Playwright.

Unlike unit tests, E2E tests verify that the entire application works correctly from the user's perspective.

## Playwright setup

I installed Playwright inside the project and created a new directory:

```text
e2e-tests
```

I also configured Jest to ignore E2E tests:

```json
"jest": {
  "testEnvironment": "jsdom",
  "testPathIgnorePatterns": ["e2e-tests"]
}
```

## First E2E test

I created a test that:

- opens the front page
- verifies that "ivysaur" is visible
- verifies that the footer text exists

## Navigation test

I added another test that:

- clicks the Ivysaur link
- verifies that the Pokémon page opens correctly
- checks that the text "chlorophyll" is visible

## Playwright configuration

I configured:

- `baseURL`
- automatic web server startup using `webServer`

This allows Playwright to automatically start the application before running tests.

## CI integration

I added Playwright execution to GitHub Actions.

The pipeline now performs:

- linting
- build
- unit tests
- E2E tests

Main takeaway:
End-to-end tests provide confidence that the application works correctly for real users, although they increase pipeline execution time.
