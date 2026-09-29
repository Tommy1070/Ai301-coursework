# Evidence guide: where proof lives in a reproduction package

<!--
THIS IS THE PART YOU WRITE (new this week: Unit 1 handed you this file
finished; the scaffolding fades). The skill uses this guide as its map:
for every kind of proof a rubric check names, this file says WHERE to
find it in a package and WHAT GOOD LOOKS LIKE when you do.

Under each family heading below, write:

- Where it lives: the exact places to look. In an eval bundle (which
  section of the package: the issue context, the repo-facts block, the
  claim comment, the repro report and its parts). In live mode (where
  on GitHub or in the draft: the issue thread, the repo's docs, the
  student's draft comment).
- What good looks like: one or two sentences someone else could apply.
  Prefer observable conditions ("the versions named match what the
  issue targets, or the difference is called out") over adjectives
  ("environment is thorough").

A rubric check whose evidence this guide cannot locate is a check
nobody else can execute; the rubric swap showed you what that feels
like. Write the map you wish your grader had.
-->

## Environment

Where it lives: In an eval package, check the issue context for the environment the issue targets, then compare it with the environment record in the repro report. In live mode, compare the issue and repository documentation with the environment described in the draft repro comment.

What good looks like: The report identifies the relevant OS, runtime, dependency, application, or tool versions needed to understand the reproduction. Those details match the environment targeted by the issue, or any meaningful differences are clearly called out so a stranger can tell what environment was actually tested.

## Steps

Where it lives: In an eval package, check the reproduction steps in the repro report and use the issue context or repo-facts block to understand any required setup. In live mode, check the steps in the draft repro comment against the repository's setup instructions and the issue being reproduced.

What good looks like: The steps give a stranger enough information to start from the required state, perform the actions in the correct order, and reach the behavior being tested without guessing a missing essential action. Commands, inputs, configuration, or setup that materially affects the reproduction are included when needed.

## Behavior shown

Where it lives: In an eval package, check the output excerpts, logs, screenshots, error messages, or other artifacts in the repro report and compare them directly with the behavior described in the issue context. In live mode, compare the evidence included in or referenced by the draft repro comment with the behavior the GitHub issue says should occur.

What good looks like: The evidence visibly demonstrates the same behavior the issue describes, not merely a related error or adjacent problem. The artifact contains enough observable information to connect the reproduced result to the issue's specific symptom, output, or failure.

## Honesty

Where it lives: In an eval package, compare the conclusion and claims in the repro report with its steps, environment record, and artifacts. In live mode, compare what the draft repro comment says happened with the evidence the student actually collected.

What good looks like: The stated outcome matches the evidence. A successful reproduction is claimed only when the artifacts show the issue's behavior, and a failed or inconclusive attempt is reported as such. An honestly evidenced cannot-reproduce passes this check; unsupported certainty or claiming more than the evidence demonstrates does not.

## Comms

Where it lives: In an eval package, check the claim comment and repro report against the issue context, repo-facts block, and any repository contribution or communication requirements. In live mode, check the draft comments against the GitHub issue, repository contribution guidelines, issue templates, and any stated disclosure requirements.

What good looks like: The comments identify the specific issue and describe the work and result without generic boilerplate or unsupported claims. They follow repository-specific communication requirements, including required templates or AI-use disclosure policies when present. The claim promises an investigation and report rather than promising a fix or completion date.
