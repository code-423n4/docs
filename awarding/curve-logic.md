---
icon: ranking-star
---

# Ranked curve model

Code4rena's ranked curve is used to calculate rank-based award distributions, including:

* [QA reports](./#ranks-for-qa-and-gas-reports)
* Historically, [Gas reports](historical-info.md#gas-optimization-reports) and [Dark Horse bonuses](historical-info.md#dark-horse-bonus-pool)

## If there are tied ranks

If two or more wardens (or teams) have tied ranks, they split the _total_ awards for the ranks they would otherwise occupy — i.e. if two wardens tie for 2nd place, they split the total awards for 2nd and 3rd place. Or if three wardens tie for 3rd, they split the total awards for 3rd place.

## QA reports: ranked curve awarding

QA reports are [ranked and graded as described here](./#ranks-for-qa-reports):

* 1st place (score: 5)
* 2nd place (score: 4)
* 3rd place (score: 3)
* `grade-a` and `grade-b` (score: 0, except in rare cases -- see below)
* `grade-c` (score: 0)

In most cases, only 1st, 2nd, and 3rd place reports are eligible for awards. See "If there are no valid HM findings" below for an exception.

* Reports (referred to as `findings` in the code) are sorted in descending order based on their scores. Findings without a score are treated as having a score of 0.
* For each report, a point value is calculated using the formula `qaAndGasConstant^(2 - idx)`, where `qaAndGasConstant` is defined in the `qaAndGasRanking` code (see example below), and `idx` is the index of the report in the sorted array. This means the highest-scored report gets the highest point value, decreasing exponentially for subsequent reports.
* **Pie** - The total value of the pie is the sum of all point values.
* **Mapping score to points** - unique score is mapped to an array of point values associated with findings that have that score.
* **Slice for each score** - sum the points for each score to determine the slice size for each score.
* **Split** - number of reports sharing the same score

### Sample output

| issueID | reportID | risk | score       | award              |
| ------- | -------- | ---- | ----------- | ------------------ |
| 13      | `Q-01`   | Q    | "1st place" | 3552.6315789473683 |
| 207     | `Q-02`   | Q    | "2nd place" | 2368.4210526315787 |
| 42      | `Q-03`   | Q    | "3rd place" | 1578.9473684210525 |

#### Sample input with ties for 1st place

```
  {
    number: 4,
    risk: 'q',
    labels: '["QA (Quality Assurance)","Q-08","3rd place"]'
  },
  {
    number: 28,
    risk: 'q',
    labels: '["QA (Quality Assurance)","Q-16","1st place"]'
  },
  {
    number: 113,
    risk: 'q',
    labels: '["QA (Quality Assurance)","Q-19","1st place"]'
  }
```

#### Sample output with ties for 1st place

| issueID | reportID | risk | pie  | split | slice | score | award              |
| ------- | -------- | ---- | ---- | ----- | ----- | ----- | ------------------ |
| 4       | `Q-08`   | Q    | 4.75 | 1     | 1     | 3     | 1578.9473684210525 |
| 28      | `Q-16`   | Q    | 4.75 | 2     | 3.75  | 5     | 2960.5263157894738 |
| 113     | `Q-19`   | Q    | 4.75 | 2     | 3.75  | 5     | 2960.5263157894738 |

### If there are no valid HM findings

In the unlikely event that zero high- or medium-risk vulnerabilities are found, all satisfactory reports without a 1st/2nd/3rd place rank will be assigned a `score` according to grade -- `grade-a` receives a score of `2`, and `grade-b` receives a score of `1` -- and the HM award pool is divided among all satisfactory QA reports based on the QA report curve, _unless otherwise stated in the audit repo._

#### Sample input (distribution to all satisfactory QA)

```
  [
    { score: 2, issueId: 4, reportId: 'Q-08' },
    { score: 1, issueId: 28, reportId: 'Q-16' },
    { score: 1, issueId: 113, reportId: 'Q-19' },
    { score: 1, issueId: 135, reportId: 'Q-18' },
    { score: 1, issueId: 144, reportId: 'Q-15' },
    { score: 1, issueId: 314, reportId: 'Q-17' },
    { score: 2, issueId: 337, reportId: 'Q-14' },
    { score: 1, issueId: 471, reportId: 'Q-13' },
    { score: 2, issueId: 534, reportId: 'Q-12' },
    { score: 2, issueId: 544, reportId: 'Q-10' },
    { score: 3, issueId: 548, reportId: 'Q-11' },
    { score: 1, issueId: 664, reportId: 'Q-09' },
    { score: 1, issueId: 819, reportId: 'Q-04' },
    { score: 1, issueId: 896, reportId: 'Q-07' },
    { score: 1, issueId: 914, reportId: 'Q-06' },
    { score: 2, issueId: 938, reportId: 'Q-05' },
    { score: 2, issueId: 984, reportId: 'Q-02' },
    { score: 4, issueId: 1044, reportId: 'Q-03' },
    { score: 5, issueId: 1124, reportId: 'Q-01' }
  ]
```

#### Sample output (distribution to all satisfactory QA)

This is an example where no HMs were found, and the HM pool is distributed among all satisfactory (`grade-a` and `grade-b`) QA reports.

| issueID | reportID | risk | pie               | split | slice               | score | award              |
| ------- | -------- | ---- | ----------------- | ----- | ------------------- | ----- | ------------------ |
| 4       | `Q-08`   | Q    | 6.746955122319307 | 6     | 1.824417009602195   | 2     | 2478.7214802565936 |
| 28      | `Q-16`   | Q    | 6.746955122319307 | 10    | 0.17253811271711028 | 1     | 140.65005661663508 |
| 113     | `Q-19`   | Q    | 6.746955122319307 | 10    | 0.17253811271711028 | 1     | 140.65005661663508 |
| 135     | `Q-18`   | Q    | 6.746955122319307 | 10    | 0.17253811271711028 | 1     | 140.65005661663508 |
| 144     | `Q-15`   | Q    | 6.746955122319307 | 10    | 0.17253811271711028 | 1     | 140.65005661663508 |
| 314     | `Q-17`   | Q    | 6.746955122319307 | 10    | 0.17253811271711028 | 1     | 140.65005661663508 |
| 337     | `Q-14`   | Q    | 6.746955122319307 | 6     | 1.824417009602195   | 2     | 2478.7214802565936 |
| 471     | `Q-13`   | Q    | 6.746955122319307 | 10    | 0.17253811271711028 | 1     | 140.65005661663508 |
| 534     | `Q-12`   | Q    | 6.746955122319307 | 6     | 1.824417009602195   | 2     | 2478.7214802565936 |
| 544     | `Q-10`   | Q    | 6.746955122319307 | 6     | 1.824417009602195   | 2     | 2478.7214802565936 |
| 548     | `Q-11`   | Q    | 6.746955122319307 | 1     | 1                   | 3     | 8151.825379430331  |
| 664     | `Q-09`   | Q    | 6.746955122319307 | 10    | 0.17253811271711028 | 1     | 140.65005661663508 |
| 819     | `Q-04`   | Q    | 6.746955122319307 | 10    | 0.17253811271711028 | 1     | 140.65005661663508 |
| 896     | `Q-07`   | Q    | 6.746955122319307 | 10    | 0.17253811271711028 | 1     | 140.65005661663508 |
| 914     | `Q-06`   | Q    | 6.746955122319307 | 10    | 0.17253811271711028 | 1     | 140.65005661663508 |
| 984     | `Q-02`   | Q    | 6.746955122319307 | 6     | 1.824417009602195   | 2     | 2478.7214802565936 |
| 1044    | `Q-03`   | Q    | 6.746955122319307 | 1     | 1.5                 | 4     | 12227.738069145495 |
| 1124    | `Q-01`   | Q    | 6.746955122319307 | 1     | 2.25                | 5     | 18341.60710371824  |
