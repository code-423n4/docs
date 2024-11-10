# Criteria for C4 bug bounty findings

Any registered warden can submit bugs to Code4rena bug bounties. 

- Only Critical and High risk issues are acceptable
- Coded runnable PoCs are required

## High likelihood

A finding with high likelihood is defined as a vulnerability purely exploitable by code without social engineering or privileged access, where 
1. the attacker has control over creating the requisite circumstances; *and* 
2. requisite circumstances not under control of the attacker can be reasonably expected to occur and can be predicted or anticipated by the attacker using publicly available information. 

Exploit complexity, sophistication, and expertise are not considered factors in determining likelihood.

## Critical severity
A **Critical severity finding** is a high impact issue which has a high likelihood of being exploited, where the impact could result in:
- Manipulation of governance voting result deviating from voted outcome and resulting in a direct change from intended effect of original results
- Direct theft of any user funds, whether at-rest or in-motion, other than unclaimed yield
- Direct theft of any user NFTs, whether at-rest or in-motion, other than unclaimed royalties
- Permanent freezing of funds
- Permanent freezing of NFTs
- Unauthorized minting of NFTs
- Predictable or manipulable RNG that results in abuse of the principal or NFT
- Unintended alteration of what the NFT represents (e.g. token URI, payload, artistic content)
- Protocol insolvency

## High severity
A **High severity finding** is a high impact issue with any likelihood which results in:
- Theft of unclaimed yield
- Theft of unclaimed royalties
- Permanent freezing of unclaimed yield
- Permanent freezing of unclaimed royalties
- Temporary freezing of funds
- Temporary freezing NFTs

## WontFix
A **WontFix finding** is a high impact issue which has been deemed valid but which the Sponsor chooses not to take action on.

In order to be considered a WontFix Finding, the issue must be assessed as Critical Severity or High Severity.

## Delayed fix
A **Delayed fix finding** is a valid finding which the Sponsor originally categorized as WontFix, but for which a fix was later deployed.

If a warden notes that a fix has been applied to an issue they reported that was judged as WontFix, they may [file a judge appeal](/awarding/judging-criteria/bounty-judging.md#appeals-process-for-bounty-programs) for a deposit of $200 USDC.

If a finding is determined to be WontFix and a judge later determines that the sponsor includes the fix in a later release, the warden will be compensated for the finding as follows:
- **Within 30 days of submission:** 100% of the bug’s full assessed value.
- Within 60 days of submission: 50% of the bug’s full assessed value
- **More than 60 days after submission:** the WontFix Fee multiplied by 2.

## Out of scope
- Impacts requiring attacks that the warden has already exploited themselves, leading to damage
- Impacts caused by attacks requiring access to leaked keys/credentials
- Impacts caused by attacks requiring access to privileged addresses (governance, strategist) except in such cases where the contracts are intended to have no privileged access to functions that make the attack possible
- Impacts relying on attacks involving the depegging of an external stablecoin where the attacker does not directly cause the depegging due to a bug in code
- Mentions of secrets, access tokens, API keys, private keys, etc. in Github will be considered out of scope without proof that they are in-use in production
- Best practice recommendations
- Feature requests
- Impacts on test files and configuration files unless stated otherwise in the bug bounty program
- Smart Contracts/Blockchain DLT
- Incorrect data supplied by third party oracles
- Impacts requiring basic economic and governance attacks (e.g. 51% attack)
- Lack of liquidity impacts
- Impacts from Sybil attacks
- Impacts involving centralization risks
