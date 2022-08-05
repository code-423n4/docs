# Incentive model and awards

To incentivize **wardens**, C4 uses a unique scoring system with two primary goals: reward contestants for finding unique bugs and also to make the contest resistant to Sybil attack. A secondary goal of the scoring system is to encourage contestants to form teams and collaborate.

**Judges** are incentivized to review findings and determine allocation of the prize pool by receiving a share of the prize pool themselves.

### High and Medium Risk bugs

Contestants are given shares for bugs discovered based on severity, and those shares give the owner a pro rata piece of the pot:

`Med Risk Shares: 3 * (0.9 ^ (findingCount - 1)) / findingCount`\
`High Risk Shares: 10 * (0.9 ^ (findingCount - 1)) / findingCount`

During awarding, each share is redeemed for: `pot / number of shares`. 

### QA and Gas Optimization Reports

In order to incentivize wardens to focus efforts on high and medium severity findings while also ensuring quality coverage, the pool’s allocation is capped for low severity, non-critical, and gas optimization findings.

Low and non-critical findings are submitted as a **single** QA report. Similarly, gas optimizations are submitted as a single gas report. For more on reports, see [Judging criteria](/awarding/judging-criteria/README.md).

QA and gas optimization reports are awarded on a curve based on the judge’s score.

- QA reports compete for a share of 10% of the prize pool (e.g. $5,000 for a $50,000 contest);
- The gas optimization pool varies from contest to contest, but is typically 5% of the total prize pool (e.g. $2,500 for a $50,000 contest);
- QA and Gas optimization reports are scored by judges on a 100 point scale and awarded on a curve.

**Note:** Contests pre-dating February 3, 2022 awarded low risk and gas optimization shares as: `Low Risk Shares: 1 * (0.9 ^ (findingCount - 1)) / findingCount`
