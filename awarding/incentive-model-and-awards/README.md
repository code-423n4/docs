# Incentive model and awards

To incentivize **wardens**, C4 uses a unique scoring system with two primary goals: reward contestants for finding unique bugs and also to make the contest resistant to Sybil attack. A secondary goal of the scoring system is to encourage contestants to form teams and collaborate.

**Judges** are incentivized to review findings and decide their severity, validity, and quality by receiving a share of the prize pool themselves.

## High and Medium Risk bugs

Contestants are given shares for bugs discovered based on severity, and those shares give the owner a pro rata piece of the pot:

`Med Risk Shares: 3 * (0.9 ^ (findingCount - 1)) / findingCount`\
`High Risk Shares: 10 * (0.9 ^ (findingCount - 1)) / findingCount`

During awarding, each share is redeemed for: `pot / number of shares`. 

### Bonus for best / selected for report

For each unique High or Medium finding, the submission selected for inclusion in the audit report receives a 30% share bonus.

### Duplicates getting partial credit

All issues which identify the same functional vulnerability will be considered duplicates regardless of effective rationalization of severity or exploit path.

However, any submissions which do not identify or effectively rationalize the top identified severity case may be judged as “partial credit” and may have their shares in that finding’s pie divided by 2 or 4 at judge’s sole discretion (e.g. 50% or 25% of the shares of a satisfactory submission in the duplicate set).


## QA and Gas Optimization Reports

In order to incentivize wardens to focus efforts on high and medium severity findings while also ensuring quality coverage, the pool’s allocation is capped for low severity, non-critical, and gas optimization findings.

Low and non-critical findings are submitted as a **single** QA report. Similarly, gas optimizations are submitted as a single gas report. For more on reports, see [Judging criteria](/awarding/judging-criteria/README.md).

QA and gas optimization reports are awarded on a curve based on the judge’s score.

- QA reports compete for a share of 5% of the prize pool (e.g. $2,500 for a $50,000 contest);
- The gas optimization pool varies from contest to contest, but is typically 5% of the total prize pool (e.g. $2,500 for a $50,000 contest);
- QA and Gas optimization reports are scored by judges using A/B/C grades (with C = unsatisfactory), and awarded on a curve.

There is a very high burden of quality and value provided for QA and gas optimization reports. Only submissions that demonstrate full effort worthy of consideration for inclusion in the report will be eligible for rewards.

It is highly recommended to clearly spell out the impact of proposed gas optimizations.

Historically, Code4rena valued non-critical findings at 0; the intent of the QA report is not to increase the value of non-criticals, but rather to allow them to be consolidated in reports alongside low severity issues.

**Note:** Contests pre-dating February 3, 2022 awarded low risk and gas optimization shares as: `Low Risk Shares: 1 * (0.9 ^ (findingCount - 1)) / findingCount`

### Grades for QA and Gas reports

Gas reports and QA reports are graded A, B, or C. 

C scores are unsatisfactory and ineligible for awards. 

Judges choose the best QA report and best Gas report, each of which earns the same 30% share bonus as described under "High and Medium Risk bugs."

All A-grade reports receive a score of 2; All B-grade reports get a 1. Awarding for QA and Gas reports is on a curve that's described [here](https://docs.code4rena.com/awarding/incentive-model-and-awards/curve-logic).


## Satisfactory / unsatisfactory submissions

Any submissions deemed unsatisfactory are ineligible for awards.

The bar for satisfactory submissions is that they are roughly at a level that could be found in a draft report by a professional auditor: specifically on the merits of technical substance, with writing quality considered only where it interferes with comprehension of the technical message. 

It is possible for a submission to be *technically* valid and still unsatisfactory. An “unsatisfactory” submission may meet any of these criteria:

- incorrect
- low/incomplete effort
- out of scope
- clearly overinflated severity
- proof of concept does not pass the burden of proof test
- approach is disrespectful of sponsors’ and judges’ time in some way

Any submissions that appear to be direct copies of other reports in the current audit will be collectively deemed unsatisfactory.
