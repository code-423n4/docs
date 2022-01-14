# How to judge a contest

### Timeline

In general, judges report that most contests take a half-day to 2 days of work&#x20;

We ask that you try to complete the judging process quickly so that we can distribute awards to wardens promptly. If you need more time, please communicate to C4 as soon as possible.

### Here’s how the process works leading up to judging

C4 kicks off the code competition and establishes a private repo to receive incoming issues. Typically most findings come in on the last day of the contest. When the contest ends, sponsors will have the chance to review the findings, comment, and provide feedback on issues.

Sponsor input is non-binding, and do note that sponsors are heavily biased against having a report that includes very many vulnerabilities. Focus your work as a judge on protecting users and providing feedback to wardens.

C4 will share a Google sheet with you that contains contest data. This sheet will be used by a script to calculate awards, so please preserve the data structure.

### Before you get started

Read the [Judging Criteria](../wardens/judging-criteria.md), [Submission Policy](../wardens/submission-policy.md), and review the contest readme as provided by the sponsor.

You may also be interested in browsing past contests in order to see how other judges have handled issues.

### Reviewing submissions

Open the findings spreadsheet and GitHub issues. There are three columns you’ll be working with:

* **risk** — your assessed risk 3 for high, 2 for medium, 1 for low, 0 for non-critical, 'g' for gas optimization
* **reportId** — This is a unique ID which contains your assessed risk level (`H`, `M`, `L` for high/med/low, `N` for non-critical, and `G` for gas optimizations) followed by a number (01, 02, 03, etc). So, for example: `H-01`, `M-10`, `L-07`, `N-03`, `G-11`). The risk here should match the risk assessed in the 'risk' column. _(Yes, this is dumb and duplicate effort. We'll change that in the future.)_
* **duplicateOf** — use this for indicating an item as a duplicate of another finding using the same form as reportId (`H-01`, `M-10`, `L-07`, `N-03`, `G-11`).

So, for example:

| title                            | risk | reportId | duplicateOf |
| -------------------------------- | ---- | -------- | ----------- |
| Some very serious issue          | 3    | H-01     |             |
| A new minor issue                | 2    | L-01     |             |
| The same serious issue as above  | 3    | H-01     | H-01        |
| A different minor issue          | 1    | L-02     |             |
| Medium severity issue            | 2    | M-05     |             |

You can also edit the **title** field as needed based on your judgment.

### Notes on judging

* Review the [judging criteria](https://code4rena.com/judging-criteria/).
* Consider the sponsor’s feedback, but keep in mind that it’s not always going to be objective.
* Any submissions that do not apply specifically to the functionality of the smart contract logic itself should be considered non-critical.
* When weighing in on severity or validity of an issue, leave a comment describing your justification for any changes you make to the warden's assessment of severity.
* When necessary, cross reference the submission with the codebase to validate the legitimacy of the proposed submission.
* Unless there is something uniquely novel created by combining vectors, most submissions regarding vulnerabilities that are inherent to a particular system or the Ethereum network as a whole should be considered non-critical. Examples of such vulnerabilities include front running, sandwich attacks, and MEV. In such events, leave a comment on the issue:

> “Sandwich attacks are inherent to AMMs, so this isn’t a unique issue presented by the MarginSwap implementation. With this in mind, I’m downgrading the risk from a proposed medium severity to non-critical.”

One important caveat to all of the above: _**unless otherwise specified by the contest sponsor or intended to be handled by the code**_**.** For example, flash loans are generally unavoidable, but since MarginSwap had a safeguard against them, we considered these findings relevant in their contest.

### Handling duplicates in GitHub

In the event that you identify an issue you think should be considered a duplicate which sponsors have not previously flagged as a duplicate:

1. Determine the best and most thorough description of the finding among the set of duplicates. (This will be used in the draft audit report.)
2. Close the other duplicate issues and mention the primary issue # so that duplicate issues get linked.

### If you have questions

At the bottom of this doc are comments and questions posed by previous judges. These may be useful to review as they account for some of the edge cases not addressed by the docs above.

In addition, do not hesitate to DM @sockdrawermoney with questions as you're working on judging. Any questions or feedback you can add to the bottom of this document or comments/questions on items above are highly welcome and essential for us improving our process. Thank you! 🙏

### When you’re done reviewing

Ping a C4 organizer and let us know you’re ready to hand off the results for award distribution.
