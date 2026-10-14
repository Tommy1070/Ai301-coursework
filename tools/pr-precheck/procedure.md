# Procedure: how this tool grades a PR package

## Read order

1. Read the issue first and record the reported problem, expected outcome, and any contributor requirements or relevant thread decisions.
2. Read `plan.md` before reading the implementation. Record the planned scope, named files, implementation approach, test plan, and every entry under `## Deviations`. Reading the plan first prevents the diff from redefining what was supposedly intended.
3. Read the committed branch diff. In live mode, use `git diff main...HEAD`. Record every changed file and the material behavior changed in each hunk.
4. Read `test_evidence.md`. Record the original reproduction result, post-fix result, and the outcome of each repository check that was run.
5. Read `pr_draft.md` last. Record what its title and description claim changed, what testing it claims was performed, what issue it links, and what deviations, limitations, or AI use it discloses.
6. In live mode, also read the repository PR template and `docs/CONTRIBUTING.md` before grading standards and communication checks.
7. Do not grade any rubric check until these reads are complete.

## Evidence gathering

1. For plan fidelity, compare the plan's scope, named files, and implementation approach with every changed file and material hunk in the diff. Record anything implemented but not planned, planned but absent, or covered by an explicit deviation.
2. For test evidence, compare the plan's test plan with `test_evidence.md`. Record whether the original failure was reproduced, whether the post-fix behavior is observable, and the actual result of each planned validation.
3. For repository checks, record the reported outcomes of unit tests, integration tests, lint, and typecheck. Preserve failures, skipped checks, and expected results exactly rather than converting them into assumed success.
4. For diff quality, inspect the changed files and hunks for unrelated edits, debug output, generated debris, commented-out experiments, accidental formatting changes, or other material outside the issue's boundary.
5. For description accuracy, compare every material claim in the PR title and description with the diff and test evidence. Record unsupported claims, omitted material changes, or testing claims that the evidence does not establish.
6. For standards and disclosure, compare `pr_draft.md` with the PR template, contribution guidance, issue-linking requirements, and AI disclosure requirements. Record which required asks are satisfied, omitted, or honestly marked as not applicable.
7. Use `references/evidence-guide.md` to resolve where an evidence family lives. If required evidence genuinely is not present, record it as absent rather than searching for a substitute source.

## Check execution

1. Execute checks in the exact order they appear in `rubric.md`.
2. For each check, use only the gathered evidence named by that rubric row and apply its pass condition literally.
3. Grade `pass` when the evidence satisfies the pass condition.
4. Grade `fail` when the evidence demonstrates that the pass condition is not satisfied.
5. Grade `unclear` when the evidence required to decide the check is missing, contradictory, or insufficient.
6. Do not turn an honestly disclosed failure or limitation into an automatic rejection unless the rubric's pass condition says that outcome makes the PR unready.
7. Once the necessary evidence for a check has been gathered, grade from those recorded facts without reinterpreting the entire package based on later polish or wording.
8. Never invent missing evidence, assume an unrun check passed, or silently repair a package while grading it.

## Verdict assembly

1. Apply the verdict rule in `rubric.md` after every check has a grade.
2. Accept only when every required check passes.
3. Treat every `unclear` required check as a failure for verdict purposes.
4. Reject when any required check is `fail` or `unclear`. Preferred checks never change the verdict.
5. If the verdict is reject, use the first failing or unclear required check in rubric order as the deciding check when a single deciding failure must be quoted. If multiple failures are reported, keep them in rubric order.
6. For every check in the final output, include one concise evidence line containing the specific fact or quote that determined its grade.
7. Emit the final binary verdict and finish with the exact JSON output required by `SKILL.md`. Nothing may appear after that JSON block.