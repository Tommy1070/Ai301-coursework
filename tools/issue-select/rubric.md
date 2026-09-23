# Rubric: is this a good first issue?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever checks
you define here. It ships empty on purpose: the judgment is your work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where. Name the source
     (repo-facts block, issue body, comment thread, or the locations in
     references/evidence-guide.md). "The repo" is not a source; "the last
     5 default-branch commit dates" is.
   - Pass condition: a condition someone else could apply and get your
     answer. Prefer thresholds with numbers ("a maintainer commented
     within 30 days") over adjectives ("maintainer is responsive").
   - Weight: `required` (a fail here rejects the issue) or `preferred`
     (never changes the verdict; a nice-to-have that helps rank the
     issues you accept).

2. A verdict rule below the table: how the check grades combine into
   accept or reject, including how `unclear` is treated. The verdict
   space is binary. If you write no rule for `unclear`, the skill treats
   it as fail.

Cover what actually kills first contributions. The lecture named four
families: the maintainer is alive, the repo is in use, the scope fits a
newcomer, and nobody else is already on it. A rubric that ignores a family
will fail eval issues designed around that family.

## Checks

|Check|Evidence|Pass condition|Weight|
|-|-|-|-|
| Maintainer activit|Repo facts: last 5 default-branch commits, commit authors, and maintainer first-response sample; issue Comments author\_association|Pass if there is at least one human-authored default-branch commit within 90 days of the capture date, OR the maintainer first-response sample shows an Owner, Member, or Collaborator response within 30 days. Bot-only commits do not satisfy this check unless the bot commit merged a human PR. |required |
|Repository in use| Repo facts: archived flag, latest release, and last push to any branch| Pass if the repository is not archived AND either the latest release or last push is within 180 days of the capture date.|required |
|Newcomer-sized scope \||Issue body and Comments section|Pass unless the issue is explicitly an umbrella/tracking issue whose sub-items are meant to be separate contributions, a pure usage/support question, an unsettled design discussion with no maintainer decision, or work that a maintainer explicitly says requires changes to core internals. Multiple concrete edits serving one outcome, technical complexity, a terse description, or missing reproduction steps do not by themselves cause failure.|required |
|Work availability|Repo facts: this issue assignees and linked PRs; Comments section for PR mentions and active claim statements|Pass if the issue has no current assignee and no open linked or comment-mentioned PR actively implementing the issue. One closed unmerged PR is an abandoned attempt rather than an active claim, but several abandoned claim or closed-unmerged-PR attempts indicate the issue is not suitable as a first contribution and fail this check.|required |
|AI contribution policy |Repo facts: contribution policy, including CONTRIBUTING.md, dedicated AI policy files, and relevant templates|Pass unless the contribution policy explicitly bans AI-generated or AI-assisted contributions. Disclosure, testing, personal-understanding, or human-review requirements pass, and silence passes|required |
| Human-authored issue|Issue opener|Pass if the issue was opened by a human contributor or maintainer. Fail if the issue opener is explicitly identified as a bot account such as an author ending in \[bot]|required |

## Verdict rule



Accept if every required check passes. Reject if any required check fails. Treat unclear evidence on a required check as a failure. Preferred checks never change the accept/reject verdict; they are used only to rank accepted issues.

