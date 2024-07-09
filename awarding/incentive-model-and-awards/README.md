# Incentive model and awards

To incentivize **wardens**, C4 uses a unique scoring system with two primary goals: reward participants for finding unique bugs and also to make the audit resistant to Sybil attack. A secondary goal of the scoring system is to encourage participants to form teams and collaborate.

**Judges** are incentivized to review findings and decide their severity, validity, and quality by receiving a share of the prize pool themselves.

**Note:**
* `pie` is the number of shares assigned to a unique [report](https://docs.code4rena.com/roles/wardens/submission-guidelines#qa-reports-low-governance) or [finding](https://docs.code4rena.com/roles/wardens/submission-guidelines#submission-types).
* `split` is the number of times those shares were divided, the findings count for a given group.
* `slice` is the number of shares assigned for that warden’s finding.

## High and Medium Risk bugs

Wardens are given shares for bugs discovered based on severity, and those shares give the owner a pro rata piece of the pie:

`Med Risk Slice: 3 * (0.85 ^ (split - 1)) / split`\
`High Risk Slice: 10 * (0.85 ^ (split - 1)) / split`

Please note that findings with partial credit still count as 1 finding in the algorithm. \
During awarding, each award is redeemed for: `award pool / pie / slice`.

### Bonus for best / selected for report

For each unique High or Medium finding, the submission selected for inclusion in the audit report receives a 30% slice bonus. The `pie` (total of slices) is also increased accordingly.

Let's look at an example of a set of High risk duplicates, with 3 satisfactory findings.

As per the formula, the pie would be: \
`10 * (0.85 ^ (findingCount - 1)) = 7.225`

Warden A's finding is selected for report; therefore the pie is adjusted as follows: \
`new pie = previous pie + [selected finding's slice] * 0.3` \
`=> 7.225 + ( 2.408333333333333 * 0.3 ) = 7.9475

The resulting awards are:

| **Warden**  | **finding** | **risk** |        **pie**     | **split** |      **slice**      |       **award**        |
| ----------- | ----------- | ---------| ------------------ | --------- | ------------------- | ---------------------- |
| 'Warden A [selected]'  | 'H-02'      | '3'      |     7.9475     |   3    |      3.1308333333333334  |  1040                  |
| 'Warden B'  | 'H-02'      | '3'      |     7.9475     |   3    |      2.4083333   |  800                  |
| 'Warden C'  | 'H-02'      | '3'      |     7.9475     |   3    |      2.4083333   |  800                  |

### Bonuses for top competitors
For audits starting on or after April 30, 2024, there are two bonuses for top-performing wardens/teams:

1. **Hunter bonus:** 10% of the HM pool will be awarded to the warden or team who identifies the greatest number of unique HMs.
2. **Gatherer bonus:** 10% of the HM pool will be awarded to the warden or team who identifies the greatest number of valid HMs.

Both bonuses weigh Highs more heavily than Mediums, similarly to Code4rena's standard awarding mechanism.

**Top Hunter score**
Each participant's High- and Medium-risk findings are used to calculate the Top Hunter score. The scoring logic is as follows:

- Only full-credit HM findings with fewer than 5 submissions in the findings set count towards the top hunter score.
- For each High-risk finding, score += 10 * 1/x, where x = number of duplicates 
- For each Medium-risk finding, score += 3 * 1/x, where x = number of duplicates 

For example, if a warden found: 
- 1 High-risk finding that was found by 3 other wardens, that finding's score would be 10 * 1/4 = 2.5 
- 1 unique Medium, that finding's score would be 3 * 1 += 3
- …for a total score of 5.5.

**Top Gatherer score**
The Top Gatherer score is calculated using all full-credit High- and Medium-risk findings, as follows: 

- (Number of High-risk findings for `user` / Total number of High-risk findings) * 10 = `highScore`
- (Number of Medium-risk findings for `user` / Total number of Medium-risk findings) * 3 = `mediumScore`
- `highScore` + `mediumScore` = `gathererScore`

Partial credit duplicates (see next section) do not count towards the Top Hunter / Top Gatherer scores.

### Duplicates getting partial credit

All issues which identify the same functional vulnerability will be considered duplicates regardless of effective rationalization of severity or exploit path.

However, any submissions which do not identify or effectively rationalize the top identified severity case may be judged as “partial credit” and may have their shares  divided at judge’s sole discretion (e.g. 25%, 50%, or 75% of the shares of a satisfactory submission in the duplicate set).

Awards for partial duplicates are calculated as follows: 

First, the portion of the total pie allocated to a specific slice is calculated, based on the scores of related findings:

1. Select findings that share the same `reportId` as the given slice.
2. Calculate total credit - for each finding in the filtered group:
  - Add the score to totalCredit if the score is ≤ 1
  - Add 1.3 to totalCredit if the score is > 1
3. Calculate slice credit, based on the slice score of each finding in the filtered group:
  - If the score is 2, set sliceCredit to 1.3
  - If the score is 1, set sliceCredit to 1
  - If the score is < 1, set sliceCredit to the score (Partials -> 0.25, 0.5, 0.75)
  - If the score is 0, return 0
4. Compute the portion as `portion = slice.pie * (sliceCredit/totalCredit)`

Next, the award is calculated using `award = (portion/mainSliceTotal) * prize.mainPool`. (In the code, `mainPool` refers to the HM pool.)


### Validator-improved submissions

*Validator improvements are paused until further notice.*

[Validators](https://docs.code4rena.com/roles/certified-contributors/validators.md) may enhance submissions (add PoC, increase quality of report, etc.) in exchange for a % of the finding’s payout. 

For Validator-improved submissions: if the judge believes the validator added a measurable enhancement, they get a split of the value of the issue:
- 25% cut → small enhancement
- 50% cut → med enhancement
- 75% cut → large enhancement

## QA and Gas Optimization Reports

In order to incentivize wardens to focus efforts on high and medium severity findings while also ensuring quality coverage, the pool’s allocation is capped for low severity, governance/centralization risk, and gas optimization findings.

Low severity and governance/centralization risk findings are submitted as a **single** QA report. Similarly, gas optimizations are submitted as a single gas report. For more on reports, see [Judging criteria](/awarding/judging-criteria/README.md).

QA and gas optimization reports are awarded on a curve based on the judge’s score.

- QA reports compete for a share of 4% of the prize pool (e.g. $2,000 for a $50,000 audit);
- The gas optimization pool varies from audit to audit;
- QA and Gas optimization reports are awarded on a curve.

There is a very high burden of quality and value provided for QA and gas optimization reports. Only submissions that demonstrate full effort worthy of consideration for inclusion in the report will be eligible for rewards.

### Ranks for QA and Gas reports

After post-judging QA is complete, the Judge and Validators vote to select the top 3 QA reports and Gas reports. (In the case of a tie vote, there may be a 4th place report.)

The 1st, 2nd, and 3rd place winners are awarded using a curve model that will be documented here ASAP. 

Tie votes are handled as follows:
- 3-way tie for 1st place: the QA/Gas pool is split evenly between the three 1st place winners (no 2nd or 3rd place reports).
- 2-way tie for 1st place: the awards for 1st and 2nd place are combined and split evenly among the tied reports (no 2nd place report).
- If 2 or more reports tie for 2nd place, the awards for 2nd and 3rd place are combined and split evenly among the tied reports (no 3rd place report).
- If 2 or more reports tie for 3rd place, the 3rd place awards are split evenly among the tied reports.

Satisfactory reports not among the winning reports will not be awarded -- but will count towards wardens' accuracy scores.

In the unlikely event that zero high- or medium-risk vulnerabilities are found, the HM award pool will be divided among all satisfactory QA reports based on the QA Report curve, **unless otherwise stated in the audit repo.** 

## Satisfactory / unsatisfactory submissions

Any submissions deemed unsatisfactory are ineligible for awards, and count against wardens' accuracy scores.

The bar for satisfactory submissions is that they are roughly at a level that could be found in a draft report by a professional auditor: specifically on the merits of technical substance, with writing quality considered only where it interferes with comprehension of the technical message.

It is possible for a submission to be *technically* valid and still unsatisfactory. An “unsatisfactory” submission may meet any of these criteria:

- incorrect
- low/incomplete effort
- out of scope
- clearly overinflated severity
- proof of concept does not pass the burden of proof test
- approach is disrespectful of sponsors’ and judges’ time in some way

Any submissions that appear to be direct copies of other reports in the current audit will be collectively deemed unsatisfactory.

## Historical notes

For more context on paused submission types and past formulas for calculating awards, see [Historical context for Code4rena awards](/incentive-model-and-awards/historical-info.md)