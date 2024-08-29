# Ranked curve model

Code4rena's ranked curve is used to calculate rank-based award distributions, including: 
- [QA reports](https://docs.code4rena.com/awarding/incentive-model-and-awards#ranks-for-qa-and-gas-reports)
- [Gas reports](https://docs.code4rena.com/awarding/incentive-model-and-awards#ranks-for-qa-and-gas-reports)
- [Dark Horse bonuses](🔴TODO: add link here)

## If there are tied ranks

If two or more wardens (or teams) have tied ranks, they split the _total_ awards for the ranks they would otherwise occupy — i.e. if two wardens tie for 2nd place, they split the total awards for 2nd and 3rd place. Or if three wardens tie for 3rd, they split the total awards for 3rd place.

## QA and Gas reports: ranked curve awarding

QA and Gas reports are [ranked and graded as described here](https://docs.code4rena.com/awarding/incentive-model-and-awards#ranks-for-qa-and-gas-reports): 
- 1st place (score: 5)
- 2nd place (score: 4)
- 3rd place (score: 3)
- `grade-a` and `grade-b` (score: 0, except in rare cases -- see below)
- `grade-c` (score: 0)

In most cases, only 1st, 2nd, and 3rd place reports are eligible for awards. See "If there are no valid HM findings" below for an exception.

- Reports (referred to as `findings` in the code) are sorted in descending order based on their scores. Findings without a score are treated as having a score of 0.
- For each report, a point value is calculated using the formula `qaAndGasConstant^(2 - idx)`, where `qaAndGasConstant` is defined in the `qaAndGasRanking` code (see example below), and  `idx` is the index of the report in the sorted array. This means the highest-scored report gets the highest point value, decreasing exponentially for subsequent reports.
- **Pie** - The total value of the pie is the sum of all point values.
- **Mapping score to points** - unique score is mapped to an array of point values associated with findings that have that score.
- **Slice for each score** - sum the points for each score to determine the slice size for each score.
- **Split** - number of reports sharing the same score

```js
sortedFindings = [{id: 1, score: 5}, {id: 2, score: 4}, {id: 3, score: 3}];
points = [4, 2, 1];  // 2^(2-0), 2^(2-1), 2^(2-2)
pie = 4 + 2 + 1 = 7;

scorePointMap = { 5: [4], 4: [2], 3: [1] };

slices = [
  { id: 1, score: 5, pie: 7, split: 1, slice: 4 },
  { id: 2, score: 4, pie: 7, split: 1, slice: 2 },
  { id: 3, score: 3, pie: 7, split: 1, slice: 1 }
];
```

### Code example
```javascript
  function qaAndGasRanking (constant = 1.5, awardSatisfactory = true) {
      const sorted = findings.sort((a, b) => {
          return b.score - a.score;
      });

      const points = sorted.map((_, idx) => Math.pow(constant, 2 - idx));
      const pie = points.reduce((a, p) => a+p, 0);

      const scorePointMap = sorted.reduce((a, c, idx) => {
          const score = c.score;
          if (!a[score]) {
              a[score] = [];
          }

          a[score].push(points[idx]);
          return a;
      }, {})

      const scoreSliceMap = {};
      for (const [score, points] of Object.entries(scorePointMap)) {
          scoreSliceMap[score] = points.reduce((a, c) => a+c, 0)
      }

      return sorted.map((s) => {
          return {
              ...s,
              pie,
              split: scorePointMap[s.score].length,
              slice: scoreSliceMap[s.score],
          }
      })
  }
```
### Sample output

| issueID | reportID | risk | score | award | 
| ------- | -------- | ---- | ----- | ----- |
| 13 | `Q-01` | Q | "1st place" | 3552.6315789473683 |
| 207 | `Q-02` | Q | "2nd place" | 2368.4210526315787 |
| 42 | `Q-03` | Q | "3rd place" | 1578.9473684210525 |


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

| issueID | reportID | risk | pie | split | slice | score | award | 
| ------- | -------- | ---- | --- | ----- | ----- | ----- | ----- |
|  4 | `Q-08 ` | Q | 4.75 | 1 | 1 | 3 | 1578.9473684210525 |
| 28 | `Q-16 ` | Q | 4.75 | 2 | 3.75 | 5 | 2960.5263157894738 |
| 113 | `Q-19 ` | Q | 4.75 | 2 | 3.75 | 5 | 2960.5263157894738 |

### If there are no valid HM findings

In the unlikely event that zero high- or medium-risk vulnerabilities are found, all satisfactory reports without a 1st/2nd/3rd place rank will be assigned a `score` according to grade -- `grade-a` receives a score of `2`, and `grade-b` receives a score of `1` -- and the HM award pool is divided among all satisfactory QA reports based on the QA report curve, *unless otherwise stated in the audit repo.* 

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

| issueID | reportID | risk | pie | split | slice | score | award | 
| ------- | -------- | ---- | --- | ----- | ----- | ----- | ----- |
| 4 | `Q-08` | Q | 6.746955122319307 | 6 | 1.824417009602195 | 2 | 2478.7214802565936 |
| 28 | `Q-16` | Q | 6.746955122319307 | 10 | 0.17253811271711028 | 1 | 140.65005661663508 |
| 113 | `Q-19` | Q | 6.746955122319307 | 10 | 0.17253811271711028 | 1 | 140.65005661663508 |
| 135 | `Q-18` | Q | 6.746955122319307 | 10 | 0.17253811271711028 | 1 | 140.65005661663508 |
| 144 | `Q-15` | Q | 6.746955122319307 | 10 | 0.17253811271711028 | 1 | 140.65005661663508 |
| 314 | `Q-17` | Q | 6.746955122319307 | 10 | 0.17253811271711028 | 1 | 140.65005661663508 |
| 337 | `Q-14` | Q | 6.746955122319307 | 6 | 1.824417009602195 | 2 | 2478.7214802565936 |
| 471 | `Q-13` | Q | 6.746955122319307 | 10 | 0.17253811271711028 | 1 | 140.65005661663508 |
| 534 | `Q-12` | Q | 6.746955122319307 | 6 | 1.824417009602195 | 2 | 2478.7214802565936 |
| 544 | `Q-10` | Q | 6.746955122319307 | 6 | 1.824417009602195 | 2 | 2478.7214802565936 |
| 548 | `Q-11` | Q | 6.746955122319307 | 1 | 1 | 3 | 8151.825379430331 |
| 664 | `Q-09` | Q | 6.746955122319307 | 10 | 0.17253811271711028 | 1 | 140.65005661663508 |
| 819 | `Q-04` | Q | 6.746955122319307 | 10 | 0.17253811271711028 | 1 | 140.65005661663508 |
| 896 | `Q-07` | Q | 6.746955122319307 | 10 | 0.17253811271711028 | 1 | 140.65005661663508 |
| 914 | `Q-06` | Q | 6.746955122319307 | 10 | 0.17253811271711028 | 1 | 140.65005661663508 |
| 984 | `Q-02` | Q | 6.746955122319307 | 6 | 1.824417009602195 | 2 | 2478.7214802565936 |
| 1044 | `Q-03` | Q | 6.746955122319307 | 1 | 1.5 | 4 | 12227.738069145495 |
| 1124 | `Q-01` | Q | 6.746955122319307 | 1 | 2.25 | 5 | 18341.60710371824 |

## Dark Horse bonuses: ranked curve awarding

Dark Horse bonuses are calculated using the same ranked curve as QA and Gas reports -- except that in lieu of assigning points for each rank (1, 2, 3), the number of ranks is flexible. Shares are calculated using a decrementer of 0.2 (starting with a decrementer of 0.5). 

### If there are only 2 Dark Horse winners

Awards are split 60/40 (rounded from the 62.5%/37.5% that would result from a strict application of the ranked curve).

### Sample output with 3 Dark Horse winners

Using a Dark Horse bonus pool of $10,000:

| warden rank | decrementer | shares      | award     | 
| ----------- | ----------- | ----------- | --------- | 
| 1           | 0.5         | 100         | $4,980.08 |
| 2           | 0.4	        | 60	        | $2,988.05 |
| 3           | 0.32	      | 40.8        | $2,031.87 |

### Sample output with 5 Dark Horse winners

Using a Dark Horse bonus pool of $10,000:

| warden rank | decrementer | shares      | award     | 
| ----------- | ----------- | ----------- | --------- | 
| 1           | 0.5         | 100         | $3,917.06 |
| 2           | 0.4	        | 60	        | $2,350.23 |
| 3           | 0.32	      | 40.8        | $1,598.16 |
| 4           | 0.256	      | 30.3552     | $1,189.03 |
| 5           | 0.2048      |	24.13845504 |   $945.52 |