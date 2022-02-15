# Judging criteria

### Submission Review Process

C4 strives to ensure a deliberate and transparent process for reviewing and judging submissions.

At the end of a given contest period, all reports will be reviewed and categorized based on criteria. Pending sponsor review, final reports will be shared publicly on the [C4 Audit Report page](https://code4rena.com/reports). Contest results will then be shared on the C4 Discord and winners will be announced on the [C4 Twitter](https://twitter.com/code423n4).

Reports are also judged based on grammar, conciseness, and formatting.

### Duplicate Submissions

Should multiple submissions describing the same vulnerability be submitted, Judges have the discretion to place these bugs into the same bucket, in which case, the award will be shared among those who submitted. However, multiple submissions from the same warden (or warden team), are treated as one by the awarding algorithm and do not split the pie into smaller pieces.

### Scoring

The scoring system has three primary goals:

* Rewarding Wardens for finding unique bugs
* Hardening C4 code contests to Sybil attacks
* Encouraging coordination by incentivizing Wardens to form teams.

### QA reports (low/non-critical)

For contests starting on or after February 3, 2022, low and non-critical findings should be submitted as a *single* QA report per warden. We are allocating a **fixed 10% of prize pools toward QA reports.**

Your QA report should include:

- a summary statement with observations on the codebase as a whole and opportunities for improved security practices;

- all low severity findings; and

- all non-critical findings.

Each QA report will be assessed based on report quality and thoroughness as compared with other reports, with awards distributed on a curve. The top QA report author will have their work included and cited in the final C4 report and receive the top prize from the category.

Wardens overstating the severity of QA issues (submitting low/non-critical issues as med/high in order to angle for higher payouts) will have their scores reduced by judges.

In the unlikely event that zero high- or medium-risk vulnerabilities are found, the full pool will be divided based on the QA Report curve.

### Gas reports

Gas reports should be submitted using the **same approach as the QA reports:** a single submission per warden which includes all identified optimizations. The gas pool will be allocated on a curve, and the top reporter’s work included in the C4 report. 

The gas pool varies from contest to contest, but typically it consists of 5% of the total prize pool. The precise gas pool for each contest can be found in that contest's repo.

## High-Level Considerations

### Malicious input handling

Does reported bug affect the abilities of function parameters to be passed in a safe and predictable manner?

### Arithmetic

Does reported bug affect mathematical operations or influence the contract’s ability to handle variable values in a predictable and safe manner?

### Gas Limitations

Does reported bug affect the use of gas? If so, is gas handled in a suboptimal manner, could this result in unnecessary losses?

## Estimating Risk tl;dr

Where **assets** refer to funds, NFTs, data, authorization, and any information intended to be private or confidential:

* **0 — Non-critical:** Code style, clarity, syntax, versioning, off-chain monitoring (events etc), exclude gas-optimisations.
* **1 — Low:** Low: Assets are not at risk. State handling, function incorrect as to spec, issues with comments.
* **2 — Med:** Assets not at direct risk, but the function of the protocol or its availability could be impacted, or leak value with a hypothetical attack path with stated assumptions, but external requirements.
* **3 — High:** Assets can be stolen/lost/compromised directly (or indirectly if there is a valid attack path that does not have hand-wavy hypotheticals).

## Estimating Risk

C4 Judges refer to the standard model as presented in the OWASP approach to risk analysis where:

`Risk = Likelihood * Impact`

The Warden’s submission should include:

* Proposed risk classification
* Threat agent involved
* Attack method(s) used
* Vulnerabilities involved
* Speculated impact of a successful exploit

The measurement of risk will be partially based on the rating submitted by the Warden, but is also subject to the judge’s best discretion. Should the judge determine a particular bug to be a lower risk than the Warden rated, this judgement will include a reason justifying the downgraded measurement.

### Risk Categories

Bugs are divided into 3 risk categories:

* Low
* Medium
* High

## Estimating Likelihood

The first set of factors are related to the threat agent involved. The goal here is to estimate the likelihood of a successful attack by this group of threat agents. Use the worst-case threat agent.

### Skill level

How technically skilled is this group of threat agents?

* No technical skills **(1)**
* Some technical skills **(3)**
* Advanced computer user **(5)**
* Network and programming skills **(6)**
* Security penetration skills **(9)**

### Motive

How motivated is this group of threat agents to find and exploit this vulnerability?

* Low or no reward **(1)**
* Possible reward **(4)**
* High reward **(9)**

### Opportunity

What resources and opportunities are required for this group of threat agents to find and exploit this vulnerability?

* Full access or expensive resources required **(0)**
* Special access or resources required **(4)**
* Some access or resources required **(7)**
* No access or resources required **(9)**

How large is this group of threat agents?

* [Uninformed users](https://medium.com/cybermiles/i-accidentally-killed-it-and-evaporated-300-million-6b975dc1f76b) **(4)**
* Partners **(5)**
* Authenticated users **(6)**
* Anonymous Internet users **(9)**

## Estimating Vulnerability

The next set of factors are related to the vulnerability involved. The goal here is to estimate the likelihood of the particular vulnerability involved being discovered and exploited. Assume the threat agent selected above.

### Ease of discovery

How easy is it for this group of threat agents to discover this vulnerability?

* Practically impossible **(1)**
* Difficult **(3)**
* Easy **(7)**
* Automated tools available **(9)**

### Ease of exploit

How easy is it for this group of threat agents to actually exploit this vulnerability?

* Theoretical **(1)**
* Difficult **(3)**
* Easy **(5)**
* Automated tools available **(9)**

### Awareness

How well known is this vulnerability to this group of threat agents?

* Unknown **(1)**
* Hidden **(4)**
* Obvious **(6)**
* Public knowledge **(9)**

## Estimating Impact

The goal is to estimate the magnitude of the impact on the system if the vulnerability were to be exploited.

### Loss of funds

Can funds be transferred without the knowledge of the owner?

* This is a critical bug with that warrants the highest rating **(9)**.

### Loss of availability

To what degree can this prevent an application from performing and how vital is it?

* Minimal secondary services interrupted **(1)**
* Minimal primary services interrupted **(5)**
* Extensive secondary services interrupted **(5)**
* Extensive primary services interrupted **(7)**
* All services completely lost **(9)**

### Credits

The C4 judging criteria references the [OWASP Risk Rating Methodology](https://owasp.org/www-community/OWASP\_Risk\_Rating\_Methodology) to score the severity and relevance of submitted reports from C4 Wardens.
