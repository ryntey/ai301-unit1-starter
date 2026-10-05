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
-->
## Checks

All dates are measured against the bundle's capture date (eval mode) or today (live mode).

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| active-repo | "archived:" on the repo line and the last 5 default-branch commit dates (Repo facts) | The repo is not archived AND the newest of the last 5 default-branch commits is within 12 months of the capture date | required |
| unclaimed | "this issue: assignees" and "linked PRs" (Repo facts), plus every PR mentioned in the comment thread | No assignee; no linked or mentioned PR is open; and no non-maintainer has posted a claim ("I'll take this", "working on this", "can I work on this") within 6 months of the capture date. Older claims with no open PR are stale and do not count | required |
| bounded-scope | Issue title and body, labels, opener's author_association, the comment thread, and closed-unmerged linked PRs | Fails if ANY of: (a) the issue is an umbrella / tracking / meta issue listing sub-tasks to split into separate PRs; (b) the thread shows the design is still being debated and no maintainer (OWNER/MEMBER/COLLABORATOR) has settled it; (c) 2 or more linked PRs are closed without merging; (d) it is a feature request that was not opened by a maintainer, carries no labels, and no maintainer has commented approving it; (e) it is a usage/support question. Otherwise pass. A short body or missing repro steps is NOT a fail | required |
| ai-policy | "contribution policy" line (Repo facts) | Fails only if the policy bans AI-generated code or documentation outright. Conditions (disclose, review, understand, test AI output) pass. No stated policy passes | required |
| maintainer-alive | "maintainer first-response sample" (Repo facts) and author_association of commenters in the thread | A maintainer (OWNER/MEMBER/COLLABORATOR) replied to an issue within 30 days in the sample, or commented in this thread within 150 days of the capture date | preferred |
| gfi-label | Issue labels | Has a "good first issue", "help wanted", or "easy" label | preferred |

## Verdict rule

Accept if every required check passes. Reject if any required check fails. An `unclear` grade on a required check counts as fail. Preferred checks never change the verdict; they only rank issues that are already accepted.

<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict, they
rank accepted issues; unclear counts as fail." -->
