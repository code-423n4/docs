# FAQ about QA and Gas Reports

This FAQ pertains to the award mechanism update that takes effect April 30, 2024, which changes the submission guidelines for low-risk, non-critical, and gas optimization reports. For more details, see [Judging Criteria](https://docs.code4rena.com/roles/wardens/judging-criteria).

### What happens to the award pool if no Med/High vulns are found? 

Unless otherwise stipulated in the audit repo, the full pool would then be divided based on the QA Report curve.

### Can I still include non-critical findings in my QA report?

Non-critical findings are discouraged for QA reports. 

### What if a low-impact QA report turns out to be a high-impact report?  Would the report be upgraded?

It's conceivable it could be upgraded, though it's important to consider that part of auditing is demonstrating proper theory of how an issue could be exploited. If a warden notices something is "off" but is unable to articulate why it could lead to loss of funds, for example, the job is only half-done; without understanding the implications, a developer could very well overlook or deprioritize the issue.

The tl;dr for [determining severity](../../awarding/judging-criteria/severity-categorization.md) is relatively clear with regard to separating by impact.

### What happens when an issue submitted by the warden as part of their QA report (an L or C) *DOES* get bumped up to Med/High by the judge after review?

If it seemed appropriate to do so based on a judge's assessment of the issue, they could certainly choose to do this.

However, QA items may be marked as a duplicate of another finding *without* being granted an upgrade, since making the case for *how* an issue can be exploited, and providing a thorough description and proof of concept, is part of what merits a finding properly earning medium or high severity.

### Conversely, in the reverse situation where an issue submitted by wardens as H/M level, is subsequently downgraded to QA level by the judge during their review, would the penalty just be excluding the overrated warden submission from consideration in regards to the QA rewards?

In theory, findings downgraded to QA are grouped with the warden's QA report (if one exists) and they are grouped together. In practice, however, we have found that downgraded issues do not have a significant impact on wardens' overall QA score. Judges can also decide to mark off points in someone's QA report if they see behavior that seems like it might be trying to game for higher rewards by inflating severity, so it can have a negative consequence as well.

