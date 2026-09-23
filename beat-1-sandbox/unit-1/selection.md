# Unit 1 — Issue Selection

Path: `beat-1-sandbox/unit-1/selection.md`

Record of the issue carried into Unit 2, and of the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in
the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the
wrong label is not graded.

---

## Selected issue

**Issue link**

https://github.com/codepath/pathreview-ai301-fa26-s3/issues/69

**Verdict output**

issue-select: grade this candidate first issue and print the complete live-mode output, including the final fenced JSON verdict block: https://github.com/codepath/pathreview-ai301-fa26-s3/issues/69
I'll invoke the issue-select skill for this.
● Skill(issue-select)
Successfully loaded skill
I'll start by reading the skill's scope and rubric files.
Read 2 files
Scope confirmed: the issue is in codepath/pathreview-ai301-fa26-s3, the scoped repo. Now the evidence guide.
Read 1 file
Now let me gather live evidence from GitHub.
Ran 3 shell commands
No gh CLI — I'll use the GitHub API directly.
Ran 6 shell commands
A commit message references docs/CONTRIBUTING.md — let me check that plus the PR template for AI policy.
Ran 4 shell commands
Grading: codepath/pathreview-ai301-fa26-s3#69 — "Output parser crashes on a top-level JSON array fallback"
Mode: live. Scope: in-bounds — the issue is in codepath/pathreview-ai301-fa26-s3, the section repo named in scope.md. Path Review house rule applied: classmate claim comments are ignored as blockers.
Evidence gathered (today, 2026-09-22): issue JSON, comment thread, timeline, repo metadata, main commit history, releases list, and contribution-policy surfaces (docs/CONTRIBUTING.md, .github/PULL_REQUEST_TEMPLATE.md, README.md; no root CONTRIBUTING.md, AI_POLICY.md, or AGENTS.md — all 404).
Check: Maintainer activity
Grade: pass
What decided it: Newest main commit authored by a human, "Andrew Burke", 2026-09-16 — 6 days ago,
inside the 90-day window. (Commits carry a Co-Authored-By: Claude trailer, but the author is human,
not a [bot] account.)
────────────────────────────────────────
Check: Repository in use
Grade: pass
What decided it: "archived": false; pushed_at: 2026-09-16T21:50:20Z — 6 days ago, inside 180 days. No
releases exist, but the rule is an OR and last push satisfies it.
────────────────────────────────────────
Check: Newcomer-sized scope
Grade: pass
What decided it: One bounded defect: .items() on a parsed list raises AttributeError, two named files
(rag/generator/output_parser.py, tests/unit/test_output_parser.py), an xfail marker to remove,
"Estimated effort: 2–4 hours". Not an umbrella issue, not a support question, no unsettled design
debate, no maintainer statement about core internals. Labeled good first issue and tier-1.
────────────────────────────────────────
Check: Work availability
Grade: pass
What decided it: "assignees": [], no cross-referenced PR events in the timeline, and the repo has zero
PRs in any state. Two claim comments (Yina-Mu 2026-09-20, tonybuii2003 2026-09-21) are classmates
(author_association: NONE) — the house rule says these do not block, and neither is an abandoned
attempt or a closed-unmerged PR.
────────────────────────────────────────
Check: AI contribution policy
Grade: pass
What decided it: docs/CONTRIBUTING.md contains no match for AI/LLM/Copilot/Claude/disclosure terms; the
PR template requires CI, tests, lint, typecheck and xfail-marker removal but says nothing about AI.
Silence passes, and testing/CI conditions are terms, not bans.
────────────────────────────────────────
Check: Human-authored issue
Grade: pass
What decided it: Opened by Aburke225, "type": "User", author_association: COLLABORATOR — not a [bot]
account.
Verdict rule applied: every required check passes, none unclear → accept. The rubric defines no preferred checks, so there is nothing to rank on beyond fit.
Fit note: this is a strong match for your profile — a Python bug with a reproducible failure mode, a pre-existing xfail test that tells you exactly when you're done, and a blast radius of two files. No architectural change, no refactor.
One thing to watch, not a grading concern: two classmates claimed it in the last two days. Per the house rule that costs you nothing — credit attaches to the PR you open — but claim it yourself in the thread before you start.
```json
{
"item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/69",
"checks": [
{"name": "Maintainer activity", "grade": "pass",
"evidence": "Newest main commit authored by human 'Andrew Burke' on 2026-09-16, 6 days before capture date 2026-09-22 (within 90 days)."},
{"name": "Repository in use", "grade": "pass",
"evidence": ""archived": false and pushed_at 2026-09-16T21:50:20Z, 6 days before capture date (within 180 days)."},
{"name": "Newcomer-sized scope", "grade": "pass",
"evidence": "Single bounded defect naming output_parser.py and its test, "Estimated effort: 2-4 hours", labeled 'good first issue' and 'tier-1'; not umbrella, support, or core-internals work."},
{"name": "Work availability", "grade": "pass",
"evidence": ""assignees": [], no cross-referenced PR in the timeline, and the repo has zero PRs in any state; the two claim comments are classmates (author_association NONE), ignored per the Path Review house rule."},
{"name": "AI contribution policy", "grade": "pass",
"evidence": "No root CONTRIBUTING.md/AI_POLICY.md/AGENTS.md (404); docs/CONTRIBUTING.md has no AI/LLM/Copilot/disclosure mentions and the PR template imposes only CI/test requirements."},
{"name": "Human-authored issue", "grade": "pass",
"evidence": "Opened by Aburke225, "type": "User", author_association COLLABORATOR - not a [bot] account."}
],
"verdict": "accept"
}
```

---


## Eval iterations

Quote source text directly in each field below. Paraphrase does not satisfy them.

**Run history**

agreement: 0/1 scored items

agreement: 1/1 scored items

agreement: 16/20 scored items  (bar: 18/20: below the bar)

agreement: 4/4 scored items

agreement: 20/20 scored items  (bar: 18/20: PASS)

**Issue analysis**

issue-15 — My rubric initially returned accept while the gold label was reject. The original Work availability check passed because the issue had no current assignee and no open linked PR. The issue evidence, however, showed repeated abandoned claims and closed/unmerged attempts. I revised the check so that several abandoned attempts cause the check to fail. On the targeted re-run, my rubric returned reject, matching the gold label.

**Check rationale**

"Work availability | Repo facts: this issue assignees and linked PRs; Comments section for PR mentions and active claim statements | Pass if the issue has no current assignee and no open linked or comment-mentioned PR actively implementing the issue. One closed unmerged PR is an abandoned attempt rather than an active claim, but several abandoned claim or closed-unmerged-PR attempts indicate the issue is not suitable as a first contribution and fail this check. | required"

I used this form because a single abandoned attempt does not necessarily mean someone is currently working on an issue, while several abandoned attempts are evidence that the issue may be more difficult than it initially appears.

**Trade-offs**

This check changes issue-15 from accept to reject because it had repeated abandoned claims and closed/unmerged attempts. I re-ran issue-15 with --only as part of the targeted run of issue-11, issue-15, issue-19, and issue-20, and that run reached agreement: 4/4 scored items.

---

## Selection rationale

Graded on whether all three are answered, in your own words. Not on how good the
reasoning is, and not on length — a short honest answer to each earns the full marks.
This is also the basis for the claim comment you write in Unit 2.

**Selection rationale**

1. Issue #69 fits my interests because it is a focused Python debugging task involving an output parser and tests. I am comfortable working with Python and debugging, and the estimated 2–4 hour scope fits the time I have available.

2. The verdict correctly identified that the repository is active, the issue is bounded, there is no blocking active PR or assignee under the Path Review rules, and there is no AI contribution ban. I also weighed whether I personally felt comfortable debugging the parser and understanding the existing test, which the rubric cannot fully measure.

3. I expect claiming the issue to be straightforward. There are recent classmate claim comments, but the Path Review house rule says those comments do not block the issue. I will follow the required claiming process when I begin Unit 2.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/issue-select/`.
