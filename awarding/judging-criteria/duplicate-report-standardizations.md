# Duplicate Report Standardizations

## Penalty / Award Standardization - Duplicate Report PoC Thoroughness

The lack of certain components has the following affect scoring:

The requisites of a full mark report are:
- Identification and demonstration of the root cause
- Identification and demonstration of the maximum achievable impact of the root cause

For a demonstration to be satisfactory, it can take the form of:

1) A step-by-step explanation from root cause to impact, with either attached code snippets or a coded POC.
2) At the judge’s discretion, a highly-standard issue can be accepted with less detail provided.

A lack of identification of the root cause is grounds for partial scoring, downgrading, or invalidating the issue.

A lack of identification of maximal impact is grounds for partial scoring or downgrading of the issue.

Additional factors that can be taken into account for partial scoring include:
- Quality of the submission in the form of writing or presentation quality
- Lack or incorrectness of the remediation steps

## Similar exploits under a single issue

Findings are duplicates if they share the same root cause.

More specifically, if fixing the Root Cause (in a reasonable manner) would cause the finding to no longer be exploitable, then the findings are duplicates.

Given the above, when similar exploits would demonstrate different impacts, the highest, most irreversible would be the one used for scoring the finding. Duplicates of the finding will be graded based on the achieved impact relative to the Submission Chosen for Report.

The above applies to duplicates from Bot Races, for which a rational fix has to be assumed.

