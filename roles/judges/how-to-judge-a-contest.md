# How to judge an audit

## Timeline
Ideally we would like audits to be judged in 48 hours after handoff.

We ask that you try to complete the judging process quickly so that we can distribute awards to wardens promptly. If you need more time, please communicate that to C4 as soon as possible.

## Here’s how the process works leading up to judging

C4 kicks off the code competition and establishes a private repo to receive incoming issues. Typically, most findings come in on the last day of the audit. When the audit ends, a Lookout will presort the repo and then it will be handed to the sponsor. Sponsors will have the chance to review the findings, comment, and provide feedback on issues.

Sponsor input is non-binding, and do note that sponsors are heavily biased against having a report that includes very many vulnerabilities. Focus your work as a judge on protecting users and providing feedback to wardens.

## Before you get started

Read the [Judging Criteria](https://docs.code4rena.com/roles/wardens/judging-criteria), [Submission Policy](../wardens/submission-policy.md), and review the audit readme as provided by the sponsor.

You may also be interested in browsing past audits, and [reviewing open issues in the Rulebook repo](https://github.com/code-423n4/rulebook/issues), in order to see how other judges have handled issues.

## Reviewing submissions
When your judge application is approved, C4 staff will contact you to invite you to our Github organization and provide you with technical documentation on our judging tools.
Those documents also includes all information regarding de-duping, grading QA/Gas and other judging tasks.

## Notes on judging

* Review the [Judging criteria](https://docs.code4rena.com/roles/wardens/judging-criteria).
* Consider the sponsor’s feedback, but keep in mind that it’s not always going to be objective.
* Any submissions that do not apply specifically to the functionality of the smart contract logic itself should be considered QA.
* When weighing in on severity or validity of an issue, leave a comment describing your justification for any changes you make to the warden's assessment of severity.
* When necessary, cross reference the submission with the codebase to validate the legitimacy of the proposed submission.
* Unless there is something uniquely novel created by combining vectors, most submissions regarding vulnerabilities that are inherent to a particular system or the Ethereum network as a whole should be considered QA. Examples of such vulnerabilities include front running, sandwich attacks, and MEV. In such events, leave a comment on the issue:

> “Sandwich attacks are inherent to AMMs, so this isn’t a unique issue presented by the MarginSwap implementation. With this in mind, I’m downgrading the risk from a proposed medium severity to QA.”

One important caveat to all of the above: _**unless otherwise specified by the audit sponsor or intended to be handled by the code**_**.** For example, flash loans are generally unavoidable, but since MarginSwap had a safeguard against them, we considered these findings relevant in their contest.

## Dealing with spam / repeated low-quality submissions

Please see the [Good Citizen policy](https://docs.code4rena.com/roles/wardens/submission-guidelines#good-citizenship-is-a-requirement-for-compensation).

Note: this policy was instated after [this proposal](https://docs.code4rena.com/awarding/judging-criteria/supreme-court-decisions-fall-2023#proposal-penalties-for-invalid-submissions) from the Autumn 2023 Supreme Court session.

## Discussing issues with the sponsor

Ultimately the judge has the final word, but we want your decisions to be well-informed.  In a typical C4 audit, there will be a few issues that benefit from discussion with the sponsor; the judge may find that their understanding of the system is incomplete and you need to ask for clarification, or where there is room for misunderstanding. Don’t hesitate to connect directly with the sponsor, either in the Github comments (where you can tag them in if needed), or via Discord.

## If you have questions

Do not hesitate to post in the #judges Discord channel, or DM a Contest Administrator with questions as you're working on judging. Any questions or feedback you can add to this documentation, or comments/questions on items above are highly welcome and essential for us improving our process. Thank you! 🙏

## Final step before handing off

Please add a comment to your top scoring QA report noting where there are any items that you disagreed with the severity listed and/or any items that were invalid. These comments will be integrated into the final report.

## When you’re done reviewing

Ping a C4 Contest Administrator and let us know you’re ready to hand off the results for post-judge QA and then award distribution.
