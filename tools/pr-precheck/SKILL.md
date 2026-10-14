---
name: pr-precheck
description: Grade a PR package (a candidate pull request read against the plan it claims to implement and the issue that plan belongs to) and decide whether it is ready to submit. Use when checking your own branch, draft PR title, and description before opening the pull request, or when grading an eval package bundle.
---

# pr-precheck: rubric-driven PR grading

## The question

Grade exactly one PR package and answer one question: is this pull
request ready to submit?

Treat the PR package as the candidate PR title and description, the
committed branch diff, test evidence, and the plan it claims to
implement, read against the issue that plan belongs to. Do not grade a
different artifact or substitute general impressions for the checks
defined by this skill.

## Inputs and modes

Operate in exactly one of two modes:

- **Live mode**: grade the student's own PR before submission. Read
  `plan.md`, including any `## Deviations` notes; the committed branch
  diff produced by `git diff main...HEAD` from the working copy; the
  draft PR title and description in `pr_draft.md`; the test evidence
  in `test_evidence.md`; and the issue URL supplied by the student.
  Gather issue-side evidence from the real repository, including the
  issue thread, `.github/PULL_REQUEST_TEMPLATE.md`, and
  `docs/CONTRIBUTING.md`. For a house-chain student, read the supplied
  house plan and house repro pack in place of the student's own plan
  and reproduction evidence, while applying the same checks.
- **Eval mode**: grade one practice package bundle. Treat the bundle
  text as the whole world. Do not fetch GitHub, inspect the working
  directory, or use outside evidence. Run every rubric check and the
  complete verdict rule using only evidence contained in the bundle.

## The scope seam (live mode only)

In live mode, read `scope.md` before grading anything else. Apply the
repository and house rules it defines. Refuse to grade a PR outside
the repository named by its `Repo:` line.

If the `Repo:` line still contains an unfilled placeholder, stop
without grading and tell the student to fill it with their section's
Path Review repository. Never guess the repository.

In eval mode, ignore `scope.md` entirely.

## The voice seam (live mode only)

In live mode, read `voice-guide.md` and check the outgoing PR title
and description against its rules. Report any broken voice rule in
the readable summary and identify the rule that was broken.

The voice guide does not change the verdict by itself unless a check
in `rubric.md` explicitly uses it.

In eval mode, ignore `voice-guide.md` entirely.

## Component reads

Read `rubric.md` for the checks, their evidence requirements, pass
conditions, weights, and the final verdict rule.

Use `references/evidence-guide.md` as the map for where each evidence
family lives in a practice package and in a live PR package, and for
what counts as useful evidence.

Execute `procedure.md` exactly as written. It defines the read order,
evidence gathering, check execution, and verdict assembly. If the
procedure is silent about a necessary step, report that gap instead
of inventing a step or silently working around it.

If `rubric.md` contains no completed checks or `procedure.md`
contains no completed operating steps, refuse to grade. Explain which
required component is empty rather than inventing checks or a
procedure at runtime.

## Verdict and output

Use only two final verdicts: `accept` means the PR is ready to submit,
and `reject` means hold the PR.

A readable per-check summary may appear before the machine-readable
result. End every completed grading run with the fenced JSON block
below. It must be valid, must be the last fenced JSON block, and
nothing may appear after it.

```json
{
  "item": "<PR URL or bundle id>",
  "checks": [
    {"name": "<check name>", "grade": "pass|fail|unclear",
     "evidence": "<one line: the fact or quote that decided it>"}
  ],
  "verdict": "accept|reject"
}