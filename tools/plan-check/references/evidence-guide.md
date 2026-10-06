# Evidence guide: where evidence lives in a plan package

<!--
THIS IS THE PART YOU WRITE (second week running: the judgment files
stay in your hands). The skill uses this guide as its map: for every
kind of evidence a rubric check names, this file says WHERE to find it
in a plan package and WHAT GOOD LOOKS LIKE when you do.

Under each family heading below, write:

- Where it lives: the exact places to look. In an eval bundle (which
  section of the package: the issue context, the repro-evidence block,
  the candidate plan's scope statement or test plan, the plan comment,
  the repo-facts block). In live mode (where on GitHub or in the
  draft: the issue thread, the student's posted repro comment, the
  repo's docs, the draft plan and comment).
- What good looks like: one or two sentences someone else could apply.
  Prefer observable conditions ("the stated cause cites behavior the
  repro evidence actually shows") over adjectives ("diagnosis is
  solid").

A rubric check whose evidence this guide cannot locate is a check
nobody else can execute, and this week that cuts twice: your
procedure.md tells the skill WHEN to gather each family, and this
guide tells it WHERE. Write the map you wish your executor had.
-->

## Diagnosis and grounding

Where it lives: In eval mode, read the candidate plan's diagnosis against the repro-evidence block and issue context. In live mode, compare the diagnosis in plan.md with the student's posted reproduction comment and the issue thread.

What good looks like: The stated cause explains behavior that the reproduction actually demonstrated and does not contradict the observed failure. It should identify the underlying cause the implementation will address rather than merely repeat the visible symptom.

## Scope

Where it lives: In eval mode, read the candidate plan's in-scope and out-of-scope statements plus the files or areas it proposes changing. In live mode, inspect those same parts of plan.md and compare them with the reproduced issue.

What good looks like: The plan proposes one bounded change that directly addresses the reproduced issue. It clearly identifies what will and will not change and avoids unrelated refactors, features, or cleanup.

## Executability

Where it lives: In eval mode, read the candidate plan's named files or areas and implementation approach against the repo-facts block. In live mode, read plan.md alongside the relevant repository files and conventions.

What good looks like: The plan identifies where the change belongs and explains the implementation approach concretely enough that another contributor could begin the work without having to invent the core solution.

## Test plan

Where it lives: In eval mode, read the candidate plan's test plan against the commands, steps, and observed output in the repro-evidence block. In live mode, compare plan.md's test plan with the student's posted reproduction evidence.

What good looks like: The test plan reruns the relevant reproduction and states a specific observable result that would prove the reported failure is fixed. It should make clear what passes after the change that failed before.

## Honesty

Where it lives: In eval mode, read the candidate plan's risks, unknowns, assumptions, and deviations against the repro evidence and repo-facts block. In live mode, inspect those sections in plan.md and compare them with what the reproduction and repository actually establish.

What good looks like: Unverified assumptions are labeled as unknowns instead of stated as facts. Risks that could affect implementation or validation are acknowledged, and any difference between the posted plan and the eventual build is recorded honestly under Deviations.

## Comms

Where it lives: In eval mode, read the candidate plan comment against the issue/thread highlights and the repo-facts block, including any contribution or AI-use requirements. In live mode, compare comment.md with the GitHub issue thread and the repository's contribution guidance.

What good looks like: The comment communicates the contributor's own diagnosis, proposed change, validation plan, and relevant uncertainty while responding to maintainer or thread context. It follows the repository's stated contribution requirements and does not rely on another contributor's plan.
