### Exercise 11.21

The main branch of the repository was protected using GitHub Branch Protection Rules.

The following rules were enabled:

- Require a pull request before merging
- Require approvals before merging
- Require status checks to pass before merging
- Restrict administrators from bypassing the rules

The workflow checks configured in GitHub Actions were selected as required checks before allowing merges into the `main` branch.

A new branch was created for development changes, and a pull request was opened targeting the `main` branch.

The GitHub user `mluukkai` was invited as a collaborator to the repository using the repository collaboration invitation link. After that, a review request was created for the pull request.

Once the review process was completed and all GitHub Actions checks passed successfully, the pull request was merged into the `main` branch.
