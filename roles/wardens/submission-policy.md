# Submission policy

Code4rena is an open organization committed to improving the security of decentralized protocols while protecting the information of our sponsors and participants. This policy is intended to provide C4 Wardens (security researchers) clear guidelines for participating in code contests while conducting vulnerability discovery activities.

The following policy conveys C4’s preferences in how to submit discovered vulnerabilities to the organization and describes what systems and types of research are covered under this policy, how to share vulnerability reports, and the length of time we expect Wardens to wait prior to publicly disclosing vulnerabilities.

When participating in C4 code contests, please formally submit any contract vulnerabilities using the submission form.

Reports can be submitted at any point prior to stop time for a given contest. The details for each code contest can be found in the contest repo.

All community members agree to be bound by the Code4rena Code of Conduct, which can be viewed [in the Code4rena Discord](https://discord.com/channels/810916927919620096/851883682470166558/851891396255940618). 

## Audit contest guidelines

Under this policy, audit contests covers activities in which you:

* Register as a C4 Warden within an individual capacity or as part of a team.
* Submit your bug report using the submission form.
* Make every effort to avoid privacy violations, degradation of user experience, disruption to production systems, and destruction or manipulation of data, especially in regard to funds.
* Only use exploits to the extent necessary to confirm a vulnerability’s presence. Do not use an exploit to compromise funds, exfiltrate data, establish persistent permissioning access, or use the exploit to redirect to other systems.
* Unless explicitly noted by the affiliated sponsor, **wait until the contest report has been published** before you disclose it publicly.
* Do not submit a high volume of low-quality reports.

In the event that you encounter a critical vulnerability that the sponsor project would want to know about, even before the end of the contest, immediately notify the sponsor privately. The sponsor's point of contact will be listed in their contest channel on the [C4 Discord](https://discord.gg/EY5dvm3evD).

> Publicly disclosing any information prior to the end of a code competition is grounds for immediate forfeit of award and disqualification from any future C4 events and activities.

## Submitting a report

C4 accepts vulnerability reports via the contest submission form.

In order to help us triage and prioritize submissions, please ensure that your reports:

* Are submitted no later than the code contest stop time.
* Use the contest submission process.
* Follow the correct report format. (See next section.)
* Describe the location the vulnerability was discovered and the potential impact of exploitation.
* Offer a detailed description of the steps needed to reproduce the vulnerability (proof of concept scripts or screenshots are helpful).
* Have not been surfaced as "known issues" (see contest repo `README` for details).
* Are written in English, if possible.

It is also recommended to ensure you receive email confirmation of each submission. (If you do not see an email confirmation, please check your spam folder.)

### Report format

- Medium or High severity findings should be submitted individually.
- All QA findings (Low risk or Non-critical) must be submitted as a single QA report per warden (or team). 
- All Gas optimizations must be submitted as a single Gas report per warden (or team).

Wardens who submit multiple QA and/or Gas findings to a single contest without following the required format will have all QA/Gas submissions invalidated for that contest. 

For more details on QA and Gas reports, and estimating risk, please see [Judging Criteria](https://docs.code4rena.com/roles/wardens/judging-criteria#qa-reports-low-non-critical).

### How to include a proof of concept

To include a proof of concept (PoC) link in your submission, please follow these steps, to ensure that your PoC remains private for the duration of the contest, but can be accessed publicly after the findings are made public:

1. Modify existing test files
2. Provide the diff ([instructions](https://gist.github.com/IllIllI000/21deaa6a55c95a6ec9ca893009ee494f)), which can be applied

### Late submissions

C4 does not accept late submissions under any circumstances; the contest deadlines are firm. We recommend that you submit your findings at least a few minutes before the cut-off time, since the submission form can become slow or unresponsive in the final minutes of a contest (due to high traffic).

### Submissions to the wrong contest

C4 cannot "transfer" your submission to another contest after the contest ends. If you discover that you have accidentally submitted a finding to the wrong contest, please re-submit it to the correct contest, and then follow the steps below to withdraw your report from the other contest.

### Findings in "parent" of forked projects

If an issue is discovered during a contest that relates to the "parent" of a forked project, wardens should disclose the finding to the parent project first, and submit a placeholder finding to the C4 contest. Guidelines: 

- **Do not** disclose the parent / third party name within the body of the finding issue.
- **Do** include a hash of the issue

It is the warden's responsibility to follow up with Code4rena in a timely manner, based on what they hear back from the original project.

### ChatGPT output (or similar) is unacceptable

Using ChatGPT or similar tools for contest submissions is prohibited, and will result in all of your contest submissions being ruled invalidated. Additional penalties may also be applied at the discretion of judges and C4 staff. 

## Editing a report

To edit a submitted finding in an open contest:

1. Sign into https://code4rena.com with your wallet. 
2. Find the contest on the C4 Contest page and click “view contest”
3. Click on the “Findings” tab. There you will see a list of all your submissions for that contest (both individual and team findings).
4. Select a finding from the list, make your edits and re-submit.

Findings can be edited until the contest deadline.

## Withdrawing a report

It is possible that a warden might want to withdraw a report after submitting it through the website. For example, if a new warden realizes they have not followed the report submission guidelines closely, or discover that a submission was outside the scope of the contest.

In this situation, wardens who wish to have a report withdrawn should: 

1. Sign into https://code4rena.com with your wallet. 
2. Find the contest on the C4 Contest page and click “view contest”
3. Click on the “Findings” tab. There you will see a list of all your submissions for that contest (both individual and team findings).
4. Select a finding from the list, and choose the "withdraw" option.

Submissions must be withdrawn before the contest deadline.

## Unauthorized test methods

The following methods are not authorized means of testing within C4 code contests:

* Testing exploits on mainnet.
* Network denial of service (DoS or DDoS) tests or other tests that impair access to or damage a system or data.
* Physical testing (e.g. office access, open doors, tailgating), social engineering (e.g. phishing, vishing), or any other non-technical vulnerability testing.

## Questions

Questions regarding this policy can be addressed in the `#questions` channel on the [C4 Discord](https://discord.gg/Dr6p5KDCdG). We also invite you to contact us with suggestions for improving this policy.

## Authorization

If you make a good faith effort to comply with this policy during your security research, C4, its affiliates, and sponsors will consider your research to be authorized.

The C4 community will work with you to understand and resolve any issues quickly, and C4, its affiliates, and sponsors will not recommend or pursue legal action related to your research.

Should legal action be initiated by a third party against you for activities that were conducted in accordance with this policy, C4 will make this authorization known.
