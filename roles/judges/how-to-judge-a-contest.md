# How to judge an audit

## Timeline
Ideally we would like contests to be judged in 48 hours after handoff.

## Notes on judging

* Review the [Judging criteria](https://docs.code4rena.com/roles/wardens/judging-criteria), [Submission Policy](../wardens/submission-policy.md), and review the contest readme as provided by the sponsor.
* You may also be interested in browsing past audits, and [reviewing open issues in the Rulebook repo](https://github.com/code-423n4/rulebook/issues), in order to see how other judges have handled issues.
* Consider the sponsor’s feedback, but keep in mind that it’s not always going to be objective.
* Any submissions that do not apply specifically to the functionality of the smart contract logic itself should be considered QA.
* When weighing in on severity or validity of an issue, leave a comment describing your justification for any changes you make to the warden's assessment of severity.
* When necessary, cross reference the submission with the codebase to validate the legitimacy of the proposed submission.
* Unless there is something uniquely novel created by combining vectors, most submissions regarding vulnerabilities that are inherent to a particular system or the Ethereum network as a whole should be considered QA. Examples of such vulnerabilities include front running, sandwich attacks, and MEV. In such events, leave a comment on the issue:

> “Sandwich attacks are inherent to AMMs, so this isn’t a unique issue presented by the MarginSwap implementation. With this in mind, I’m downgrading the risk from a proposed medium severity to QA.”

One important caveat to all of the above: _**unless otherwise specified by the audit sponsor or intended to be handled by the code_.** For example, flash loans are generally unavoidable, but since MarginSwap had a safeguard against them, we considered these findings relevant in their audit.

## Discussing issues with the sponsor

Ultimately the judge has the final word, but we want your decisions to be well-informed.  In a typical C4 audit, there will be a few issues that benefit from discussion with the sponsor; the judge may find that their understanding of the system is incomplete and you need to ask for clarification, or where there is room for misunderstanding. Don’t hesitate to connect directly with the sponsor, either in the Github comments (where you can tag them in if needed), or via Discord.

## If you have questions

Do not hesitate to post in the #judges Discord channel, or DM a Contest Administrator with questions as you're working on judging. Any questions or feedback you can add to this documentation, or comments/questions on items above are highly welcome and essential for us improving our process. Thank you! 🙏

## Final step before handing off

Please add a comment to your top scoring QA report noting where there are any items that you disagreed with the severity listed and/or any items that were invalid. These comments will be integrated into the final report.

## When you’re done reviewing

Ping a C4 Contest Administrator and let us know you’re ready to hand off the results for post-judge QA and then award distribution.

