# Judging criteria

### Submission Review Process

C4 strives to ensure a deliberate and transparent process for reviewing and judging submissions.

At the end of a given audit period, all reports will be reviewed and categorized based on these criteria. Pending sponsor review, final reports will be shared publicly on the [C4 Audit Report page](https://code4rena.com/reports). Audit results are shared on the C4 Discord and winners announced on the [C4 Twitter](https://twitter.com/code423n4).

Reports are also judged based on grammar, conciseness, and formatting.

### Best Current Practices

The [Code4rena org repo](https://github.com/code-423n4/org) documents open discussions and emergent best practices for judging C4 audits. Judges are encouraged to review [open issues in that repo](https://github.com/code-423n4/org/issues) regularly.

### Duplicate Submissions

Should multiple submissions describing the same vulnerability be submitted, Judges have the discretion to place these bugs into the same bucket, in which case, the award will be shared among those who submitted. However, multiple submissions from the same warden (or warden team), are treated as one by the awarding algorithm and do not split the pie into smaller pieces.

### Scope

Each audit may include code that is explicitly in scope and out of scope, and specific issues which also may be identified as out of scope.

Wardens who adhere to the audit guidelines and report valid low/medium/high severity bugs which are not explicitly excluded from scope will earn a guaranteed payment.

Wardens _may_ elect to argue to bring things into scope—either by making the case that an issue poses a more urgent threat than identified or by submitting a medium or high severity finding in code which is out of scope. However, it is up to judges' absolute discretion whether to include these findings and award them, and these issues should include a clear argument as to why the items merit being brought into scope.

In the interest of everyone's time, **please do not offer QA or gas reports on any code or known issues which are identified as out of scope.**

### Scoring

The scoring system has three primary goals:

* Rewarding Wardens for finding unique bugs
* Hardening C4 code audits to Sybil attacks
* Encouraging coordination by incentivizing Wardens to form teams.

### Analysis

An analysis is a written submission outlining:

- Wardens' analysis of the codebase as a whole and any observations or advice they have about architecture, mechanism, or approach
- Broader concerns like systemic risks or centralization risks
- The approach taken in reviewing the code
- New insights and learnings from the audit

If individual findings are trees, Analyses are the forest. They provide wardens with an opportunity to contribute value through high level insights and advice that aren't necessarily covered by specific bugs -- and a way to get credit for doing so.

Analyses are judged A/B/C, with the top Analysis selected for inclusion in the audit report, similarly to Gas and QA reports.

### QA reports (low/non-critical)

Low and non-critical findings must be submitted as a _single_ QA report per warden. We allocate a **fixed 10% of prize pools toward QA reports.**

Your QA report should include:

* all low severity findings; and
* all non-critical findings.

Each QA report will be assessed based on report quality and thoroughness as compared with other reports, with awards distributed on a curve. The top QA report author will receive the top prize from the category.

Wardens overstating the severity of QA issues (submitting low/non-critical issues as med/high in order to angle for higher payouts) will have their scores reduced by judges.

In the unlikely event that zero high- or medium-risk vulnerabilities are found, the full pool will be divided based on the QA Report curve.

### Gas reports

Gas reports should be submitted using the **same approach as the QA reports:** a single submission per warden which includes all identified optimizations. The gas pool will be allocated on a curve, and the top reporter will receive the top prize in the category.

The gas pool varies from audit to audit, but typically it consists of 2.5% of the total prize pool. The precise gas pool for each audit can be found in that audit's repo.

## Estimating Risk

See [Severity Categorization](https://docs.code4rena.com/awarding/judging-criteria/severity-categorization).
