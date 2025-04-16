# Awarding

To incentivize **wardens**, C4 uses a unique scoring system with two primary goals: reward participants for finding unique vulnerabilities and also to make the audit resistant to Sybil attack. A secondary goal of the scoring system is to encourage participants to form teams and collaborate.

**Judges** are incentivized to review findings and decide their severity, validity, and quality by receiving a share of the prize pool themselves.

**Notes:**

* `pie` is the number of shares assigned to a unique [finding](../competitions/submission-guidelines.md#high-medium-and-qa-reports) or [report](../competitions/submission-guidelines.md#qa-reports-low-governance).
* `split` is the number of times those shares were divided, the findings count for a given group.
* `slice` is the number of shares assigned for that warden’s finding.

We periodically ship bug fixes that may produce minor differences in award calculation results over time.

## High and Medium Risk findings

Wardens are given shares for findings discovered based on severity, and those shares give the owner a pro rata piece of the pie:

`Med Risk Slice: 3 * (0.85 ^ (split - 1)) / split`\
`High Risk Slice: 10 * (0.85 ^ (split - 1)) / split`

Please note that submissions with partial credit still count as 1 submission in the algorithm.\
During awarding, each award is redeemed for: `award pool / pie / slice`.

### Bonus for best / selected for report

For each unique High or Medium finding, the submission selected for inclusion in the audit report receives a 30% slice bonus. The `pie` (total of slices) is also increased accordingly.

Let's look at an example of a High risk finding (set of duplicates), containing 3 satisfactory submissions.

As per the formula, the pie would be:\
`10 * (0.85 ^ (findingCount - 1)) = 7.225`

Warden A's submission is selected for report; therefore the pie is adjusted as follows:\
`new pie = previous pie + [selected submission's slice] * 0.3`\
`=> 7.225 + ( 2.408333333333333 * 0.3 ) = 7.9475`

The resulting awards are:

| **Warden**             | **finding** | **risk** | **pie** | **split** | **slice**          | **award** |
| ---------------------- | ----------- | -------- | ------- | --------- | ------------------ | --------- |
| 'Warden A \[selected]' | 'H-02'      | '3'      | 7.9475  | 3         | 3.1308333333333334 | 1040      |
| 'Warden B'             | 'H-02'      | '3'      | 7.9475  | 3         | 2.4083333          | 800       |
| 'Warden C'             | 'H-02'      | '3'      | 7.9475  | 3         | 2.4083333          | 800       |

### Bonuses for top competitors

For audits starting on or after April 30, 2024, there are two bonuses for top-performing wardens/teams:

1. **Hunter bonus:** 10% of the HM pool will be awarded to the warden or team who identifies the greatest number of unique HMs.
2. **Gatherer bonus:** 10% of the HM pool will be awarded to the warden or team who identifies the greatest number of valid HMs.

Both bonuses weigh Highs more heavily than Mediums, similarly to Code4rena's standard awarding mechanism.

**Top Hunter score**

Each participant's High- and Medium-risk submissions are used to calculate the Top Hunter score. The scoring logic is as follows:

* Only full-credit HM findings with fewer than 5 submissions in the findings set count towards the top hunter score.
* For each High-risk finding, score += 10 \* 1/x, where x = number of duplicates
* For each Medium-risk finding, score += 3 \* 1/x, where x = number of duplicates

For example, if a warden found:

* 1 High-risk finding that was found by 3 other wardens, that finding's score would be 10 \* 1/4 = 2.5
* 1 unique Medium, that finding's score would be 3 \* 1 += 3
* …for a total score of 5.5.

Partial-credit duplicates (see next section) do not count towards a competitor's Top Hunter score, but they are factored into the value of `x` (number of duplicates), as follows:

* If a group of High-risk duplicates (`Finding A`) includes 4 full-credit submissions and 1 `partial-25` submission, `x` = 4 + 0.25 = 4.25.
* If a group of High-risk duplicates (`Finding B`) includes 4 full-credit submissions and 2 `partial-50` submissions, `x` = 4 + (2 \* 0.5) = 5.

In these examples, any full-credit submissions within `Finding A` would count for `+= 10 * 1/4.25`, whereas full-credit submissions within `Finding B` would not be counted towards the Top Hunter score (since it does not meet the `fewer than 5 submissions in the findings set` criterion).

**Top Gatherer score**

The Top Gatherer score is calculated using all full-credit High- and Medium-risk findings, as follows:

* (Number of High-risk findings for `user` / Total number of High-risk findings) \* 10 = `highScore`
* (Number of Medium-risk findings for `user` / Total number of Medium-risk findings) \* 3 = `mediumScore`
* `highScore` + `mediumScore` = `gathererScore`

Partial credit duplicates (see next section) do not count towards the Top Gatherer scores.

### Duplicates getting partial credit

All submissions that identify the same functional vulnerability will be considered duplicates regardless of effective rationalization of severity or exploit path.

However, any submissions which do not identify or effectively rationalize the top identified severity case may be judged as “partial credit” and may have their shares divided at the judge’s sole discretion (e.g. 25%, 50%, or 75% of the shares of a satisfactory submission in the duplicate set).

Awards for partial duplicates are calculated as follows:

First, the portion of the total pie allocated to a specific slice is calculated, based on the scores of related findings:

1. Select findings that share the same `reportId` as the given slice.
2. Calculate total credit - for each finding in the filtered group:

* Add the score to totalCredit if the score is ≤ 1
* Add 1.3 to totalCredit if the score is > 1

3. Calculate slice credit, based on the slice score of each finding in the filtered group:

* If the score is 2, set sliceCredit to 1.3
* If the score is 1, set sliceCredit to 1
* If the score is < 1, set sliceCredit to the score (Partials -> 0.25, 0.5, 0.75)
* If the score is 0, return 0

4. Compute the portion as `portion = slice.pie * (sliceCredit/totalCredit)`

Next, the award is calculated using `award = (portion/mainSliceTotal) * prize.mainPool`. (In the code, `mainPool` refers to the HM pool.)

#### Sample results

Scenario:

* 1 Solo High
* Group of 19 High duplicates
* 5 partial-25 credit duplicates
* 5 partial-50 credit duplicates
* 5 partial-75 credit duplicates
* 1 selected for report
* 3 satisfactory

| Handle    | Finding | Pie   | Split | Slice | Score | Award        |
| --------- | ------- | ----- | ----- | ----- | ----- | ------------ |
| warden\_2 | H-02    | 13.00 | 1     | 13.00 | 2     | 4798.84 USDC |
| warden\_c | H-01    | 0.54  | 19    | 0.6   | 2     | 22.16 USDC   |
| warden\_a | H-01    | 0.54  | 19    | 0.05  | 1     | 17.05 USDC   |
| warden\_b | H-01    | 0.54  | 19    | 0.05  | 1     | 17.05 USDC   |
| warden\_d | H-01    | 0.54  | 19    | 0.05  | 1     | 17.05 USDC   |
| warden\_n | H-01    | 0.54  | 19    | 0.03  | 0.75  | 12.79 USDC   |
| warden\_o | H-01    | 0.54  | 19    | 0.03  | 0.75  | 12.79 USDC   |
| warden\_p | H-01    | 0.54  | 19    | 0.03  | 0.75  | 12.79 USDC   |
| warden\_q | H-01    | 0.54  | 19    | 0.03  | 0.75  | 12.79 USDC   |
| warden\_r | H-01    | 0.54  | 19    | 0.03  | 0.75  | 12.79 USDC   |
| warden\_j | H-01    | 0.54  | 19    | 0.02  | 0.5   | 8.52 USDC    |
| warden\_k | H-01    | 0.54  | 19    | 0.02  | 0.5   | 8.52 USDC    |
| warden\_l | H-01    | 0.54  | 19    | 0.02  | 0.5   | 8.52 USDC    |
| warden\_m | H-01    | 0.54  | 19    | 0.02  | 0.5   | 8.52 USDC    |
| warden\_m | H-01    | 0.54  | 19    | 0.02  | 0.5   | 8.52 USDC    |
| warden\_e | H-01    | 0.54  | 19    | 0.01  | 0.25  | 4.26 USDC    |
| warden\_f | H-01    | 0.54  | 19    | 0.01  | 0.25  | 4.26 USDC    |
| warden\_g | H-01    | 0.54  | 19    | 0.01  | 0.25  | 4.26 USDC    |
| warden\_h | H-01    | 0.54  | 19    | 0.01  | 0.25  | 4.26 USDC    |
| warden\_i | H-01    | 0.54  | 19    | 0.01  | 0.25  | 4.26 USDC    |

### The "live criticals" exception

A submission matching the following criteria has special rules:

* [High severity](../competitions/severity-categorization.md#estimating-risk) or [critical](../bounties/bounty-criteria.md#critical-severity) vulnerability in LIVE contracts,
* reported using the [proper procedure](../competitions/submission-guidelines.md#how-to-submit-zero-day-or-otherwise-highly-sensitive-bugs),
* accompanied by [coded proof of concept](../competitions/submission-guidelines.md#how-to-include-a-proof-of-concept), AND
* submitted prior to the related code being fixed or the bug documented in any way potentially accessible to wardens

In order to ensure fairness and to incentivize prompt reporting of such issues, findings meeting these criteria will be the only ones in the duplicate set eligible for payout from the competitive audit pool. Submissions that meet the above criteria and are not reported via the proper procedure will not be eligible for awards.

To preserve the fairness of the competition, sponsors agree to only make fixes for high severity / critical issues submitted in this way and to refrain from fixing or leaking anything else prior to the end of the competition.

**Warning:** A false positive submitted this way which seems to have taken advantage of the system and wasted sponsor time will result in a potential ["good citizen rule"](../competitions/submission-guidelines.md#good-citizenship-is-a-requirement-for-compensation) violation.

## QA Reports

In order to incentivize wardens to focus efforts on high and medium severity findings while also ensuring quality coverage, the pool’s allocation is capped for low severity, and governance/centralization risk findings.

Low severity and governance/centralization risk findings are submitted as a **single** QA report. For more on reports, see [Judging criteria](../competitions/judging-criteria.md).

QA reports are [awarded on a curve](curve-logic.md) based on the judge’s score.

There is a very high burden of quality and value provided for QA reports. Only submissions that demonstrate full effort worthy of consideration for inclusion in the report will be eligible for rewards.

### Ranks for QA reports

After post-judging QA is complete, the Judge selects the top 3 QA reports.

The 1st, 2nd, and 3rd place winners are awarded using Code4rena's standard [curve model](curve-logic.md).

Tie votes are handled as follows:

* 3-way tie for 1st place: the QA pool is split evenly between the three 1st place winners (no 2nd or 3rd place reports).
* 2-way tie for 1st place: the awards for 1st and 2nd place are combined and split evenly among the tied reports (no 2nd place report).
* If 2 or more reports tie for 2nd place, the awards for 2nd and 3rd place are combined and split evenly among the tied reports (no 3rd place report).
* If 2 or more reports tie for 3rd place, the 3rd place awards are split evenly among the tied reports.

Satisfactory reports not among the winning reports will not be awarded -- but will count towards wardens' accuracy scores.

## Historical notes

For more context on paused submission types and past formulas for calculating awards, see [Historical context for Code4rena awards](historical-info.md)
