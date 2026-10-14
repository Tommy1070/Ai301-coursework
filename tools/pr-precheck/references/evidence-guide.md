# Evidence guide: where evidence lives in a PR package

## Plan fidelity (harness category: silent-drift)

**Where it lives:** In an eval bundle, read the plan-context block's scope, boundary, named files, test plan, and deviation notes against the candidate PR's unified diff and description. In live mode, read `plan.md`, including `## Deviations`, against `git diff main...HEAD` and the title and description in `pr_draft.md`.

**What good looks like:** Every material changed file and behavior falls within the plan's stated boundary or is covered by an explicit, honest deviation. The PR description accurately describes what the diff actually implements. Silent drift exists when the diff adds unplanned work, silently omits planned work, or the description claims fidelity or behavior that the diff contradicts.

## Test evidence (harness category: not-tested)

**Where it lives:** In an eval bundle, read the test-evidence section against the plan-context test plan and reproduction steps, plus any recorded repository check results. In live mode, read `test_evidence.md` against the test plan in `plan.md`, the original reproduction evidence, and the recorded results of unit tests, integration tests, lint, and typecheck.

**What good looks like:** Evidence names observable behavior: what failed before, what happens after the change, and the actual outcome of each relevant repository check. A bare statement such as "tests pass" is not decisive evidence without results that establish what was run. Honest failures or expected no-test outcomes remain useful evidence when reported accurately.

## Diff quality (harness category: unreviewable)

**Where it lives:** In an eval bundle, inspect the candidate PR's unified diff and commit list. In live mode, inspect `git diff main...HEAD` and the branch's commits, using the issue and plan boundary to distinguish relevant work from unrelated changes.

**What good looks like:** The intended fix and its regression coverage are visible without unrelated changes obscuring them. The diff contains no debug leftovers, dead or commented-out experimental code, accidental generated files, broad formatting churn, drive-by refactors, or unrelated edits that make the issue-specific change harder to review.

## Standards and comms (harness category: standards-wall)

**Where it lives:** In an eval bundle, read the repo-facts block for PR-template requirements, contribution instructions, issue-linking rules, maintainer direction, and AI-use disclosure policy, then compare those asks with the candidate PR description. In live mode, read `.github/PULL_REQUEST_TEMPLATE.md`, `docs/CONTRIBUTING.md`, relevant issue-thread instructions, and `pr_draft.md`.

**What good looks like:** Required template sections are answered with real, relevant content; the issue is linked as required; explicit maintainer instructions are addressed; and required AI-use disclosure is present and accurate. Deviations, omissions, or limitations are disclosed rather than hidden. Boilerplate, unchecked required asks, or ignored repository policy indicate a standards-wall failure. Whether the description's implementation claims match the diff is graded under plan fidelity instead.