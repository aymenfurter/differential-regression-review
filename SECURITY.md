# Security policy

Agent skills can influence tool use and can include executable resources. Treat every
skill as code and inspect it before installation.

## Report a vulnerability

Use
[GitHub private vulnerability reporting](https://github.com/aymenfurter/differential-regression-review/security/advisories/new)
for:

- prompt injection that can bypass the skill's safety rules;
- credential or private-data exposure;
- unintended writes, commits, pushes, or production side effects;
- unsafe test cleanup or worktree handling.

Do not open a public issue for a security report. Include a minimal reproduction with
fictional data. Do not include credentials, private source code, or production logs.

You can expect an initial response within seven days.
