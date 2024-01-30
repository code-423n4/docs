# Incentive model and awards

To incentivize **wardens**, C4 uses a unique scoring system with two primary goals: reward contestants for finding unique bugs and also to make the audit resistant to Sybil attack. A secondary goal of the scoring system is to encourage contestants to form teams and collaborate.

**Judges** are incentivized to review findings and decide their severity, validity, and quality by receiving a share of the prize pool themselves.

**Note:**
* `pie` is the number of shares / slice assigned to that report or finding.
* `split` is the number of times those shares were divided, the findings count for a given group.
* `slice` is the number of shares assigned for that warden’s finding.

## High and Medium Risk bugs

Contestants are given shares for bugs discovered based on severity, and those shares give the owner a pro rata piece of the pie:

`Med Risk Slice: 3 * (0.9 ^ (split - 1)) / split`\
`High Risk Slice: 10 * (0.9 ^ (split - 1)) / split`

Please note that findings with partial credit as still count as 1 finding in the algorithm. \
During awarding, each award is redeemed for: `award pool / pie / slice`.

### Bonus for best / selected for report

For each unique High or Medium finding, the submission selected for inclusion in the audit report receives a 30% slice bonus. \
The `pie` ( total of slices ) will be also increased accordingly as well as the slice of this finding.

Let's see an example of a group of set of High risk duplicates, with 3 satisfactory findings.

As per the formula, the pie would be: \
`10 * (0.9 ^ (findingCount - 1)) = 8.10`

However, the warden A has its findings selected for report, therefore the pie will be adapted as follows: \
`new pie = previous pie + [selected finding's slice] * 0.3` \
`=> 8.91 = 8.1 + ( 2.7 * 0.3 )`

So the result would be:

| **Warden**  | **finding** | **risk** |        **pie**     | **split** |      **slice**      |       **award**        |
| ----------- | ----------- | ---------| ------------------ | --------- | ------------------- | ---------------------- |
| 'Warden A'  | 'H-02'      | '3'      |         8.91       |   3       |         3.51        |  1300                  |
| 'Warden B'  | 'H-02'      | '3'      |         8.91       |   3       |         2.70        |  1000                  |
| 'Warden C'  | 'H-02'      | '3'      |         8.91       |   3       |         2.70        |  1000                  |

### Duplicates getting partial credit

All issues which identify the same functional vulnerability will be considered duplicates regardless of effective rationalization of severity or exploit path.

However, any submissions which do not identify or effectively rationalize the top identified severity case may be judged as “partial credit” and may have their shares  divided at judge’s sole discretion (e.g. 25%, 50%, or 75% of the shares of a satisfactory submission in the duplicate set).

Let's see an example of a duplicate group without partial findings.

| **Warden**  | **finding** | **risk** |        **pie**     | **split** |      **slice**      |       **award**        |
| ----------- | ----------- | ---------| ------------------ | --------- | ------------------- | ---------------------- |
| 'Warden A'  | 'H-02'      | '3'      |         8.91       |   3       |         3.51        |  1300                  |
| 'Warden B'  | 'H-02'      | '3'      |         8.91       |   3       |         2.70        |  1000                  |
| 'Warden C'  | 'H-02'      | '3'      |         8.91       |   3       |         2.70        |  1000                  |


Now, let's compare to a group of 3 high findings, 2 of them are identified as partial-25. Findings from warden B & C.
Let's see how the pie and slices evolves.

| **Warden**  | **finding** | **risk** |        **pie**     | **split** |      **slice**      |       **award**        |
| ----------- | ----------- | ---------| ------------------ | --------- | ------------------- | ---------------------- |
| 'Warden A'  | 'H-01'      | '3'      |         4.86       |   3       |         3.51        |  1300                  |
| 'Warden B'  | 'H-01'      | '3'      |         4.86       |   3       |        0.675        |  250                   |
| 'Warden C'  | 'H-01'      | '3'      |         4.86       |   3       |        0.675        |  250                   |

The pie allocated to that findings group will be adapted accordingly so the award of the non-partials findings will remain equal, only the partial findings' award will be adapted.


**Conclusion:**

Only the award amounts for "partial" findings have been reduced, in line with expectations. The aim of this adjustment is to recalibrate the rewards allocated for these specific findings. Meanwhile, the awards for the fully validated findings remain unchanged.

## Bot races

The first hour of each Code4rena audit is devoted to a bot race, to incentivize high quality automated findings as the first wave of the audit.

- The winning bot report is selected and shared with all wardens within 24 hours of the audit start time.
- The full set of issues identified by the best automated tools are considered out of scope for the audit and ineligible for awards.

Doing this eliminates the enormous overlapping effort of all wardens needing to document common low-hanging issues And because the best bot report is shared with auditors at the start of the audit, these findings serve as a thorough starting place for understanding the codebase and where weaknesses may exist.

**Ultimately, the bot race ensures human auditors are focused on things humans can do.**

By designating a portion of the pool in this direction, Code4rena creates a separate lane for the significant investment of effort that many auditors already make in automated tooling -- and rather than awarding 100 people for identifying the same issue, we award the best automated tools.

## Analyses

Each warden is encouraged to submit an Analysis alongside their findings for each audit, to share high-level advice and insights from their review of the code.

Where individual findings are the "trees" in an audit, the Analysis is a "forest"-level view.

Advanced-level Analyses compete for a portion of each audit's award pool, and are graded and awarded similarly to QA and Gas Optimization reports.


## QA and Gas Optimization Reports

In order to incentivize wardens to focus efforts on high and medium severity findings while also ensuring quality coverage, the pool’s allocation is capped for low severity, non-critical, and gas optimization findings.

Low and non-critical findings are submitted as a **single** QA report. Similarly, gas optimizations are submitted as a single gas report. For more on reports, see [Judging criteria](/awarding/judging-criteria/README.md).

QA and gas optimization reports are awarded on a curve based on the judge’s score.

- QA reports compete for a share of 2.5% of the prize pool (e.g. $1,250 for a $50,000 audit);
- The gas optimization pool varies from audit to audit, but is typically 2.5% of the total prize pool (e.g. $1,250 for a $50,000 audit);
- QA and Gas optimization reports are scored by judges using A/B/C grades (with C = unsatisfactory), and awarded on a curve.

There is a very high burden of quality and value provided for QA and gas optimization reports. Only submissions that demonstrate full effort worthy of consideration for inclusion in the report will be eligible for rewards.

It is highly recommended to clearly spell out the impact of proposed gas optimizations.

Historically, Code4rena valued non-critical findings at 0; the intent of the QA report is not to increase the value of non-criticals, but rather to allow them to be consolidated in reports alongside low severity issues.

**Note:** Audits pre-dating February 3, 2022 awarded low risk and gas optimization shares as: `Low Risk Shares: 1 * (0.9 ^ (findingCount - 1)) / findingCount`

In the unlikely event that zero high- or medium-risk vulnerabilities are found, the HM award pool will be divided based on the QA Report curve.

## Grades for Analyses, QA and Gas reports

Analyses, QA reports and Gas reports are graded A, B, or C.

C scores are unsatisfactory and ineligible for awards.

All A-grade reports receive a score of 2; All B-grade reports get a 1. Awarding for QA and Gas reports is on a curve that's described [here](https://docs.code4rena.com/awarding/incentive-model-and-awards/curve-logic).

### Bonus for best / selected for report
Judges choose the best report in each category (Analysis, QA report, and Gas report), each of which earns the same 30% share bonus described under "High and Medium Risk bugs."

**Note:** if the `selected for report` submission has a B-grade label, it will still be treated as A-grade and given proportionally more than B-grade, plus the 30% bonus for being `selected for report`.

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
