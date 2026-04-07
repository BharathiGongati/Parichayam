# Contributing

## Recommended Workflow

1. Start from the latest `main`.
2. Create a short-lived branch:
   - `feature/<topic>`
   - `fix/<topic>`
   - `chore/<topic>`
3. Make the change in that branch.
4. Push the branch to GitHub.
5. Open a pull request into `main`.
6. Let CodeRabbit review the PR.
7. Fix important findings, then merge to `main`.

## Pull Request Guidelines

- Keep PRs small when possible.
- Separate UI changes from security/backend changes if they are unrelated.
- Mention affected areas clearly:
  - frontend pages
  - admin panel
  - Firebase rules
  - Cloud Functions
  - payments
- Include a short test note in the PR.

## CodeRabbit Usage

After CodeRabbit is installed on the repository, it will automatically review pull requests opened against `main`.

Useful PR comments:

- `@coderabbitai review`
- `@coderabbitai full review`
- `@coderabbitai resolve`
- `@coderabbitai summary`

## High-Risk Areas In This Repo

- `functions/index.js`
- `firestore.rules`
- `storage.rules`
- `admin.html`
- `dashboard.html`
- `parichayam-firebase.js`

Changes in these files should be reviewed carefully before merge.

