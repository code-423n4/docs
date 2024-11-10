# Historical context for Code4rena awards

## Submission types paused

As of April 30, 2024, the following submission types are paused:

### Bot reports

The first hour of each Code4rena audit is devoted to a bot race, to incentivize high quality automated findings as the first wave of the audit.

- The winning bot report is selected and shared with all wardens within 24 hours of the audit start time.
- The full set of issues identified by the best automated tools are considered out of scope for the audit and ineligible for awards.

Doing this eliminates the enormous overlapping effort of all wardens needing to document common low-hanging issues And because the best bot report is shared with auditors at the start of the audit, these findings serve as a thorough starting place for understanding the codebase and where weaknesses may exist.

**Ultimately, the bot race ensures human auditors are focused on things humans can do.**

By designating a portion of the pool in this direction, Code4rena creates a separate lane for the significant investment of effort that many auditors already make in automated tooling -- and rather than awarding 100 people for identifying the same issue, we award the best automated tools.

### Analyses

Analyses share high-level advice and insights from wardens' review of the code.

Where individual findings are the "trees" in an audit, the Analysis is a "forest"-level view.

Analyses compete for a portion of each audit's award pool, and are graded and awarded similarly to QA and Gas Optimization reports.

## Understanding historical grading for QA, Gas, and Analysis reports

For audits that started after October 13, 2022 and before April 30, 2024: 

- Analyses, QA reports and Gas reports in this time period were graded A, B, or C.
- C scores are unsatisfactory and ineligible for awards.
- All A-grade reports receive a score of 2; All B-grade reports get a 1. Awarding for QA and Gas reports is on a curve that's described [here](https://docs.code4rena.com/awarding/incentive-model-and-awards/curve-logic).
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