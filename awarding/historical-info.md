# Historical context for Code4rena awards

## Submission types paused

The following submission types are deprecated:

### Gas optimization reports

- Gas reports should be submitted using the same approach as QA reports: a single submission per warden (or team) which includes all identified optimizations.
- It is highly recommended to clearly spell out the impact of proposed gas optimizations.
- Submissions that claim gas optimization when the optimizer is inactive will be considered invalid.

### Bot reports

The first hour of each Code4rena audit is devoted to a bot race, to incentivize high quality automated findings as the first wave of the audit.

- The winning bot report is selected and shared with all wardens within 24 hours of the audit start time.
- The full set of issues identified by the best automated tools are considered out of scope for the audit and ineligible for awards.

Doing this eliminates the enormous overlapping effort of all wardens needing to document common low-hanging issues And because the best bot report is shared with auditors at the start of the audit, these findings serve as a thorough starting place for understanding the codebase and where weaknesses may exist.

**Ultimately, the bot race ensures human auditors are focused on things humans can do.**

By designating a portion of the pool in this direction, Code4rena creates a separate lane for the significant investment of effort that many auditors already make in automated tooling -- and rather than awarding 100 people for identifying the same issue, we award the best automated tools.

### Analyses

An analysis is a written submission outlining:

- Wardens' analysis of the codebase as a whole and any observations or advice they have about architecture, mechanism, or approach
- Broader concerns like systemic risks or centralization risks
- The approach taken in reviewing the code
- New insights and learnings from the audit

If individual findings are trees, Analyses are the forest. They provide wardens with an opportunity to contribute value through high level insights and advice that aren't necessarily covered by specific bugs -- and a way to get credit for doing so.

Each Analysis is judged based on quality and thoroughness as compared with other Analyses, with awards distributed on a curve. Wardens are encouraged to read the top-scoring Analyses from past Code4rena audits, which are highlighted in [C4's audit reports](https://code4rena.com/reports).

Analyses are judged A, B, or C, with C being unsatisfactory and ineligible for awards. The judge selects the best Analysis for inclusion in the audit report.

The Autumn 2023 Supreme Court session provided further judging guidelines for Analyses, saying they should provide "[actionable] insight on improvement steps of outlined characteristics." 

Areas of interest include:
- Full representation of the project’s risk model:
  - Admin abuse risks
  - Systemic risks
  - Technical risks
  - Integration risks
  - Non-standard token risks (if in scope)
- Software engineering considerations
- In-depth architecture assessment of business logic 
- Testing suite
- Weakspots and any single points of failure

Merely repeating the code functionality in pseudo-documentation is not considered valuable information.


## Understanding historical grading for QA, Gas, and Analysis reports

For audits that started after October 13, 2022 and before April 30, 2024: 

- Analyses, QA reports and Gas reports in this time period were graded A, B, or C.
- C scores are unsatisfactory and ineligible for awards.
- All A-grade reports receive a score of 2; All B-grade reports get a 1. Awarding for QA and Gas reports is on a curve that's described [here](/awarding/curve-logic.md).
- Judges choose the best report in each category (Analysis, QA report, and Gas report), each of which earns the same 30% share bonus described under "High and Medium Risk bugs."

**Note:** if the `selected for report` submission has a B-grade label, it will still be treated as A-grade and given proportionally more than B-grade, plus the 30% bonus for being `selected for report`.

## QA/Gas curve for audits prior to April 30, 2024

For Code4rena audits that started after October 13, 2022 and before April 30, 2024, the QA/Gas curve logic worked as follows.

Reports were graded based on 3 different grades:
* Grade-a: outstanding report.
* Grade-b: satisfactory report.
* Grade-c: unsatisfactory report.

Each grade will be allocated a portion of the pool, with a decrementer of 0.6 between, and steps of 0.2.

Audits pre-dating February 3, 2022 awarded low risk and gas optimization shares as: `Low Risk Shares: 1 * (0.9 ^ (findingCount - 1)) / findingCount`

### Can I see some examples of how awards work?

Awards for each audit are [posted on the Code4rena website](https://code4rena.com/contests). See [Numoen](https://code4rena.com/contests/2023-01-numoen-contest), for example. The award calculation for Numoen had the following parameters:

* **Total awards: 50,000 USDC**
* Main award pool: 42,500 USDC
* QA pool: 5,000 USDC
* Gas pool: 2,500 USDC

The table below shows each unique high and medium severity finding (`H-XX`, `M-XX`), QA report (`Q-XX`), gas optimization report (`G-XX`), and the way each submission’s award was calculated:

* `pie` is the number of shares assigned to that report or finding
* `split` is the number of times those shares were divided
* `slice` is the number of shares assigned for that warden’s finding
* each `award` is calculated by `shares * (pot / number_of_shares)`

**Tribe Turbo awards**

| **handle**       | **finding** | **risk** |        **pie**     | **split** |      **slice**      |       **award**        |
| ---------------- | ----------- | -------- | ------------------ | --------- | ------------------- | ---------------------- |
| 'hansfriese'     | 'H-01'      | '3'      |         13         |   1       |         13          | 17615.514252816203     |
| 'RaymondFam'     | 'M-01'      | '2'      | 2.0863980000000004 |   5       | 0.5117580000000002  | 693.4523340763628      |
| '0xhacksmithh'   | 'M-01'      | '2'      | 2.0863980000000004 |   5       | 0.39366000000000007 |  533.424872366433      |
| 'Deivitto'       | 'M-01'      | '2'      | 2.0863980000000004 |   5       | 0.39366000000000007 |  533.424872366433      |
| 'rvierdiiev'     | 'M-01'      | '2'      | 2.0863980000000004 |   5       | 0.39366000000000007 |  533.424872366433      |
| 'peakbolt'       | 'M-01'      | '2'      | 2.0863980000000004 |   5       | 0.39366000000000007 |  533.424872366433      |
| 'hansfriese'     | 'M-02'      | '2'      |        3.9         |   1       | 3.9000000000000004  | 5284.654275844861      |
| 'Allarious'      | 'M-03'      | '2'      |        3.9         |   1       | 3.9000000000000004  | 5284.654275844861      |
| 'hansfriese'     | 'M-04'      | '2'      | 3.1050000000000004 |   2       | 1.7550000000000001  | 2378.0944241301877     |
| 'peakbolt'       | 'M-05'      | '2'      |       2.268        |   3       | 1.0530000000000002  | 1426.8566544781127     |
| 'nadin'          | 'M-04'      | '2'      | 3.1050000000000004 |   2       |        1.35         | 1829.3034031770674     |
| 'adeolu'         | 'M-05'      | '2'      |       2.268        |   3       |        0.405        | 548.7910209531202      |
| 'rvierdiiev'     | 'M-05'      | '2'      |       2.268        |   3       |        0.81         | 1097.5820419062404     |
| 'Breeje'         | 'M-06'      | '2'      | 3.1050000000000004 |   2       |        1.35         | 1829.3034031770674     |
| 'ladboy233'      | 'M-06'      | '2'      | 3.1050000000000004 |   2       | 1.7550000000000001  | 2378.0944241301877     |
| 'Deivitto'       | 'G-01'      | 'g'      |  86.5490783392284  |  15       |  5.76993855594856   | 45.42556528683028      |
| 'Aymen0909'      | 'G-02'      | 'g'      |  86.5490783392284  |  15       |  5.76993855594856   | 45.42556528683028      |
| 'matrix_0wl'     | 'G-03'      | 'g'      |  86.5490783392284  |  15       |  5.76993855594856   | 45.42556528683028      |
| 'RaymondFam'     | 'G-04'      | 'g'      |  86.5490783392284  |  15       |  5.76993855594856   | 45.42556528683028      |
| 'c3phas'         | 'G-05'      | 'g'      |        140         |   2       |         70          | 551.0959153628928      |
| 'Rageur'         | 'G-06'      | 'g'      |  86.5490783392284  |  15       |  5.76993855594856   | 45.42556528683028      |
| 'nadin'          | 'G-07'      | 'g'      |  86.5490783392284  |  15       |  5.76993855594856   | 45.42556528683028      |
| 'IllIllI'        | 'G-08'      | 'g'      |        140         |   2       |         70          | 551.0959153628928      |
| 'cryptostellar5' | 'G-09'      | 'g'      |  86.5490783392284  |  15       |  5.76993855594856   | 45.42556528683028      |
| 'Diana'          | 'G-10'      | 'g'      |  86.5490783392284  |  15       |  5.76993855594856   | 45.42556528683028      |
| 'antonttc'       | 'G-11'      | 'g'      |  86.5490783392284  |  15       |  5.76993855594856   | 45.42556528683028      |
| '0xackermann'    | 'G-12'      | 'g'      |  86.5490783392284  |  15       |  5.76993855594856   | 45.42556528683028      |
| '0xSmartContract'| 'G-13'      | 'g'      |  86.5490783392284  |  15       |  5.76993855594856   | 45.42556528683028      |
| 'ReyAdmirado'    | 'G-14'      | 'g'      |  86.5490783392284  |  15       |  5.76993855594856   | 45.42556528683028      |
| 'NoamYakov'      | 'G-15'      | 'g'      |         91         |   1       |         91          | 716.4246899717607      |
| 'Rolezn'         | 'G-16'      | 'g'      |  86.5490783392284  |  15       |  5.76993855594856   | 45.42556528683028      |
| 'oyc_109'        | 'G-17'      | 'g'      |  86.5490783392284  |  15       |  5.76993855594856   | 45.42556528683028      |
| 'arialblack14'   | 'G-18'      | 'g'      |  86.5490783392284  |  15       |  5.76993855594856   | 45.42556528683028      |
| 'matrix_0wl'     | 'Q-01'      | 'q'      | 38.296345887055885 |   5       |  7.659269177411177  | 142.48406332285143     |
| 'SleepingBugs'   | 'Q-02'      | 'q'      | 38.296345887055885 |   5       |  7.659269177411177  | 142.48406332285143     |
| 'CodingNameKiki' | 'Q-03'      | 'q'      |       69.68        |   1       |        69.68        | 1296.2450205584805     |
| 'IllIllI'        | 'Q-04'      | 'q'      |       160.8        |   3       |        53.6         | 997.1115542757543      |
| '0xAgro'         | 'Q-05'      | 'q'      | 38.296345887055885 |   5       |  7.659269177411177  | 142.48406332285143     |
| '0xSmartContract'| 'Q-06'      | 'q'      |       160.8        |   3       |        53.6         | 997.1115542757543      |
| 'btk'            | 'Q-07'      | 'q'      |       160.8        |   3       |        53.6         | 997.1115542757543      |
| 'chrisdior4'     | 'Q-08'      | 'q'      | 38.296345887055885 |   5       |  7.659269177411177  | 142.48406332285143     |
| 'Rolezn'         | 'Q-09'      | 'q'      | 38.296345887055885 |   5       |  7.659269177411177  | 142.48406332285143     |


## Partial credit duplicates prior to April 2024

For audits that started after October 13, 2022 and before April 30, 2024, the math for partial-credit duplicates was handled as described below. 

Let's first review an example of a duplicate group *without* partial findings.

| **Warden**  | **finding** | **risk** |        **pie**     | **split** |      **slice**      |       **award**        |
| ----------- | ----------- | ---------| ------------------ | --------- | ------------------- | ---------------------- |
| 'Warden A'  | 'H-02'      | '3'      |         8.91       |   3       |         3.51        |  1300                  |
| 'Warden B'  | 'H-02'      | '3'      |         8.91       |   3       |         2.70        |  1000                  |
| 'Warden C'  | 'H-02'      | '3'      |         8.91       |   3       |         2.70        |  1000                  |


Now, let's compare to a group of three high findings where two of the duplicate findings are identified as `partial-25`: the findings from wardens B and C.
Let's see how the pie and slices evolve.

| **Warden**  | **finding** | **risk** |        **pie**     | **split** |      **slice**      |       **award**        |
| ----------- | ----------- | ---------| ------------------ | --------- | ------------------- | ---------------------- |
| 'Warden A'  | 'H-01'      | '3'      |         4.86       |   3       |         3.51        |  1300                  |
| 'Warden B'  | 'H-01'      | '3'      |         4.86       |   3       |        0.675        |  250                   |
| 'Warden C'  | 'H-01'      | '3'      |         4.86       |   3       |        0.675        |  250                   |

The pie allocated to that findings group is adjusted accordingly so the award of the full-credit findings remains constant; only the partial findings' award is adjusted.

Let's compare another two sets of duplicates.

1. Group A:
  - 3 full-credit findings
  - Warden A's finding is selected for report
2. Group B:
  - Warden A's finding is selected for report
  - Warden B's finding is a full-credit duplicate
  - Warden C's finding is a partial-credit (`partial-25`) duplicate

**Group A**
| **Warden**  | **finding** | **risk** |        **pie**     | **split** |      **slice**      |       **award**        |
| ----------- | ----------- | ---------| ------------------ | --------- | ------------------- | ---------------------- |
| 'Warden A'  | 'M-02'      | '2'      |         2.673      |   3       |        1.0530       |  1300                  |
-> selected
| 'Warden B'  | 'M-02'      | '2'      |         2.673      |   3       |        0.81         |  1000                  |
-> full credit
| 'Warden C'  | 'M-02'      | '2'      |         2.673      |   3       |        0.81         |  1000                  |
-> full credit


**Group B**
| **Warden**  | **finding** | **risk** |        **pie**     | **split** |      **slice**      |       **award**        |
| ----------- | ----------- | ---------| ------------------ | --------- | ------------------- | ---------------------- |
| 'Warden A'  | 'M-01'      | '2'      |         2.0655     |   3       |        1.0530       |  1300                  |
-> selected
| 'Warden B'  | 'M-01'      | '2'      |         2.0655     |   3       |        0.81         |  1000                  |
-> full credit
| 'Warden C'  | 'M-01'      | '2'      |         2.0655     |   3       |        0.2025       |  250                   |
-> partial credit

We can see here that the logic behind the `partial-` labels only impacts the awards for partial findings; even though the pies vary, the awards stay the same.

**Conclusion:**

Only the award amounts for "partial" findings have been reduced, in line with expectations. The aim of this adjustment is to recalibrate the rewards allocated for these specific findings. Meanwhile, the awards for full-credit findings remain unchanged.

## Z Pools and Dark Horse bonuses

If a Z pool is listed among an audit's award pools, then it has a Z pool, which may be repurposed (in part or whole) as a Dark Horse pool. For audits with a Z pool: 

- `n` [Zenith](https://www.zenith.security/) Researchers (ZRs) are designated as leads for the audit ("LZRs"), with teams counting as one.
- Z pool is split among LZRs based on their [Gatherer score](/awarding#bonuses-for-top-competitors), using the [ranked curve](/awarding/curve-logic)
- LZRs also compete for a portion of HM awards and are eligible for Hunter/Gatherer bonuses

### Dark Horse bonus pool

Dark Horse is (1) a non-LZR who (2) finishes in the top `n + 3`, and (3) outperforms (or ties) the top-ranked LZR auditor based on [Gatherer score](/awarding#bonuses-for-top-competitors) 

Dark Horse awards come out of the Z pool.

- If an LZR ranks outside the top `n` (by [Top Gatherer score](/awarding#bonuses-for-top-competitors)):
    - 50% of their share of the Z pool goes to the Dark Horse bonus pool
- If an LZR ranks outside the top `n + 3` (by [Top Gatherer score](/awarding#bonuses-for-top-competitors)):
    - The LZR forfeits their share of the Z pool (but are still eligible for HM / QA awards)
    - 50% of their share of the Z pool goes to the Dark Horse bonus pool
    - 50% of their share of the Z pool is refunded to sponsor
- Dark Horse awards are distributed using C4’s ranked curve.

### Specific edge cases:

- If no lead ranks outside the top `n`, no Dark Horse bonus is awarded.
- In the event that no LZRs rank in the top `n + 3` the Dark Horse pool will be distributed, but only the top `n` ranked competitors will earn the Dark Horse achievement for the competition.
- Any unused portion of the Z pool is returned to the Sponsor

## Dark Horse bonuses: ranked curve awarding

[Dark Horse bonuses](#z-pools-and-dark-horse-bonuses) are calculated using the same ranked curve as QA and Gas reports -- except that in lieu of assigning points for each rank (1, 2, 3), the number of ranks is flexible. 

### Sample output with 2 Dark Horse winners

Using a Dark Horse bonus pool of $10,000:

| warden rank | shares     | award     | 
| ----------- | ---------- | --------- | 
| 1           | 1.5        | $6,000.00 |
| 2           | 1 	       | $4,000.00 |

### Sample output with 3 Dark Horse winners

Using a Dark Horse bonus pool of $10,000:

| warden rank | shares     | award     | 
| ----------- | ---------- | --------- | 
| 1           | 2.25       | $4,736.84 |
| 2           | 1.5	       | $3,157.89 |
| 3           | 1          | $2,105.26 |

### Sample output with 5 Dark Horse winners

Using a Dark Horse bonus pool of $10,000:

| warden rank | shares     | award     | 
| ----------- | ---------- | --------- | 
| 1           | 5.0625     | $3,838.86 |
| 2           | 3.375	     | $2,559.24 |
| 3           | 2.25       | $1,706.16 |
| 4           | 1.5        | $1,137.44 |
| 5           |	1          |   $758.29 |
