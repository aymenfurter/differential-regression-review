# Contributing

Thank you for improving Differential Regression Review.

## Before you start

Open an issue for changes that alter the review method, risk model, evidence threshold,
or safety boundaries. Small documentation corrections can go directly to a pull
request.

## Development

1. Edit the canonical file at
   `skills/differential-regression-review/SKILL.md`.
2. Keep the skill name equal to its parent directory name.
3. Keep the description specific enough to activate only for regression, blast-radius,
   and differential review work.
4. Preserve the rule that only repeatable end-to-end behavior is evidence.
5. Keep all examples fictional and free of credentials or private source code.
6. Run:

   ```bash
   gh skill publish --dry-run
   ```

## Pull requests

Explain the problem, the method change, and the evidence that the change improves the
skill. Keep each pull request focused on one review-method concern.

By contributing, you agree that your contribution is licensed under the MIT License.
