# Judging criteria

C4 strives to ensure a deliberate and transparent process for reviewing and judging submissions.

C4's judging and awarding system has three primary goals:

* Rewarding Wardens for finding unique vulnerabilities
* Hardening C4 audits to Sybil attacks
* Encouraging coordination by incentivizing Wardens to form teams.

## Submission review process

See ["How competitive audits work"](/competitions#how-competitive-audits-work).

## Understanding judge evaluations

While input from Sponsors and the Validator is carefully considered, Judges have final say in determining validity and severity of issues, as well as whether/how issues are considered duplicates. 

During the judging phase, judges make the following assessments: 

- [Validity](#validity)
- [Quality](#quality) 
- [Full/partial credit](#partial-credit-duplicates-standards-for-fullpartial-credit)
- [Severity](#severityrisk)
- Selection of [primary submission](/awarding#bonus-for-best--selected-for-report) within duplicate sets ("findings")

A submission must be judged as both valid *and* sufficient quality to be eligible for awards. 

## Validity

Judges assess each submissions' validity as `valid`, `invalid`, or `out of scope`.

Validity is evaluated according to the following guidelines:

- [Burden of proof](/competitions/submission-guidelines.md#burden-of-proof)
- [Fairness and validity](/competitions/fairness-and-validity.md)
- [Good citizenship](/competitions/submission-guidelines.md#good-citizenship-is-a-requirement-for-compensation)
- [Scope](#scope)

## Severity/Risk

See [Severity Categorization](/competitions/severity-categorization.md).

## Quality

Judges assess each submissions' validity as `sufficient`, `insufficient`, or `low quality/spam`.

Any submissions deemed insufficient or low quality are ineligible for awards, and count against wardens' [signal](/roles/signal.md) scores.

The bar for sufficient quality submissions is that they are roughly at a level that could be found in a draft report by a professional auditor: specifically on the merits of technical substance, with writing quality considered only where it interferes with comprehension of the technical message.

It is possible for a submission to be *technically* valid and still insufficient. An insufficient quality submission may meet any of these criteria:

- incorrect
- low/incomplete effort
- clearly overinflated severity
- proof of concept does not pass the burden of proof test
- approach is disrespectful of sponsors’ and judges’ time in some way

Any submissions that appear to be direct copies of other reports in the current audit will be collectively deemed insufficient.

Submissions are also judged based on grammar, conciseness, and formatting.

## Scope

Each audit may include code that is explicitly in scope and out of scope, and specific issues which also may be identified as out of scope.

Wardens who adhere to the audit guidelines and submit valid medium/high severity vulnerabilities which are not explicitly excluded from scope will earn a guaranteed payment.

Wardens _may_ elect to argue to bring things into scope—either by making the case that an issue poses a more urgent threat than identified or by submitting a medium or high severity vulnerability in code which is out of scope. However, it is up to judges' absolute discretion whether to include these findings and award them, and these issues should include a clear argument as to why the items merit being brought into scope.

In the interest of everyone's time, **QA reports should not include findings relating to any code or known issues which are identified as out of scope.**

## Duplicate submissions

Should multiple submissions describing the same vulnerability be submitted, Judges have the discretion to place these submissions into the same finding (duplicate group), in which case, the award will be shared among those who submitted. Note that multiple submissions from the same warden (or warden team) are treated as one by the awarding algorithm, and do not split the award into smaller pieces.

### Similar exploits under a single issue

Findings are duplicates if they share the same root cause.

More specifically, if fixing the Root Cause (in a reasonable manner) would cause the finding to no longer be exploitable, then the findings are duplicates.

Given the above, when similar exploits would demonstrate different impacts, the highest, most irreversible would be the one used for scoring the finding. Duplicates of the finding will be graded based on the achieved impact relative to the submission selected for inclusion in the report.

### Partial credit duplicates: standards for full/partial credit

The requisites of a full mark submission are:
- Identification and demonstration of the root cause
- Identification and demonstration of the maximum achievable impact of the root cause

For a demonstration to be satisfactory, it can take the form of:

1. A step-by-step explanation from root cause to impact, with either attached code snippets or a coded PoC.
2. At the judge’s discretion, a high-standard issue can be accepted with less detail provided.

A lack of identification of the root cause is grounds for partial scoring, downgrading, or invalidating the issue.

A lack of identification of maximal impact is grounds for partial scoring or downgrading of the issue.

Additional factors that can be taken into account for partial scoring include:
- Quality of the submission in the form of writing or presentation quality
- Lack or incorrectness of the remediation steps

## Findings published in prior audit reports

Findings from previous audit reports listed in the audit repo `README` should generally be considered as known issues and therefore out of scope, especially if they were evaluated as acknowledged/wontfix by the sponsor. 
 
- If the finding was confirmed, and can be reasonably expected to have been mitigated prior to the sponsor's Code4rena audit, then the judge may assess it as a valid finding since the vulnerability has persisted. 
- If the submission demonstrates a substantively distinct or higher-severity attack path, the judge may deem it to be valid.

Judges should use their discretion to assess whether the submission a) provides value to the customer, and/or b) would be irresponsible to exclude from the Code4rena audit report. 

## QA reports (Low risk and Governance/Centralization risk)

Low risk and Governance/Centralization risk findings must be submitted as a _single_ QA report per warden. 

QA reports should include:

* all low severity findings; and
* all governance/centralization risk findings.

Each QA report is assessed based on report quality and thoroughness as compared with other reports, with awards distributed on a curve. 

Judges have discretion to assign a lower grade to wardens overstating the severity of QA issues (submitting low/non-critical issues as med/high in order to angle for higher payouts). 