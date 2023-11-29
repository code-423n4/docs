# Decisions from the innagural Supreme Court session, Fall 2023

## Judges

- [Alex The Entreprenerd](https://code4rena.com/@GalloDaSballo)
- [Trust](https://code4rena.com/@Trust)
- [LSDan](https://code4rena.com/@lsdan)


# Executive Summary
This document contains the verdicts as well as recommendations that the first C4 Supreme Court session has generated.

The issues are sorted by priority that the Supreme Court Member have determined, with 9 being the highest priority.

# 9s

## Recommendation: Appeal Committee

The following Process is suggested
With exact $ amounts being indicative of perceived price / value which should be derived in an analytical way

```	
- A panel of 3 judges RSVP on demand per contest. 
- One seat reserved for SC member at least initially
- Original judge cannot be part of panel
```
```
- Escalation costs $500 up front
- Escalation can only be submitted on issues surfaced in PJQA
```
```
- Overruling the Previous Verdict Requires 2/3 consensus
- If the Overruling is voted with a 3/3 consensus, then it’s labeled as a clear mistake
```
```
- In case of a clear mistake, the Judge pays court fee of $300 from earnings
- if mistake but not clear mistake, sponsor subsidizes court fee of $300, escalation fee returns to warden
- if the Appeal Committee agrees there was no mistake, the warden loses the escalation fee.
  Panel receives $300, judge receives $200
```
```
- C4 collects a 10 escalation deposit, $3k (isn't viewed as part of pot)
```
```
- Deposit is only reduced in case of a "mistake, not clear mistake" scenario. Unspent deposit is
  returned to sponsor (or the contest pot)
```
```
- In the event of over 10 escalations (extremely unlikely), only the first 10 escalations are
  guaranteed to be reviewed. Remaining escalations may be reviewed if they are not clear mistakes.
- The escalation shall be judged precisely with the information provided in the initial report and
  PJQA, no new evidence or elaboration will be accepted.
```

### Mechanism Analysis:
```
- Warden needs high degree of confidence to be incentivized to submit appeal
- Judge is held accountable for very clear mistakes, however they also stand to gain from abuse of appeals
- Panel members are paid $100 / ruling, which should be enough to get sufficient RSVPs
- Expenditure on side of sponsor is capped to a relatively low amount, and in effect will be mostly unused
- For C4 the mechanism is net zero so there's no exposure to volatility
```

### Post Judging QA additional Comments

**The ruling was already consultative**

We maintain that the suggested mechanics are likely to be adequate for all parties.

It is left to staff, who have much better insight on sponsor relations, to land on the best structure. 

We are cautious of penalizing wardens when their escalations are not unanimously accepted as that may create too strong a chilling effect for the escalation process.

We recommend staff to experiment over time to find an effective process that works for all parties


## Verdict: Severity Standardization - Centralization risks

Submissions would be separated into subcategories:
```
- Direct misuse of privileges shall be submitted in the Analysis report
- Reckless admin mistakes are invalid. Assume calls are previewed.
- Mistakes in code only unblocked through admin mistakes are QA-level
- Privilege escalation issues are judged by likelihood and impact and their severity is uncapped.
```

## Verdict: Severity standardization - Conditional on User Mistake

Findings that require the user to be careless or enter the wrong information into a contract call are QA or Invalid. 

Non privileged users are expected to preview their transactions to protect against input mistakes. Anyone using modern tooling will have previews built into their toolset.

Phishing attacks, and improper caution on using a protocol fall under this rule.

## Verdict: Unsupported fee-on-transfer tokens (and broader ERC20 discussion)

- Generally speaking, all non-standard ERC-20 token issues should be included in a dedicated part
  of the analysis writeup, not submitted as high, medium, or low risk issues. The exception is an
  actual threat to the functionality of the protocol or funds thereof. Judges should immediately 
  invalidate useless issues in this category.
- Regardless of the place of submission, out of scope issues should never be submitted. Doing so 
  is a waste of everyone’s time.
- Rather than treat EIP-20 as an authoritative document, we recognize that the commonly understood
  definition is the one stated here:
  https://ethereum.org/en/developers/docs/standards/tokens/erc-20/#body

- 🟢 <span style="background:yellow">Recommendation:</span> We recommend that C4 staff include the following list of common non-standard token types in the onboarding questionnaire, asking if the sponsor wishes to specifically exclude these tokens from the scope of the contest:
_We recognize these mechanisms as in-scope by default, and suggest that the sponsor manually opt-out of the following list, which we expect over time will change, based on common mechanisms being used_
```
  - Fee on Transfer
  - Rebasing / Elastic Supply
  - Streaming Token
  - Revert on Zero Value
  - Revert on Non-Zero to Non-Zero Approval
  - Doesn’t Revert on Failure
  - Blacklisting
  - Token upgradeability
  - Over 18 decimals
  - Pausability
  - Flash-mintable tokens
  - Callback tokens (ERC777)
  - non-bool returning tokens
```
- If a mechanism is out of scope but tokens with such mechanisms can be added permissionlessly AND
these would have effects on assets unrelated to the mechanism, those would still be treated in scope.

## Verdict: How to handle “post-game” judge re-assessments

No ruling changes are desirable.

### Recommendations:
We recommend improving the robustness of the PJQA stage through:

- An automatic changelog for judge verdicts
- A structured process to validate a request for review has been processed
- Exclusively for issues that were raised during the original PJQA timeline, a change or request for comments from the Judge allows an additional 24 hours of time for Wardens to raise additional concerns.

## Verdict: QA, Gas and Bot Race Judging

The decision is meant to confirm the direction that has been taken while maintaining sufficient leniency to allow consensus practices to emerge over time.

Reports will be judged via the following Rules:

1) An initial Qualitative Filtering Round will be conducted

&nbsp;&nbsp;&nbsp;&nbsp;Reports that distinguish themselves as:
```
  - Poorly Written
  - Generic
  - Low amount of findings
  - Overall with a High Noise to Signal Ratio (at the discretion of the Judge)
```  
&nbsp;&nbsp;&nbsp;&nbsp;Will be closed at this initial round and will not be manually judged

2) Score via algorithm for chosen reports

&nbsp;&nbsp;&nbsp;&nbsp;Reports will be scored based on their Findings
```
  - Each finding will be assigned a Category of Impact and a Bonus / Detraction score
```
3) Reports overall will be awarded a Bonus or a Detraction
4) The Judge will, at their discretion, adjust the Quantitative Results based on more subjective Qualitative Analysis with the Objective Function being giving as much value as possible to the Sponsor

### Recommendation:
For advisory output, we believe that these report categories are overly specialized for the lookout or judge role and should be delegated to new roles. As of now they take a vastly disproportionate amount of the judge’s time, which is best spent on the HM reports. In the absence of a specialized role, we recommend that the lookout’s role be allowed to close and invalidate low-quality gas and QA reports without input from the judge.

# 5-8s

## Recommendation: Proposition for collection and processing of judge performance

We advise to establish metrics that may assist in the assessment of judge performance. It is premature to discuss the interpretation of those metrics. When amounts are used, they should be interpreted as ratios of the total issue pool.
- number of PJQA review requests
- number of PJQA ruling changes
- number of accepted appeals
- Sponsor feedback
- Duration of the judging period

For Presorters, useful metrics are:
- Amount of Low Quality that are Partially Awarded or Closed by the Judge (True Positive)
- Amount of Duplicate findings that are undupped as Unique or as incorrect Duplicates by the Judge (False Positive)
- Amount of High Quality Reports that end up being Valid and/or Selected For Report (True Positive)

## Verdict: Penalty / Award Standardization - Duplicate Report PoC Thoroughness

We will address this as part of a clarification on the core criteria of submission and how lacking certain components would affect scoring.

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

## Recommendation: Standardize acceptance of reports based on automated findings

~~When the only prerequisite for a high or medium issue is a Bot Race finding, and fixing the relevant bot race finding in the most logical common way will cause the issue to no longer exist, the issue is invalid.~~

~~Interpreting this rule should be done in favor of the Sponsor as to avoid breaking the intention of this ruling.~~

### Post Judging QA additional Comments

**The ruling is changed to consultative**

After PJQA we agree that there are scenarios in which raising the severity of an OOS finding is very important to the Sponsor.

More specifically, it seems that the Agency of the Sponsor should have a high factor in determining whether a finding should be “escalatable” or not

We believe that duplicates that have the same severity as the known findings are clearly OOS in all scenarios (copy pasting a known issue is basically spam)

We believe that chaining OOS findings can be helpful in some scenarios

And that it can be considered spam in others.

Because we cannot determine a specific line, we believe that this Ruling should be changed to consultative

For Example:
- If the Sponsor ran 4nalyz3r and claimed all the findings as known
- Then escalating some severities by chaining would be in scope

However, the side effect of Bot Races is that the Sponsor has no agency in determining fixes for those findings, making it so that for some duplicates, raising severity would be useful, while other issues would never surface.

## Verdict: Severity for protocol does not work as intended

No agreement was reached on changing the rule definitions. The individual judges shall optionally provide an opinion on their view of the severity definitions.

See Appendix A

## Verdict: Similar exploits under a single issue
The findings are duplicates if they share the same root cause. 

More specifically, if fixing the Root Cause (in a reasonable manner) would cause the finding to no longer be exploitable, then the findings are duplicates.

Given the above, when similar exploits would demonstrate different impacts, the highest, most irreversible would be the one used for scoring the finding. Duplicates of the finding will be graded based on the achieved impact relative to the Submission Chosen for Report.

The above applies to duplicates from Bot Races, for which a rational fix has to be assumed.

## Verdict: Fault in out-of-scope library, impact in in-scope contract, to reward or not to reward

We would like to clarify the situation where an in-scope contract composes/inherits with an OOS contract, and the root cause exists in the OOS contract. In such cases, the finding is to be treated as OOS, while exceptional scenarios are at the discretion of the judge.

At the consultative level, we advise that the sponsor (not the scout) must be held responsible for the final list of files in scope (scope.txt). This would remove any gray areas around scope when contracts are interdependent. The Sponsor must understand that adding a file to scope.txt means it’s in scope, while the omission of a file means it’s out of scope, even if the file will be part of the deployed contracts.

## Verdict: There are little incentives to produce quality descriptions

No change of rules is necessary. Partial scoring addresses incentives adequately.

## Verdict: Severity standardization - speculation on future code

Any issue that is not exploitable within the scope of the contest is defined as speculating on future code. Any such speculation only has the potential to be valid if the root cause is demonstrated to be in the contest scope. Warden may make an argument on why a future code change that would make the bug manifest is reasonably likely. Based on likelihood considerations, the Judge may assign a severity rating in any way they see fit.

If the exploitability relies on a particular 3rd party integration, the likelihood must factor in a competent integrator who has done due diligence.

## Verdict: Using contract upgradability as a severity mitigation

Contract upgradability should never be used as a severity mitigation, i.e. we assume contracts are non-upgradable.

## Verdict: RFC - A case for or against admin privilege reports

This has been addressed through other verdicts.
See: Severity Standardization - Centralization risks

## Verdict: Problems with Libra Finance contest judging

The broader discussion of judging QA is addressed through other verdicts and consultative pieces.

## Recommendation: Adding 75% credit as an option

We recommend that a 75% option be added to the judging tool and grading algorithm.

## Verdict: Severity standardization - event-related impacts

A bug whose consequence is faulty emission of event(s) shall be graded in line with its broader-level impact:
- For events which are used for additional on-chain processes such as bridging, inclusion proofs etc., issue will be graded based on impacted functionality.
- Bugs that cause non-compliance with EIPs shall be graded based on EIP ruling guidelines
- Failure to demonstrate the broader level impacts above shall cap the severity to Low. For clarification, bugs leading to readability or accessibility of data, or issues of display in frontends, are capped to Low.

# 3s

## Contest retrospectives

Issue has not been addressed in this session.

## Judging of valid submissions without POC

Issue has been addressed in other verdicts.

## Verdict: Loss of Fees as Low

Loss of fees should be regarded as an impact similar to any other loss of capital:
- Loss of dust amounts are QA
- Loss of real amounts depends on specific conditions and likelihood considerations.

## Verdict: Loss of yield as high

Loss of **matured** yield should be regarded as an impact similar to any other loss of capital:
- Loss of dust amounts are QA
- Loss of real amounts depends on specific conditions and likelihood considerations.

Loss of **unmatured** yield or yield in motion shall be capped to medium severity.

## Verdict: Severity standardization - Protocol does not support CryptoPunks

- QA as Refactoring / Improvement
- Cannot be argued as a vulnerability

## Severity standardization - Contract upgradeability 

This issue is addressed as part of the more broad speculation of future code discussion.

## Severity standardization - Lack of two-step ownership transfers

See: Severity Standardization - Conditional on User Mistake

See: Severity Standardization - Centralization risks

## Verdict: Approve Race Condition - Suggested NC or Invalid
- We have long rejected the finding as anything above NC
- OZ has deprecated increaseAllowance and decreaseAllowance
- We officially confirm:
```
  - Approve and safeApprove front-run is NOT a valid vulnerability
  - Approve and safeApprove are NOT deprecated
  - increaseAllowance and decreaseAllowance ARE deprecated, although usage of those functions
    is not regarded as a bug report.
```

## Inconsistent severity for two-step change in governance

Has been addressed in other verdicts.

# New issues (late-submission spreadsheet):

| Title                                                                                          | URL                                          | Labels          | Prio | Alex | Dan | Trust      |
|------------------------------------------------------------------------------------------------|----------------------------------------------|-----------------|------|------|-----|------------|
| POC submitted during post judging QA or during judge period #122                               | https://github.com/code-423n4/org/issues/122 | Already done    |   -1 |   -1 |     |            |
| Rules about overinflated for severity #123                                                     | https://github.com/code-423n4/org/issues/123 | Rules           |    3 |    3 |     | Non answer |
| Disclose who is the judge before the contest #124                                              | https://github.com/code-423n4/org/issues/124 | Staff / Scam?   |   -1 |   -1 |     |            |
| Common issues willingly not included by bots during races #126                                 | https://github.com/code-423n4/org/issues/126 | Bots / Scam?    |    3 |    3 |     |            |
| Proposal - Penalties for invalid submissions #127                                              | https://github.com/code-423n4/org/issues/127 | Rules / Unclear |    3 |    3 |     |            |
| Proposal: Prevent overuse of "burden of proof" to increase objectivity of judging #128         | https://github.com/code-423n4/org/issues/128 | Vindication     |    1 |    1 |     |            |
| Proposal: Splitting the H/M rewards between QA and the bots in case no H/M has been found #129 | https://github.com/code-423n4/org/issues/129 | Bots / Scam?    |   -1 |   -1 |     |            |

## POC submitted during post-judging QA or during judge period 

Has been addressed in a separate ruling.

See: Standardization of additional warden output during QA

## Rules about overinflated for severity

We have determined it is in the best interest of C4 to not provide additional rules and guidelines around overinflation. It is left to the discretion of the judge.

## Disclose who is the judge before the contest

We do not advise changing this policy.

## Common issues willingly not included by bots during races

We do not believe regulatory action is necessary.

## Verdict: Proposal - Penalties for invalid submissions

Per-invalid penalties shall not be imposed on wardens. However, it is within the judge’s discretion to invalidate all of a warden’s findings in a particular contest in the case of repeated low-quality submissions.

## Proposal: Prevent overuse of "burden of proof" to increase the objectivity of judging

No change of ruling is necessary. When significant effort has been made by the warden, we advise judges to relate to the specific gap leading to the closing of submissions.

## Proposal: Splitting the H/M rewards between QA and the bots in case no H/M has been found

We advise against this motion. We suggest that once submissions are scored individually, the pot would only go to Low-severity finding, the highest grade of QA submissions highlighting a concrete mistake in the code with an impact below Medium.


# Court-initiated issues

## Verdict: Consensus Mechanism

We differentiate between the two possible outputs of the court.

For change or introduction of rulings, it shall be necessary to have a full 3/3 consensus due to the high impact of errors.

For consultative output, a 2/3 consensus is required. If there is a disagreement, consultation would be split into majority opinion and dissenting opinion.

## Verdict: Judging analysis submissions

Assessment can be viewed on two planes:
- Basic analysis - laying out the characteristics of the codebase, informational
- Expert analysis - insight on improvement steps of outlined characteristics, actionable

Areas of interest include:
- Full representation of the project’s risk model
```
  - Admin abuse risks
  - Systemic risks
  - Technical risks
  - Integration risks
  - Non-standard token risks (if in scope)
```
- Software engineering considerations
- In-depth architecture assessment of business logic 
- Testing suite
- Weakspots and any single points of failure

Merely repeating the code functionality in pseudo-documentation is not considered valuable information

## Recommendation: Conflict of Interests

We’ve discussed a variety of conflicts of interest situations in the Sponsor <> Judge <> Warden triangle. We recommend listing out known COI risks that almost by definition, cannot be effectively mitigated:
1) Warden/Judge is providing or has provided security services to Sponsor outside of C4
2) Warden has work relations or extra-curricular relations with Judge

It is recommended that whenever a Warden or Judge find themselves in a place of COI, they would voluntarily disclose the details of said COI. 

## Verdict: Standardization of additional warden output during QA

No new information should be introduced and considered in PJQA. Elaborations of the already introduced information can be considered (e.g. tweaking a POC), from either the Judge or the Warden, but they will only count towards the validity of the issue, not its quality score.

## Recommendation: Review of judge lifecycle

We identify some issues in the lifecycle. The granting of judge role should be a slower and tightly-controlled process. New judges must first prove themselves as lookouts. Once given the title, there should be a 2-3 contest period where they are closely reviewed by a SC judge, and only through scoring high grades should they establish their permanent status.

Overall the recommended period before judging is 3 to 6 months to ensure sufficient feedback was given.

Additionally, there should be tighter controls on existing judges and the concept of demotion into the lookout role should not be highly extraordinary. The implementation of these controls must be preceded by the development of a rating system for judges.

# Appendix

## Appendix A - Comments on Severity for protocol does not work as intended

The individual members of the Supreme Court share the following comments

### Alex’s View

Before discussions with the Supreme Court, I had prepared the following suggestion for amending the rules

![image](Alex notes.png)

This is an elaboration at the time of writing:

**3 — High:** Assets can be stolen/lost/compromised directly (or indirectly if there is a valid attack path that does not have hand-wavy hypotheticals) or the Protocol can be Halted or Substantially controlled by an attacker.

**2 — Med:**
- Assets not at direct risk, but the function of the protocol or its availability could be impacted, or leak value with a hypothetical attack path with stated assumptions, but external requirements. 
- An egregious mistake that doesn’t directly lead to loss of funds (ERCs / Incorrect View Logic, Missing function)
- Temporary DOS not being preventable under reasonable circumstances, with a duration above the intended “DOS mitigation path” if present.

**QA (Quality Assurance)** Includes both Non-critical (code style, clarity, syntax, versioning, off-chain monitoring (events, etc) and Low risk (e.g. assets are not at risk: state handling, function incorrect as to spec, issues with comments). Excludes Gas optimizations, which are submitted and judged separately.
Admin Privileges exploits and risks are to be sent as part of analyses.

### Trust’s view

The severity definitions have been molded and untouched since the very early days. Much has advanced in our understanding of bugs as well as the breadth of architectures that are being built. It’s my view that in an ever-shaping world, the severities should not be coupled to particular impacts or smart contract considerations. Instead they should define the logic-level requirements to unlock a particular severity. It should be viewed as a constitution and remain unchanged indefinitely. In parallel, specific impacts can and should be standardized as ruling clarifications, which are subject to ever-present debates and overrulings, if needed.

Below are the proposed definitions:

High - A **core** invariant of the protocol can be broken for an extended duration.

Medium - A **non-core** invariant of the protocol can be broken for an extended duration or at scale, or an otherwise high-severity issue is reduced due to hypotheticals or external factors affecting likelihood.

Low - A non-core invariant of the protocol can be broken with reduced likelihood or impact.

Refactor - A code or documentation flaw whose impact does not achieve Low severity
Informational - An issue without theoretical impact, a valuable best-practice

Note the detachment from smart contract terminology (DeFi in particular) and the focus on the classification of the invariant broken as core or non-core. Indeed every bug is ultimately the shattering of a set of assumptions (invariants), and categorizing the resulting gap in a highly abstract way makes for a highly future-proof set of definitions.

### Dan’s View

I’m generally of the opinion that the current definition is satisfactory enough to avoid confusion, however, I believe that the definition of asset could use some clarification. I suggest changing the current first line from:

Where **assets** refer to funds, NFTs, data, authorization, and any information intended to be private or confidential

To

Where **assets** refer to funds, NFTs, data, or any critical component of the protocol itself

## Appendix B - Artifacts

Prioritization Sheet
The following was used to discuss issues and prioritize them based on perceived importance
https://docs.google.com/spreadsheets/d/10d1qIqyEUCyGbgtm0Sf6mGldsMwNnoMIl-L1rBHqwho/edit?usp=sharing

## New Org Issues Prioritization Sheet

The following was used to discuss and prioritize new issues that were created while the Supreme Court was discussing
https://docs.google.com/spreadsheets/d/1dl5yk_FMG62Fvd77gmDNqitzK2uCTFVxZVcwgCDwk2o/edit?usp=sharing

