# Contributing

1. Open an issue describing the change and its acceptance criteria.
2. Create a short-lived branch from `main` (`feature/...` or `fix/...`).
3. Keep changes focused. Add tests for observable behavior and update docs for API or configuration changes.
4. Run `npm ci` and `npm run check` before opening a pull request.
5. Explain the change, test result, deployment impact, and any data or privacy implications in the pull request.
6. Request review before merging. Never commit client documents, credentials, `.env`, or generated output.

Use clear commit subjects such as `feat: add task persistence` or `docs: clarify local setup`. Report security concerns privately to the owner rather than posting secrets in an issue.
