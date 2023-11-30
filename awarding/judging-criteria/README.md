# Judging criteria

## Submission Review Process

C4 strives to ensure a deliberate and transparent process for reviewing and judging submissions.

At the end of a given audit period, all reports will be reviewed and categorized based on these criteria. Pending sponsor review, final reports will be shared publicly on the [C4 Audit Report page](https://code4rena.com/reports). Audit results are shared on the C4 Discord and winners announced on the [C4 Twitter](https://twitter.com/code423n4).

Reports are also judged based on grammar, conciseness, and formatting.

## Best Current Practices

The [Code4rena org repo](https://github.com/code-423n4/org) documents open discussions and emergent best practices for judging C4 audits. Judges are encouraged to review [open issues in that repo](https://github.com/code-423n4/org/issues) regularly.

## Duplicate Submissions

Should multiple submissions describing the same vulnerability be submitted, Judges have the discretion to place these bugs into the same bucket, in which case, the award will be shared among those who submitted. However, multiple submissions from the same warden (or warden team), are treated as one by the awarding algorithm and do not split the pie into smaller pieces.

### Penalty / Award Standardization - Duplicate Report PoC Thoroughness

The lack of certain components has the following affect scoring:

The requisites of a full mark report are:
- Identification and demonstration of the root cause
- Identification and demonstration of the maximum achievable impact of the root cause

For a demonstration to be satisfactory, it can take the form of:

1. A step-by-step explanation from root cause to impact, with either attached code snippets or a coded POC.
2. At the judge’s discretion, a highly-standard issue can be accepted with less detail provided.

A lack of identification of the root cause is grounds for partial scoring, downgrading, or invalidating the issue.

A lack of identification of maximal impact is grounds for partial scoring or downgrading of the issue.

Additional factors that can be taken into account for partial scoring include:
- Quality of the submission in the form of writing or presentation quality
- Lack or incorrectness of the remediation steps

### Similar exploits under a single issue

Findings are duplicates if they share the same root cause.

More specifically, if fixing the Root Cause (in a reasonable manner) would cause the finding to no longer be exploitable, then the findings are duplicates.

Given the above, when similar exploits would demonstrate different impacts, the highest, most irreversible would be the one used for scoring the finding. Duplicates of the finding will be graded based on the achieved impact relative to the Submission Chosen for Report.

The above applies to duplicates from Bot Races, for which a rational fix has to be assumed.

## Scope

Each audit may include code that is explicitly in scope and out of scope, and specific issues which also may be identified as out of scope.

Wardens who adhere to the audit guidelines and report valid low/medium/high severity bugs which are not explicitly excluded from scope will earn a guaranteed payment.

Wardens _may_ elect to argue to bring things into scope—either by making the case that an issue poses a more urgent threat than identified or by submitting a medium or high severity finding in code which is out of scope. However, it is up to judges' absolute discretion whether to include these findings and award them, and these issues should include a clear argument as to why the items merit being brought into scope.

In the interest of everyone's time, **please do not offer QA or gas reports on any code or known issues which are identified as out of scope.**

## Acceptance of reports based on automated findings

Wardens and judges are recommended to read [the Supreme Court's verdict on this issue]((https://docs.code4rena.com/awarding/judging-criteria/supreme-court-decisions-fall-2023). 

## Scoring

The scoring system has three primary goals:

* Rewarding Wardens for finding unique bugs
* Hardening C4 code audits to Sybil attacks
* Encouraging coordination by incentivizing Wardens to form teams.

### Analysis

Analyses are judged A, B, or C, with C being unsatisfactory and ineligible for awards. The judge selects the best Analysis for inclusion in the audit report.

An analysis is a written submission outlining:

- Wardens' analysis of the codebase as a whole and any observations or advice they have about architecture, mechanism, or approach
- Broader concerns like systemic risks or centralization risks
- The approach taken in reviewing the code
- New insights and learnings from the audit

If individual findings are trees, Analyses are the forest. They provide wardens with an opportunity to contribute value through high level insights and advice that aren't necessarily covered by specific bugs -- and a way to get credit for doing so.

Each Analysis is judged based on quality and thoroughness as compared with other reports, with awards distributed on a curve. 

The Autumn 2023 Supreme Court session provided further judging guidelines for Analyses, saying they should provide "[actionable] insight on improvement steps of outlined characteristics." 

Areas of interest include:
- Full representation of the project’s risk model:
  - Admin abuse risks
  - Systemic risks
  - Technical risks
  - Integration risks
  - Non-standard token risks (if in scope)
- Software engineering considerations
- In-depth architecture assessment of business logic 
- Testing suite
- Weakspots and any single points of failure

Merely repeating the code functionality in pseudo-documentation is not considered valuable information.

### QA reports (low/non-critical)

QA reports are graded A, B, or C, with C being unsatisfactory and ineligible for awards. The judge selects the best QA report for inclusion in the audit report.

Low and non-critical findings must be submitted as a _single_ QA report per warden. We allocate a **fixed 2.5% of prize pools toward QA reports.**

QA reports should include:

* all low severity findings; and
* all non-critical findings.

Each QA report should be assessed based on report quality and thoroughness as compared with other reports, with awards distributed on a curve. 

Judges have discretion to assign a lower grade to wardens overstating the severity of QA issues (submitting low/non-critical issues as med/high in order to angle for higher payouts). Judges may also raise the severity of a QA finding at their discretion. 

### Gas reports

Gas reports are graded A, B, or C, with C being unsatisfactory and ineligible for awards. The judge selects the best Gas report for inclusion in the audit report.

Gas reports should be submitted using the **same approach as the QA reports:** a single submission per warden which includes all identified optimizations. The gas pool is allocated on a curve. 

The gas pool varies from audit to audit, but typically it consists of 2.5% of the total prize pool. The precise gas pool for each audit can be found in that audit's repo.

## Estimating Risk

See [Severity Categorization](https://docs.code4rena.com/awarding/judging-criteria/severity-categorization).
