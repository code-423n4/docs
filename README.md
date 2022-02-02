---
description: Community-driven contests for smart contract audits
---

# Code4rena

The players in the arena:

* [**Wardens**](roles/wardens/) protect the DeFi ecosystem from threats by auditing code.
* [**Sponsors**](roles/sponsors/) create prize pools to attract wardens to audit their project.
* [**Judges**](roles/judges/) allocate awards to wardens based on performance.

C4 audit contests are different from both bug bounties and traditional audits.

### Bug bounties vs C4 audit contests

| Bug bounties                                                                                            | Audit contests                                                                                                         |
| ------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| **Spec work.** No way to have confidence that the time invested will produce a payout.                  | **Guaranteed payouts.** Auditors know it’s highly likely they can find a bug that will make it worth their time.       |
| **Dark forest.** Who knows how much competition there is right now? Or how mature the codebase is?      | **Low-hanging fruit.** If a project is seeking an audit, it’s likely fresh code with clear opportunities to dig in.    |
| **Grow on your own.** Researchers have to proactively look for ways to learn and level up their skills. | **Learning community.** Open contests let auditors compare everyone’s findings and learn new things every single week. |
| **Paradox of choice.** So many projects have bounties. How does an auditor choose which to focus on?    | **No FOMO.** C4 runs a handful of active contests at a time—often just one or two, tops.                               |

### Traditional audits vs C4 audit contests

| Traditional audits                                                                                                     | C4 audit contests                                                                                                         |
| ---------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| **Constrained time.** If you want a quality audit from a top firm, you’re going to have to wait.                       | **Time flexible.** Code contests can be put together quickly for teams eager to go to market.                             |
| **Constrained cost.** Audit firms must recruit and retain talent, and defensively maintain their brand.                | **Flexible cost.** C4 scales to meet demand. Sponsors can increase pot size to attract more attention.                    |
| **Constrained diversity.** Audit firm staff have to work to stay ahead of DeFi's complex and expanding attack surface. | **Diverse capability.** C4 contests allow specialized security researchers to demonstrate their skill and creativity.     |
| **Systematic.** Firms use set processes for evaluating code, which differs from the way attackers approach things.     | **Rigorous.** C4 wardens are incentivized to work creatively to find as many rare, high risk vulnerabilities as possible. |

## Incentive model and awards

To incentivize **wardens**, C4 uses a unique scoring system with two primary goals: reward contestants for finding unique bugs and also to make the contest resistant to Sybil attack. A secondary goal of the scoring system is to encourage contestants to form teams and collaborate.

Contestants are given shares for bugs discovered based on severity, and those shares give the owner a pro rata piece of the pot:

`Low Risk Shares:   1 * (0.9 ^ (findingCount - 1)) / findingCount`\
`Med Risk Shares:   3 * (0.9 ^ (findingCount - 1)) / findingCount`\
`High Risk Shares: 10 * (0.9 ^ (findingCount - 1)) / findingCount`

Each share is redeemable for: `pot / number of shares`

**Important mechanism update:** For contests starting on or after February 3, 2022, low and non-critical findings should be submitted as a SINGLE QA report; contests will allocate a fixed 10% of prize pools toward QA reports. (Similarly, gas findings should be submitted as a single gas report.) For more on QA and gas reports, see [Judging criteria](roles/wardens/judging-criteria).

**Judges** are incentivized to review findings and determine allocation of the prize pool by receiving a share of the prize pool themselves.
