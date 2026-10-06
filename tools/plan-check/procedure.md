# Procedure: how this skill grades a plan package

<!--
THIS IS THE PART YOU WRITE, and it is a new kind of part. Weeks 1 and
2, SKILL.md carried a numbered workflow and you only wrote judgment
files. This week the workflow is gone from the frame: SKILL.md says
"execute procedure.md", and these are the operating steps you author.
The machinery is in your hands now.

Your operator swap is the design brief. When your executor stalled
because your rubric said WHAT to decide but not HOW to find the
evidence, that was a procedure gap. This file is where those gaps get
closed: a complete procedure lets someone who has never seen a plan
package before (a groupmate, or the skill itself) grade one exactly the
way you would.

Under each stage heading below, write the concrete steps for that
stage. The one-line note under each heading says what a complete
procedure must decide there. Write steps, not intentions: "read the
repro evidence before the plan, and note what behavior it pins down"
is a step; "understand the context" is a wish.
-->

## Read order

1. Read the issue/thread context first and note the reported behavior, expected behavior, and any repository or maintainer constraints.
2. Read the reproduction evidence next and record the exact reproduced failure, commands or steps used, and observed output. Treat this as the factual baseline for judging the diagnosis and test plan.
3. Read the repo-facts block and note the relevant files, functions, tests, and repository conventions that constrain the implementation.
4. Read the proposed plan and draft comment last. Compare their diagnosis, scope, approach, test plan, risks, and claims against the evidence already recorded rather than accepting the plan's claims at face value.

## Evidence gathering

1. From the issue/thread, record the reported and expected behavior plus any maintainer instructions or repository conventions relevant to the proposed change.
2. From the repro evidence, record the reproduced command or steps, the exact observable failure, and any evidence that identifies where or why the failure occurs.
3. From the repo-facts block, record the files, functions, tests, and conventions relevant to implementing and validating the fix.
4. From the plan, record the stated diagnosis, files to change, implementation approach, explicit in-scope and out-of-scope boundaries, test plan, and risks or unknowns.
5. From the draft comment, record what it tells maintainers about the diagnosis, proposed change, validation, and any unresolved uncertainty.

## Check execution

1. Grade the required checks in rubric order: diagnosis, scope, test plan, approach, risks and unknowns, then plan comment.
2. For each check, compare only the gathered evidence named by that rubric row against its pass condition.
3. Mark a check pass only when the evidence clearly satisfies the pass condition. Mark it fail when the evidence clearly contradicts or fails the condition. Mark it unclear when required evidence is genuinely missing or insufficient to decide.
4. Do not assume missing facts or repair the plan with outside knowledge. Once the evidence needed for a check has been gathered, grade from those notes without re-reading unrelated parts of the package.

## Verdict assembly

1. Collect the grade for every rubric check after all checks have been executed.
2. Apply the rubric verdict rule exactly: accept only if every required check passes. Any required check graded fail or unclear makes the final verdict reject. Preferred checks never change the verdict.
3. For a reject verdict, identify the first required check in rubric order that failed or was unclear and quote the smallest relevant evidence excerpt that explains the decision.
4. For an accept verdict, report that all required checks passed and include concise evidence supporting the required checks without inventing facts beyond the package.
