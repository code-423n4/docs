# FAQ about QA and Gas Reports

This FAQ pertains to the award mechanism update that takes effect February 3, 2022, which changes the submission guidelines for low-risk, non-critical, and gas optimization reports. For more details, see [Judging Criteria](roles/wardens/judging-criteria).

### What happens to the award pool if no Med/High vulns are found? 

The full pool would then be divided based on the QA Report curve.

### Will non-critical findings hold some weight? Just want to know if it's worth spending a considerable amount of time writing this part of the report.

The full QA report will be graded on a curve against the other reports. We'll be experimenting together as a community with this, but we think we'll learn a lot and it will be interesting to see the best practices emerge.

We are intentionally not providing an "example," as we are eager to see what approaches folks take and to be able to learn from a variety of approaches.

### What if a low-impact QA report turns out to be a high-impact report? How does that work with the 10% prize pool? Would the report be upgraded?

It's conceivable it could be upgraded, though it's important to consider that part of auditing is demonstrating proper theory of how an issue could be exploited. If a warden notices something is "off" but is unable to articulate why it could lead to loss of funds, for example, the job is only half-done; without understanding the implications, a developer could very well overlook or deprioritize the issue.

The tl;dr for determining severity is relatively clear with regard to separating by impact.

### What happens when an issue submitted by the warden as part of their QA report (an L or N) *DOES* get bumped up to Med/High by the judge after review?

If it seemed appropriate to do so based on a judge's assessment of the issue, they could certainly choose to do this.

The judge could create a new separate Github issue in the findings repo that contains the relevant portions of the warden's QA report, and add that to the respective H or M level bucket.

### Conversely, in the reverse situation where an issue submitted by wardens as H/M level, is subsequently downgraded to QA level by the judge during their review, would the penalty just be excluding the overrated warden submission from consideration in regards to the QA rewards?

We'll need to see how it works in reality, but our current assumption is that (a) low severity findings attempted to get pushed into med/high would essentially get zero (just logically so since they wouldn't be high or med), and then (b) their QA report would be lower quality as a result, and so they wouldn't score as highly as they could have. Judges could also decide to mark off points in someone's QA report if they saw behavior that seemed like it might be trying to game for higher rewards by inflating severity, so it could have a negative consequence as well.
