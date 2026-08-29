# Differential Regression Review

Turn pull request risk into repeatable end-to-end evidence.

> **The base branch is the control. The PR branch is the experiment.**
> Code reading forms hypotheses. Only end-to-end behavior counts as evidence.

Most reviews ask whether the code looks correct. This skill asks a stricter question:
**Did the pull request change user-visible behavior that it was not meant to change?**

It creates disposable end-to-end probes, compares the base and PR revisions, proves
that high-risk probes can detect their predicted faults, and reports only repeatable
behavioral evidence.

## Install

Requires [GitHub CLI 2.90.0 or later](https://cli.github.com/).

```bash
gh skill preview aymenfurter/differential-regression-review differential-regression-review
gh skill install aymenfurter/differential-regression-review differential-regression-review
```

Then ask your agent:

```text
Review PR #4821 for user-visible regressions.
```

## What it changes

| Ordinary review | Differential Regression Review |
| --- | --- |
| Reads the diff and predicts defects | Traces each risk to a causal chain in the diff |
| Uses one reviewer's risk list | Merges 2-3 independent maximum-reasoning risk passes |
| Runs the existing test suite | Writes disposable probes at public boundaries |
| Tests only the PR revision | Compares the merge base with the PR head |
| Accepts one green run | Runs each PR probe twice and the base probe once |
| Trusts a passing test | Proves Critical and High probes can detect the predicted fault |
| Uses one timing sample | Compares repeated-run medians for user-visible slowdowns |
| Reports plausible concerns | Drafts comments only for repeatable regressions |
| Gives an opinion-based verdict | Gates `LGTM` on findings, follow-up work, and evidence coverage |
