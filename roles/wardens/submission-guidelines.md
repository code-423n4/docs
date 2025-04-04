# Submission guidelines

Best practices and recommendations for submitting to Code4rena competitions. Please also refer to the official [submission policy](https://docs.code4rena.com/roles/wardens/submission-policy).

## Submitting a report

C4 accepts vulnerability reports via the audit submission form.

In order to help us triage and prioritize findings, please ensure that your submissions:

- Are submitted before the submission deadline;
- Use the correct submission form;
- Follow the correct format (see next section);
- Describe the location the vulnerability was discovered and the potential impact of exploitation;
- Offer a detailed description of the steps needed to reproduce the vulnerability (coded Proof of Concept or screenshots are encouraged);
- Have not been surfaced as "known issues" (see audit repo README for details); and
- Are written in English.

## Submission types

### High, Medium, and QA reports

- Wardens should [review Code4rena's severity categorization](https://docs.code4rena.com/awarding/judging-criteria/severity-categorization) prior to submitting vulnerabilities, and select the appropriate risk when submitting.
- Medium or High severity findings should be submitted individually.

### QA reports (low/governance)

Low and non-critical findings must be submitted as a single QA report per warden. 

Your QA report should include:
- all Low severity findings
- all Governance / Centralization risk findings (including centralization risks, systemic risks, and admin privileged functions)

**Non-critical findings are discouraged.** 

Formatting:
- Wardens are encouraged to use a standard format to label findings, e.g. `L-01`, `L-02`, etc. for low-risk findings, and `C-01`, `C-02`, etc. for centralization/governance findings. 
- Please do not use `G-` prefixes as those are typically used to identify Gas optimization findings.
- Non-standard labels such as `R-` (refactor), `I-` (informational), or `S-` (suggestion) will be considered non-critical and are therefore discouraged.

Each QA report is assessed based on report quality and thoroughness as compared with other reports. 

Wardens overstating the severity of QA issues (submitting low/non-critical issues as med/high in order to angle for higher payouts) will have their scores reduced by judges. Wardens who submit multiple QA and/or Gas findings to a single audit without following the required format will have all QA/Gas submissions invalidated for that audit.

For more details on estimating risk for QA reports, please see [Judging Criteria](https://docs.code4rena.com/roles/wardens/judging-criteria#qa-reports-low-non-critical).

## Good citizenship is a requirement for compensation

In order to be eligible for awards, competitors must contribute more value than they take. This is measured by impact rather than intent.

Contributing value to sponsors by helping secure their code must always be the central concern. Attempts that have the impact of gaming the system or circumventing rules will be interpreted as breaking the rules. (See [Satisfactory / unsatisfactory submissions](https://docs.code4rena.com/awarding/incentive-model-and-awards#satisfactory-unsatisfactory-submissions) for some examples.)

Judges have the right to deem a warden ineligible for awards based on behavior and net quality/accuracy of submissions. This includes interactions with judges, staff, sponsors, and other wardens. Multiple violations or egregious abuses may also result in additional consequences, including account suspension or bans.

Wardens who do not have the [SR role](https://docs.code4rena.com/roles/certified-contributors/sr-backstage-wardens) must not solicit SR wardens, validators, or judges to perform post-judging QA (PJQA) actions on their behalf; doing so is a violation of this policy. 

In order to ensure fairness and objectivity, a judge who makes the determination that a warden is deserving of consequences under the Good Citizen Rule will need “+1s” from two other judges. Staff will consider and validate each discipline recommendation based on the evidence presented by judges.

## Burden of proof

Wardens have the burden of proof in submissions. Explaining and rationalizing the potential impact is an essential part of a quality submission. The burden of proof increases based on the potential value of the submission (rarity, severity).

Insufficient proof shall be defined as the judge needing to do additional research or coding in order to validate the claims made in the submission. Therefore it is recommended to have a coded proof of concept for high severity findings in order to make it easy for a judge to validate your case.

Submissions which judges deem insufficiently proven will not be eligible for anything higher than a satisfactory score.

## How to include a proof of concept

To include a proof of concept (PoC) link in your submission, please follow these steps, to ensure that your PoC remains private for the duration of the audit, but can be accessed publicly after the findings are made public:

1. Modify existing test files
2. Provide the diff ([instructions](https://gist.github.com/IllIllI000/21deaa6a55c95a6ec9ca893009ee494f)), which can be applied

## Late submissions

C4 does not accept late submissions under any circumstances; the audit deadlines are firm. We recommend that you submit your findings at least a few minutes before the cut-off time, since the submission form can become slow or unresponsive in the final minutes of an audit, due to high traffic.

## Submissions to the wrong audit

C4 cannot "transfer" your submission to another audit after the audit ends. If you discover that you have accidentally submitted a finding to the wrong audit, please re-submit it to the correct audit, and then follow the steps below to withdraw your report from the other audit.

## How to submit Zero-day or otherwise highly sensitive bugs

If you discover a high- or critical-severity vulnerability affecting deployed contracts, please follow these steps:

1. Confirm that the audit scope includes live/deployed code. Typically this info will be posted in the audit channel in C4's Discord server.
1. Review [the "live criticals" exception](https://docs.code4rena.com/awarding/incentive-model-and-awards#the-live-criticals-exception) section of our docs for definitions and awarding rules.
1. Using the audit submission form (audit page > `Submit finding`), submit a placeholder finding, with a non-specific title (e.g. "Potentially sensitive issue - disclosed privately")
   - In the `Links to affected code` field, link to `#L1` of any file in scope. 
   - In the `Vulnerability details` field, enter "Disclosed privately" and omit any other details.
1. While logged in to the Code4rena website, [submit a Help Desk request](https://code4rena.com/help/), and select "Sensitive disclosure" for "What type of problem do you need help with?" Please include:
    - Name of audit, and
    - Link to a [secret Gist](https://gist.github.com/) containing the finding details. (You may use Markdown in your Gist -- just save with the filename extension `.md`.)

**All Highs affecting live code should be reported as sensitive disclosures** (and therefore must include coded PoC). Submissions that meet the above criteria and are not reported via the proper procedure will not be eligible for awards.

Code4rena staff will review the issue immediately with the judge and sponsor, and will ensure the finding details are added to your placeholder finding after any immediate risks have been addressed.

## Findings in "parent" of forked projects

If an issue is discovered during an audit that relates to the "parent" of a forked project, wardens should disclose the finding to the parent project first, and submit a placeholder finding to the C4 audit. Please follow these steps:

1. Submit a placeholder finding using the audit submission form, with a non-specific title (e.g. "Potentially sensitive issue")
    - **Do not** disclose the parent / third party name within the body of the finding issue.
    - **Do** include a hash of the issue
2. While logged in to the Code4rena website, [submit a Help Desk request](https://code4rena.com/help/), and select "Sensitive disclosure" for "What type of problem do you need help with?" Please include:
    - Name of audit, and
    - Brief summary of the situation (e.g. "I've disclosed a finding to the parent project and am awaiting response. I've submitted a placeholder submission for the C4 audit in the meantime.")

It is the warden's responsibility to follow up with Code4rena in a timely manner, based on what they hear back from the original project.

## Use of writing assistance software, ChatGPT output, etc

As a professional audit platform, Code4rena's bar for a satisfactory submission is that it is **as good as one might find in a professional audit report.**

Using the output of ChatGPT, GPT-3, or automated tools for audit submissions is highly discouraged as it leads to a high ratio of nonsense submissions. Wardens are responsible for verifying the validity and clarity of their own submissions. Sending multiple poor quality submissions in a single audit will result in all of your audit submissions being ruled invalidated. Additional penalties may also be applied at the discretion of judges and C4 staff.

We are aware this privileges native English speakers as online translation services can result in unclear wordings; therefore, a submission should not be marked as unsatisfactory purely based on grammar and spelling which does not interfere with a judge's ability to understand the submission.

Judges must make the best decision they can regarding quality and understandability of findings.

## Automated findings considered known issues

Wardens may use automated tools as a first pass, and build on these findings to identify High and Medium severity issues ("HM issues"). However, submissions based on automated tools will have a higher burden of proof for demonstrating to sponsors a relevant HM exploit path in order to be considered satisfactory.

Wardens and judges are recommended to read [the Supreme Court's verdict on this issue](https://docs.code4rena.com/awarding/judging-criteria/supreme-court-decisions-fall-2023) for further advice on the validity of submissions based on automated tools.

## Editing a report

To edit a submitted finding in an open audit:

1. Sign into your https://code4rena.com user account.
2. Find the audit on the C4 Audit page and click “view competition"
3. Click on the “Findings” tab. There you will see a list of all your submissions for that audit (both individual and team findings)
4. Select a finding from the list, make your edits and re-submit.

Findings can be edited until the audit deadline.

## Withdrawing a report

It is possible that a warden might want to withdraw a report after submitting it through the website. For example, if a new warden realizes they have not followed the report submission guidelines closely, or discover that a submission was outside the scope of the audit.

In this situation, wardens who wish to have a report withdrawn should:

1. Sign into https://code4rena.com with your wallet.
2. Find the audit on the C4 Audit page and click “view competition"
3. Click on the “Findings” tab. There you will see a list of all your submissions for that audit (both individual and team findings).
4. Select a finding from the list, and choose the "withdraw" option.

Submissions must be withdrawn before the audit deadline.
