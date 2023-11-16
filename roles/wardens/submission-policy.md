# Submission policy

Code4rena is an open organization committed to improving the security of decentralized protocols while protecting the information of our sponsors and participants. This policy is intended to provide C4 Wardens (security researchers) clear guidelines for participating in code audits while conducting vulnerability discovery activities.

The following policy conveys C4’s preferences in how to submit discovered vulnerabilities to the organization and describes what systems and types of research are covered under this policy, how to share vulnerability reports, and the length of time we expect Wardens to wait prior to publicly disclosing vulnerabilities.

Reports can be submitted at any point prior to stop time for a given audit. The details for each code audit can be found through [the Code4rena website](https://code4rena.com/).

All community members agree to be bound by the Code4rena Code of Conduct, which can be viewed [in the Code4rena Discord](https://discord.com/channels/810916927919620096/851883682470166558/851891396255940618). 

## Audit contest guidelines

Under this policy, audit contests covers activities in which you:

* Register as a C4 Warden within an individual capacity or as part of a team.
* Submit your bug report using the submission form.
* Make every effort to avoid privacy violations, degradation of user experience, disruption to production systems, and destruction or manipulation of data, especially in regard to funds.
* Only use exploits to the extent necessary to confirm a vulnerability’s presence. Do not use an exploit to compromise funds, exfiltrate data, establish persistent permissioning access, or use the exploit to redirect to other systems.
* Unless explicitly noted by the affiliated sponsor, **wait until the audit report has been published** before you disclose any findings or submissions publicly. 
* Do not submit a high volume of low-quality reports.

In the event that you encounter a critical vulnerability that the sponsor project would want to know about, even before the end of the audit, please refer to ["How to submit Zero-day or otherwise highly sensitive bugs."](#how-to-submit-zero-day-or-otherwise-highly-sensitive-bugs)

> Without explicit permission from sponsors, publishing or discussing findings publicly prior to report publication is grounds for immediate forfeit of award and disqualification from any future C4 events and activities.

## Submitting a report

C4 accepts vulnerability reports via the audit submission form.

In order to help us triage and prioritize submissions, please ensure that your reports:

* Are submitted no later than the audit stop time.
* Use the audit submission process.
* Follow the correct report format. (See next section.)
* Describe the location the vulnerability was discovered and the potential impact of exploitation.
* Offer a detailed description of the steps needed to reproduce the vulnerability (proof of concept scripts or screenshots are helpful).
* Have not been surfaced as "known issues" (see audit repo `README` for details).
* Are written in English, if possible.

It is also recommended to ensure you receive email confirmation of each submission. (If you do not see an email confirmation, please check your spam folder.)

### Submission types

- **High, Medium, and QA reports:** 
  - Wardens should [review Code4rena's severity categorization](https://docs.code4rena.com/awarding/judging-criteria/severity-categorization) prior to submitting vulnerabilities, and select the appropriate risk when submitting.
  - Medium or High severity findings should be submitted individually.
  - All QA findings (Low risk or Non-critical) must be submitted as a single QA report per warden (or team).
  - Centralization risks, systemic risks, and architecture recommendations should be submitted as part of an Analysis (see below).
- **Analyses:** An analysis is a written submission outlining:
  - Wardens' analysis of the codebase as a whole and any observations or advice they have about architecture, mechanism, or approach
  - Broader concerns like systemic risks or centralization risks
  - The approach taken in reviewing the code
  - New insights and learnings from the audit
- **Gas optimizations:** All identified gas optimizations should be submitted as a separate report. *Note:* the gas award pool is set according to the sponsor's preference, and some audits do not include gas optimizations awards.


### Report formats
- Medium or High severity findings should be submitted individually.
- Analyses should be submitted via the "Submit Analysis report" form.
- All QA findings (Low risk or Non-critical) must be submitted within a single QA report per warden (or team). 
- All Gas optimizations must be submitted within a single Gas report per warden (or team).

Wardens who submit multiple QA and/or Gas findings to a single audit without following the required format will have all QA/Gas submissions invalidated for that audit. 

### Analyses

An analysis allows wardens to provide a high-level architectural review and codebase analysis as well as recommendations — and to win a slice of the pool based on their insights and advice.

The Analysis submission form includes a set of questions for you to answer to the best of your ability: 

1. Analysis of the codebase (What's unique? What's using existing patterns?)
2. Architecture feedback
3. Centralization risks
4. Systemic risks
5. Other recommendations
6. How much time did you spend?

### QA reports (low/non-critical)

Low and non-critical findings must be submitted as a _single_ QA report per warden. We allocate a **fixed 2.5% of prize pools toward QA reports.**

Your QA report should include:

* all low severity findings; and
* all non-critical findings.

Each QA report will be assessed based on report quality and thoroughness as compared with other reports, with awards distributed on a curve. The top QA report author will receive the top prize from the category.

Wardens overstating the severity of QA issues (submitting low/non-critical issues as med/high in order to angle for higher payouts) will have their scores reduced by judges.

In the unlikely event that zero high- or medium-risk vulnerabilities are found, the full pool will be divided based on the QA Report curve.

### Gas reports

Gas reports should be submitted using the **same approach as the QA reports:** a single submission per warden which includes all identified optimizations. The gas pool will be allocated on a curve, and the top reporter will receive the top prize in the category.

The gas pool varies from audit to audit, but typically it consists of 2.5% of the total prize pool. The precise gas pool for each audit can be found in that audit's repo.


For more details on QA and Gas reports, and estimating risk, please see [Judging Criteria](https://docs.code4rena.com/roles/wardens/judging-criteria#qa-reports-low-non-critical).

### Burden of proof

Wardens have the burden of proof in submissions. Explaining and rationalizing the potential impact is an essential part of a quality submission. The burden of proof increases based on the potential value of the submission (rarity, severity).

Insufficient proof shall be defined as the judge needing to do additional research or coding in order to validate the claims made in the submission. Therefore it is recommended to have a coded proof of concept for high severity findings in order to make it easy for a judge to validate your case.

Submissions which judges deem insufficiently proven will not be eligible for anything higher than a satisfactory score.

### How to include a proof of concept

To include a proof of concept (PoC) link in your submission, please follow these steps, to ensure that your PoC remains private for the duration of the audit, but can be accessed publicly after the findings are made public:

1. Modify existing test files
2. Provide the diff ([instructions](https://gist.github.com/IllIllI000/21deaa6a55c95a6ec9ca893009ee494f)), which can be applied

### Late submissions

C4 does not accept late submissions under any circumstances; the audit deadlines are firm. We recommend that you submit your findings at least a few minutes before the cut-off time, since the submission form can become slow or unresponsive in the final minutes of an audit, due to high traffic.

### Submissions to the wrong audit

C4 cannot "transfer" your submission to another audit after the audit ends. If you discover that you have accidentally submitted a finding to the wrong audit, please re-submit it to the correct audit, and then follow the steps below to withdraw your report from the other audit.

### How to submit Zero-day or otherwise highly sensitive bugs

If you discover a highly sensitive bug, e.g. a high-severity vulnerability affecting deployed contracts, please follow these steps: 

1. Submit a placeholder finding using the audit submission form, with a non-specific title (e.g. "Potentially sensitive issue - disclosed privately")
1. While logged in to the Code4rena website, [submit a Help Desk request](https://code4rena.com/help/), and select "Sensitive disclosure" for "What type of problem do you need help with?" Please include: 
   - Name of audit, and 
   - Link to a private Gist containing the finding.

Code4rena staff will review the issue immediately with the judge and sponsor, and will ensure the submission is added to the audit repo after any immediate risks have been addressed. 

### Findings in "parent" of forked projects

If an issue is discovered during an audit that relates to the "parent" of a forked project, wardens should disclose the finding to the parent project first, and submit a placeholder finding to the C4 audit. Please follow these steps: 

1. Submit a placeholder finding using the audit submission form, with a non-specific title (e.g. "Potentially sensitive issue")
   - **Do not** disclose the parent / third party name within the body of the finding issue.
   - **Do** include a hash of the issue
1. While logged in to the Code4rena website, [submit a Help Desk request](https://code4rena.com/help/), and select "Sensitive disclosure" for "What type of problem do you need help with?" Please include: 
   - Name of audit, and
   - Brief summary of the situation (e.g. "I've disclosed a finding to the parent project and am awaiting response. I've submitted a placeholder submission for the C4 audit in the meantime.")

It is the warden's responsibility to follow up with Code4rena in a timely manner, based on what they hear back from the original project.

### Use of writing assistance software, ChatGPT output, etc

As a professional audit platform, Code4rena's bar for a satisfactory submission is that it is **as good as one might find in a professional audit report.** 

Using the output of ChatGPT, GPT-3, or automated tools for audit submissions is highly discouraged as it leads to a high ratio of nonsense submissions. Wardens are responsible for verifying the validity and clarity of their own submissions. Sending multiple poor quality submissions in a single audit will result in all of your audit submissions being ruled invalidated. Additional penalties may also be applied at the discretion of judges and C4 staff. 

We are aware this privileges native English speakers as online translation services can result in unclear wordings; therefore, a submission should not be marked as unsatisfactory purely based on grammar and spelling which does not interfere with a judge's ability to understand the submission.

Judges must make the best decision they can regarding quality and understandability of findings.

### Automated findings considered known issues

- At the start of each audit, Code4rena runs a [Bot Race](https://www.code4rena.com/register/bot) where wardens compete to see whose AI-driven bot can create the highest quality and most thorough audit report. 
- The winning report is shared with all C4 wardens within 24 hours of the audit start time, both in the audit repo and in the audit's Discord channel. 
- All findings in the winning Bot Report will be declared publicly known issues, and therefore ineligible for awards.

Wardens may use automated tools as a first pass, and build on these findings to identify High and Medium severity issues ("HM issues"). However, submissions based on automated tools will have a higher burden of proof for demonstrating to sponsors a relevant HM exploit path in order to be considered satisfactory.

## Unauthorized test methods

The following methods are not authorized means of testing within C4 code audits:

* Testing exploits on deployed contracts or systems.
* Network denial of service (DoS or DDoS) tests or other tests that impair access to or damage a system or data.
* Physical testing (e.g. office access, open doors, tailgating), social engineering (e.g. phishing, vishing), or any other non-technical vulnerability testing.

## Editing a report

To edit a submitted finding in an open audit:

1. Sign into your https://code4rena.com user account. 
2. Find the audit on the C4 Audit page and click “view competition"
3. Click on the “Findings” tab. There you will see a list of all your submissions for that audit (both individual and team findings).
4. Select a finding from the list, make your edits and re-submit.

Findings can be edited until the audit deadline.

## Withdrawing a report

It is possible that a warden might want to withdraw a report after submitting it through the website. For example, if a new warden realizes they have not followed the report submission guidelines closely, or discover that a submission was outside the scope of the audit.

In this situation, wardens who wish to have a report withdrawn should: 

1. Sign into https://code4rena.com with your wallet. 
2. Find the audit on the C4 Audit page and click “view competition
3. Click on the “Findings” tab. There you will see a list of all your submissions for that audit (both individual and team findings).
4. Select a finding from the list, and choose the "withdraw" option.

Submissions must be withdrawn before the audit deadline.

## Questions

Questions regarding this policy can be addressed in the `#questions` channel on the [C4 Discord](https://discord.gg/Dr6p5KDCdG). We also invite you to contact us with suggestions for improving this policy.

## Intellectual Property

Unless otherwise specified in the contest's repo, You hereby grant a Creative Commons 0 1.0 license ([details here](https://creativecommons.org/publicdomain/zero/1.0/legalcode)) to any Background IP included in any findings, work product, or other deliverable provided to C4. “Background IP” includes any intellectual property that (i) was developed prior to relevant Opportunity; (ii) was developed after the start of the relevant Opportunity but is outside the scope of the services; (iii) was developed after the conclusion of the relevant Opportunity but has generic applicability; or (iv) derived from or relating to the Background IP. Notwithstanding the forgoing, with the exception of source code that is provided for the purposes of demonstrating a Finding, Background IP does not include source code.

## Authorization

If you make a good faith effort to comply with this policy during your security research, C4, its affiliates, and sponsors will consider your research to be authorized.

The C4 community will work with you to understand and resolve any issues quickly, and C4, its affiliates, and sponsors will not recommend or pursue legal action related to your research.

Should legal action be initiated by a third party against you for activities that were conducted in accordance with this policy, C4 will make this authorization known.
