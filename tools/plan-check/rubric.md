# Rubric: is this plan ready to post and build from?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever
checks you define here (via your procedure.md). It ships empty on
purpose: the judgment is your work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four
   columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where in the package. Name
     the part (the plan's scope statement, the test plan read against
     the repro evidence's steps, the plan comment read against the
     thread highlights, the repo-facts block) or a location from your
     references/evidence-guide.md. "The plan" is not a source; "the
     plan's stated cause read against what the repro evidence shows"
     is.
   - Pass condition: a decision rule about the OUTCOME that someone
     else could apply and get your answer. Judge the thing itself (is
     this one bounded change? could a stranger start executing it?),
     never the write-up's shape (how many sections it has, how long it
     is, whether it uses headings). Structure-shaped checks are what
     make graders disagree with themselves.
   - Weight: `required` (a fail here holds the package) or `preferred`
     (never changes the verdict).

2. A verdict rule below the table: how the check grades combine into
   accept (ready) or reject (hold), including how `unclear` is
   treated. The verdict space is binary. If you write no rule for
   `unclear`, the skill treats it as fail.

Cover what actually gets bad plans posted. The lecture named the
failure families: the diagnosis ignores or contradicts the reproduced
evidence, the change is unbounded (scope creep), the plan targets the
symptom while the evidence points at the cause, a stranger could not
start executing it, the test plan proves nothing observable, the
unknowns are dressed up as certainty, and the comment ignores what the
thread or the repo's stated conventions ask. A rubric that ignores a
family will fail eval packages designed around that family.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Diagnosis grounded in evidence | The plan's stated cause read against the reproduced failure and observed output in the repro evidence. | Pass if the diagnosis is consistent with the reproduced evidence and identifies the cause the implementation should address rather than only restating the symptom. | required |
| Scope is bounded | The plan's scope statement, including what it says will change and what it explicitly leaves unchanged. | Pass if the proposed change is limited to the reproduced issue, names clear boundaries, and avoids unrelated refactors or feature work. | required |
| Test plan proves the fix | The plan's test plan read against the repro evidence's original reproduction steps and observed failure. | Pass if the test plan reruns the relevant reproduction and defines an observable post-fix result that would demonstrate the reported failure no longer occurs. | required |
| Approach is executable | The plan's implementation approach and named files read against the repo-facts block. | Pass if the plan identifies the relevant files and gives enough concrete implementation direction that another contributor could begin the change without inventing the core approach. | required |
| Risks and unknowns are honest | The plan's risks and unknowns read against the repro evidence and repo facts. | Pass if unresolved assumptions or risks are identified as unknowns rather than presented as confirmed facts, and the plan explains how they affect implementation or validation. | required |
| Plan comment fits the issue | The draft plan comment read against the issue thread highlights and the repo's stated conventions. | Pass if the comment communicates the proposed fix in the contributor's own words, addresses relevant thread context, and follows the repository's stated contribution expectations without relying on another contributor's plan. | required |

## Verdict rule

Accept only if every required check passes. Any failed or unclear required check causes a reject. Preferred checks may provide guidance but never change the final verdict.
