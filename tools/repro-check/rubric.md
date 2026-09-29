# Rubric: is this reproduction package ready to post?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever
checks you define here. It ships empty on purpose: the judgment is your
work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four
   columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where in the package. Name
     the part (the claim comment, the repro report's environment
     record, the artifacts read against the issue's description, the
     repo-facts block) or a location from your
     references/evidence-guide.md. "The report" is not a source; "the
     output excerpt read against the error the issue describes" is.
   - Pass condition: a decision rule about the OUTCOME that someone
     else could apply and get your answer. Judge the thing itself (does
     the artifact show the issue's behavior?), never the write-up's
     shape (how many steps it has, how long it is, whether it uses a
     template's headings). Structure-shaped checks are what make
     graders disagree with themselves.
   - Weight: `required` (a fail here holds the package) or `preferred`
     (never changes the verdict).

2. A verdict rule below the table: how the check grades combine into
   accept (ready) or reject (hold), including how `unclear` is
   treated. The verdict space is binary. If you write no rule for
   `unclear`, the skill treats it as fail.

Cover what actually gets bad packages posted. The lecture named the
proof families: the environment is recorded, the steps are complete
and followable, the behavior shown matches the issue (not an adjacent
one), the outcome is stated honestly (an evidenced cannot-reproduce is
a pass, a confident wrong-target is not), and the words respect the
repo's conventions. A rubric that ignores a family will fail eval
packages designed around that family.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Environment match | The repro report's environment record, read against the issue context and the Environment section of references/evidence-guide.md. | Pass if the environment identifies the relevant platform, runtime, dependency, application, or tool versions needed for the reproduction and they match the issue's target environment, or any meaningful differences are explicitly called out. | required |
| Followable steps | The reproduction steps in the repro report, read with any required setup in the issue context or repo-facts block and the Steps section of references/evidence-guide.md. | Pass if a stranger can start from the stated setup, perform the actions in order, and reach the tested behavior without guessing any essential command, input, configuration, or action. | required |
| Behavior match | The output excerpts, logs, screenshots, error messages, or other artifacts in the repro report, read against the behavior described in the issue context and the Behavior shown section of references/evidence-guide.md. | Pass if the evidence demonstrates the specific behavior described by the issue. Fail if the evidence shows only a related or adjacent problem without demonstrating the issue's actual symptom, output, or failure. | required |
| Honest outcome | The repro report's stated conclusion or outcome, read against its environment record, reproduction steps, artifacts, and the Honesty section of references/evidence-guide.md. | Pass if the stated outcome does not claim more than the evidence supports. A successful reproduction must be backed by evidence of the issue's behavior; an evidenced cannot-reproduce or inconclusive result also passes when reported accurately. | required |
| Repo conventions | The claim comment and repro report, read against the issue context, repo-facts block, repository contribution requirements, and the Comms section of references/evidence-guide.md. | Pass if the comments identify the specific issue, avoid unsupported promises, and follow any repository-specific communication requirements that apply, including required templates or AI-use disclosure. If the repository requires a disclosure and the comment omits it, fail. | required |

## Verdict rule

Accept only if every required check passes. Reject if any required check fails or is unclear. Preferred checks, if any are added later, may provide feedback but never change the final verdict. Treat unclear as fail because a package is not ready to post when the available evidence is insufficient to decide a required check.
