# Sample report

This example is fictional. It shows the text output shape, not a real finding.

```text
RISK PLAN
R1  ████████████  SEVERE    Guest checkout shows totals without tax
R2  █████████░░░  ELEVATED  Saved filters lost after profile edit
R3  ██████░░░░░░  MODERATE  Search returns stale results after rename
```

## Results

```text
R1  ███▒▒▒▒▒▒▒▒▒  SEVERE → LOW   pass, sensitivity proven
R2  █████████░░░  ELEVATED → ELEVATED   blocked: Windows env unavailable
R3  ▓▓▓▓▓▓▓▓▓▓▓▓  MODERATE → CONFIRMED MEDIUM   stale results reproduced
Open risk −67% · 1 finding · Critical/High conclusive: 2 of 3
```

| Summary | Result |
| --- | --- |
| Open-risk reduction | 67% |
| Confirmed findings | 1 |
| Review verdict | NEEDS WORK |

1. **Guest checkout shows totals without tax - Pass**
   - Base: correct tax total
   - PR run 1: correct tax total
   - PR run 2: correct tax total
   - Sensitivity: proven
   - Classification: Pass
   - Reason: the probe detects the predicted missing-tax fault, but the fault is not
     present in the PR revision.

2. **Saved filters lost after profile edit - Blocked**
   - Base: not run
   - PR run 1: not run
   - PR run 2: not run
   - Sensitivity: not proven
   - Classification: Blocked
   - Reason: the required Windows environment is unavailable.

3. **Search returns stale results after rename - Regression**
   - Base: renamed result appears
   - PR run 1: stale result appears
   - PR run 2: stale result appears
   - Sensitivity: proven
   - Classification: Regression
   - Reason: the PR keeps the previous result after a rename.

## Draft review comments

`src/search/index.ts:118`

> Renaming an item leaves the previous name in search results. The end-to-end probe
> passed at the merge base and reproduced the stale result in both PR runs. The same
> probe failed at its assertion when the predicted invalidation fault was introduced.
