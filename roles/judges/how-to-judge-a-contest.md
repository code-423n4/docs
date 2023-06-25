# How to judge an audit

## Timeline

In general, judges report that most audits take a half-day to 2 days of work.

We ask that you try to complete the judging process quickly (ideally within 5 days) so that we can distribute awards to wardens promptly. If you need more time, please communicate that to C4 as soon as possible.

## Here’s how the process works leading up to judging

C4 kicks off the code competition and establishes a private repo to receive incoming issues. Typically, most findings come in on the last day of the audit. When the audit ends, sponsors will have the chance to review the findings, comment, and provide feedback on issues.

Sponsor input is non-binding, and do note that sponsors are heavily biased against having a report that includes very many vulnerabilities. Focus your work as a judge on protecting users and providing feedback to wardens.

C4 will share a Google sheet with you that contains audit data. This sheet will be used by a script to calculate awards, so please preserve the data structure.

## Before you get started

Read the [Judging Criteria](../wardens/judging-criteria.md), [Submission Policy](../wardens/submission-policy.md), and review the audit readme as provided by the sponsor.

You may also be interested in browsing past audits, and [reviewing open issues in the Rulebook repo](https://github.com/code-423n4/rulebook/issues), in order to see how other judges have handled issues.

## Reviewing submissions

Open the findings spreadsheet and GitHub issues. There are four columns you’ll be working with:

* **reportId** — This is a unique ID which contains your assessed risk level (`H`, `M`, `Q` for QA Report, and `G` for gas optimizations) followed by a number (01, 02, 03, etc). So, for example: `H-01`, `M-10`, `Q-07`, `G-11`). The risk here should match the risk assessed in the 'risk' column. _(Yes, this is dumb and duplicate effort. We'll change that in the future.)_ **Tip:** Most of our judges fill this column in last, after they have assessed risk, duplicates, and scores.
* **duplicateOf** — use this for indicating an item as a duplicate of another finding using the same form as reportId (`H-01`, `M-10`, `Q-07`, `G-11`).
* **risk** — your assessed risk: 3 for high, 2 for medium, Q for QA Reports, 'G' for gas optimization
* **score** — for QA and Gas reports only, use this column to enter your score (from 0-100), based on thoroughness, quality of description, and overall value of recommendations.

So, for example:

| title                           | reportId | duplicateOf | risk | score |
| ------------------------------- | -------- | ----------- | ---- | ----- |
| Some very serious issue         | H-01 |      | 3    |    |
| The same serious issue as above | H-01 | H-01 | 3    |    |
| QA Report                       | Q-02 |      | Q    | 85 |
| Medium severity issue           | M-05 |      | 2    |    |
| Gas optimization issue          | G-01 |      | G    | 52 |

You can edit the **title** field as needed, based on your judgment.

### For High and Medium risk submissions

- Review each submission and assess:
    - **Is it valid?** — There are two main categories of invalid issues: findings that are out of scope (per the sponsor’s audit repo), and issues where the warden has misunderstood the system. You should mark any invalid submissions as such, using the `invalid` label in Github, and enter `INVALID` (all caps) in *both* the ReportId and risk columns in the judging sheet. All invalid issues should be closed in Github.
    - **What is the correct risk level? —** If you disagree with the risk level assigned by the warden, you may adjust it. Please change the labels in Github, and leave a comment with your reasoning. (You may wish to refer to the [Judging Criteria](https://docs.code4rena.com/roles/wardens/judging-criteria#estimating-risk-tl-dr) for guidance.) Please also adjust the value in the `risk` column of the judging spreadsheet.
    - **If a Medium or High risk issue needs to be downgraded** to low or non-critical risk level, please see below for instructions.
- You can ignore the “score” column for High and Medium risk submissions; that is only used for QA and Gas reports.

### For QA and Gas reports

- **You do *not* need to de-dupe QA and Gas reports.** Each one is intended to be a compilation of issues and recommendations from a warden.
- **Each QA and Gas report should be scored on a scale of 0-100.** Enter your score in the `score` column of the judging spreadsheet.
- It's usually preferable to assign a *unique* score to each report, and avoid ties, due to [the way the awarding curve works](https://docs.code4rena.com/incentive-model-and-awards). However, ties are allowed.
- For each category (QA/Gas), the top-scoring report will be included in the C4 audit report, and will receive the largest share of the awards.
- For more information on how scores affect awarding, see [“Incentive Model and Awards.”](https://docs.code4rena.com/incentive-model-and-awards)
- **If a QA or Gas report contains a finding that should be upgraded** to Medium or High risk, please see below for instructions.

### Upgrading issues from QA/Gas to Medium/High

If you find an issue in a QA or Gas report that deserves to be upgraded in severity to Medium or High risk: first, we ask that you consider that part of auditing is demonstrating proper theory of how an issue could be exploited. (If a warden notices something is “off,” but is unable to articulate why it could lead to loss of funds, for example, the job is only half-done—without understanding the implications, a developer could very well overlook or deprioritize the issue.)
It is also worth noting that QA items may be marked as a duplicate of a Medium or High finding without being granted an upgrade, since making the case for how an issue can be exploited, and providing a thorough description and proof of concept, is part of what merits a finding properly earning Medium or High severity

Judges can upgrade an issue by using the 'create Upgraded submission' script in the judging spreadsheet:
    *If you do not want to provide the Authorizations to run this script yourself, then just highlight the QA reports that will need upgraded in the spreadsheet, and contact your Contest Administrator (CA) when you have completed judging and they will help with this step.
1. Highlight the row in the spreadsheet that contains the QA or Gas that needs to be upgraded.
2. Click the C4 menu to the right of Help at the top of the sheet.
3. Choose create Upgraded submission  
4. The first time you will need to provide authorization through Google, and then repeat Steps 1-3.
5. Type either H or M for the risk level of the new issue.
6. You will now see a new entry at the bottom of the spreadsheet. It has Columns E -> K filled in just like when the spreadsheet is generated. It has also created a new issue in the findings repo, which you can see by clicking the link in Column H.
7. You do not need to change the auto-generated title, but please update the body of the finding with the relevant information from the QA/Gas that you are upgrading from.
8. Finally update the first 4 columns of the spreadsheet for that issue as you normally would.
9. Repeat for any additional upgrades.

### Downgrading issues from Medium/High to QA/Gas

To downgrade an issue’s severity from Medium or High to QA (Low or Non-critical) or Gas:

1. Adjust the labels on Github per usual (remove Medium/High and add QA/Gas, leaving a comment with your reasoning);
2. Enter the reportID and risk into the judging sheet, per usual;
3. **If the warden also submitted a QA report:** 
    1. Mark the downgraded issue as a duplicate of their QA report. (See “Handling duplicates” below.) 
    2. Comment on the Github issue: “Grouping this with the warden’s QA report, [link to issue]”
    3. You may choose to adjust the warden’s QA report score if you think the additional issues increase or decrease the value of the warden's overall contribution.
4. **If the warden did NOT submit a QA/Gas report:** treat the downgraded issue as a QA report, and assign it a score (0-100). (If a warden has more than one downgraded issue, judge them together as a single QA report.)

For each category — Gas and QA — each warden should have a single reportID, no matter how many issues they have.

## Notes on judging

* Review the [judging criteria](https://docs.code4rena.com/roles/wardens/judging-criteria).
* Consider the sponsor’s feedback, but keep in mind that it’s not always going to be objective.
* Any submissions that do not apply specifically to the functionality of the smart contract logic itself should be considered QA.
* When weighing in on severity or validity of an issue, leave a comment describing your justification for any changes you make to the warden's assessment of severity.
* When necessary, cross reference the submission with the codebase to validate the legitimacy of the proposed submission.
* Unless there is something uniquely novel created by combining vectors, most submissions regarding vulnerabilities that are inherent to a particular system or the Ethereum network as a whole should be considered QA. Examples of such vulnerabilities include front running, sandwich attacks, and MEV. In such events, leave a comment on the issue:

> “Sandwich attacks are inherent to AMMs, so this isn’t a unique issue presented by the MarginSwap implementation. With this in mind, I’m downgrading the risk from a proposed medium severity to QA.”

One important caveat to all of the above: _**unless otherwise specified by the audit sponsor or intended to be handled by the code**_**.** For example, flash loans are generally unavoidable, but since MarginSwap had a safeguard against them, we considered these findings relevant in their audit.

### Discussing issues with the sponsor

Ultimately the judge has the final word, but we want your decisions to be well-informed.  In a typical C4 audit, there will be a few issues that benefit from discussion with the sponsor; the judge may find that their understanding of the system is incomplete and you need to ask for clarification, or where there is room for misunderstanding. Don’t hesitate to connect directly with the sponsor, either in the Github comments (where you can tag them in if needed), or via Discord.

## Handling duplicates in GitHub

In the event that you identify an issue you think should be considered a duplicate which sponsors have not previously flagged as a duplicate:

1. Determine the best and most thorough description of the finding among the set of duplicates; this will be used in the audit report. We'll refer to this as the "primary" issue within a given set of dupes.
2. The primary issue should remain open in Github; all related duplicate submissions should be labeled "duplicate", include a comment linking to the primary issue, and closed.
3. If the sponsor selected a different primary issue, but you prefer another one, please re-open the one you want to be the primary, and remove the duplicate tag; then do the inverse to the sponsor’s pick (close it and attach the duplicate label).

## If you have questions

In the Judging FAQ, you'll find comments and questions posed by previous judges. These may be useful to review as they account for some of the edge cases not addressed by the docs above.

In addition, do not hesitate to DM a Contest Administrator with questions as you're working on judging. Any questions or feedback you can add to this documentation, or comments/questions on items above are highly welcome and essential for us improving our process. Thank you! 🙏

## When you’re done reviewing

Ping a C4 Contest Administrator and let us know you’re ready to hand off the results for award distribution.
