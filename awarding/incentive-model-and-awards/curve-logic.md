# Curve Logic for QA and Gas Optimization Reports

QA and Gas reports are [ranked and graded as described here](https://docs.code4rena.com/awarding/incentive-model-and-awards#ranks-for-qa-and-gas-reports): 
- 1st place (score: 5)
- 2nd place (score: 4)
- 3rd place (score: 3)
- `grade-a` and `grade-b` (score: 0, except in rare cases -- see below)
- `grade-c` (score: 0)

In most cases, only 1st, 2nd, and 3rd place reports are eligible for awards. See "If there are no valid HM findings" below for an exception.

- Reports (referred to as `findings` in the code) are sorted in descending order based on their scores. Findings without a score are treated as having a score of 0.
- For each report, a point value is calculated using the formula `qaAndGasConstant^(2 - idx)`, where `idx` is the index of the report in the sorted array. This means the highest-scored report gets the highest point value, decreasing exponentially for subsequent reports.
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

## Curve model

Code example
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

## Sample input

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

## Sample output

This is an example where no HMs were found, and the HM pool is distributed among all satisfactory (`grade-a` and `grade-b`) QA reports. 

| score | issueID | Pie               | Split | Slice               | reportID | award |
| ----- | ------- | ----------------- | ----- | ------------------- | -------- | ----- |
| 5     | 1124    | 6.746955122319307 | 1     | 2.25                | 'Q-01'   |  |
| 4     | 1044    | 6.746955122319307 | 1     | 1.5                 | 'Q-03'   |  |
| 3     | 548     | 6.746955122319307 | 1     | 1                   | 'Q-11'   |  |
| 2     | 4       | 6.746955122319307 | 6     | 1.824417009602195   | 'Q-08'   |  |
| 2     | 337     | 6.746955122319307 | 6     | 1.824417009602195   | 'Q-14'   |  |
| 2     | 534     | 6.746955122319307 | 6     | 1.824417009602195   | 'Q-12'   |  |
| 2     | 544     | 6.746955122319307 | 6     | 1.824417009602195   | 'Q-10'   |  |
| 2     | 938     | 6.746955122319307 | 6     | 1.824417009602195   | 'Q-05'   |  |
| 2     | 984     | 6.746955122319307 | 6     | 1.824417009602195   | 'Q-02'   |  |
| 1     | 28      | 6.746955122319307 | 10    | 0.17253811271711028 | 'Q-16'   |  |
| 1     | 113     | 6.746955122319307 | 10    | 0.17253811271711028 | 'Q-19'   |  |
| 1     | 135     | 6.746955122319307 | 10    | 0.17253811271711028 | 'Q-18'   |  |
| 1     | 144     | 6.746955122319307 | 10    | 0.17253811271711028 | 'Q-15'   |  |
| 1     | 314     | 6.746955122319307 | 10    | 0.17253811271711028 | 'Q-17'   |  |
| 1     | 471     | 6.746955122319307 | 10    | 0.17253811271711028 | 'Q-13'   |  |
| 1     | 664     | 6.746955122319307 | 10    | 0.17253811271711028 | 'Q-09'   |  |
| 1     | 819     | 6.746955122319307 | 10    | 0.17253811271711028 | 'Q-04'   |  |
| 1     | 896     | 6.746955122319307 | 10    | 0.17253811271711028 | 'Q-07'   |  |
| 1     | 914     | 6.746955122319307 | 10    | 0.17253811271711028 | 'Q-06'   |  |

## If there are no valid HM findings

In the unlikely event that zero high- or medium-risk vulnerabilities are found, all satisfactory reports without a 1st/2nd/3rd place rank will be assigned a `score` according to grade -- `grade-a` receives a score of `2`, and `grade-b` receives a score of `1` -- and the HM award pool is divided among all satisfactory QA reports based on the QA report curve, *unless otherwise stated in the audit repo.* 

## If there are tied report scores

If two or more QA (or gas optimization) reports have tied scores, they split the _total_ awards for the slots they would otherwise occupy — i.e. if two wardens tie for 2nd place, they split the total awards for 2nd and 3rd place. Or if three wardens tie for 3rd, they split the total awards for 3rd place.
