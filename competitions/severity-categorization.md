## Estimating Risk

Where **assets** refer to funds, NFTs, data, authorization, and any information intended to be private or confidential:

* **QA (Quality Assurance)** Includes **Low risk** (e.g. assets are not at risk: state handling, function incorrect as to spec, issues with comments) and **Governance/Centralization risk** (including admin privileges). Excludes Gas optimizations, which are submitted and judged separately. Non-critical issues (code style, clarity, syntax, versioning, off-chain monitoring (events, etc) are discouraged.
* **2 — Med:** Assets not at direct risk, but the function of the protocol or its availability could be impacted, or leak value with a hypothetical attack path with stated assumptions, but external requirements.
* **3 — High:** Assets can be stolen/lost/compromised directly (or indirectly if there is a valid attack path that does not have hand-wavy hypotheticals).

## Centralization risks

Submissions describing centralization risks should be submitted as follows:

- Direct misuse of privileges shall be submitted in the QA report.
- Reckless admin mistakes are invalid. Assume calls are previewed.
- Mistakes in code only unblocked through admin mistakes should be submitted within a QA Report.
- Privilege escalation issues are judged by likelihood and impact and their severity is uncapped.

## Conditional on user mistake

Findings that require the user to be careless or enter the wrong information into a contract call are QA or Invalid. 

Non privileged users are expected to preview their transactions to protect against input mistakes. Anyone using modern tooling will have previews built into their toolset.

Phishing attacks, and improper caution on using a protocol fall under this rule.

## Speculation on future code

Any issue that is not exploitable within the scope of the contest is defined as speculating on future code. Any such speculation only has the potential to be valid if the root cause is demonstrated to be in the contest scope. Warden may make an argument on why a future code change that would make the bug manifest is reasonably likely. Based on likelihood considerations, the Judge may assign a severity rating in any way they see fit.

If the exploitability relies on a particular 3rd party integration, the likelihood must factor in a competent integrator who has done due diligence.

## Event-related impacts

A bug whose consequence is faulty emission of event(s) shall be graded in line with its broader-level impact:
- For events which are used for additional on-chain processes such as bridging, inclusion proofs etc., issue will be graded based on impacted functionality.
- Bugs that cause non-compliance with EIPs shall be graded based on EIP ruling guidelines
- Failure to demonstrate the broader level impacts above shall cap the severity to Low. For clarification, bugs leading to readability or accessibility of data, or issues of display in frontends, are capped to Low.

## Protocol does not support CryptoPunks

- QA as Refactoring / Improvement
- Cannot be argued as a vulnerability

## Unsupported fee-on-transfer tokens (and broader ERC20 discussion)

Generally speaking, all non-standard ERC-20 token issues should be included in a dedicated part of the analysis writeup, not submitted as high, medium, or low risk issues. The exception is an actual threat to the functionality of the protocol or funds thereof. Judges should immediately invalidate useless issues in this category.

Regardless of the place of submission, out of scope issues should never be submitted. Doing so  is a waste of everyone’s time.

Rather than treat EIP-20 as an authoritative document, we recognize that the commonly understood definition is the one stated here: https://ethereum.org/en/developers/docs/standards/tokens/erc-20/#body

## Fault in out-of-scope library with impact on an in-scope contract

When an in-scope contract composes/inherits with an OOS contract, and the root cause exists in the OOS contract, the finding is to be treated as OOS. Exceptional scenarios are at the discretion of the judge.

## Loss of fees as Low

Loss of fees should be regarded as an impact similar to any other loss of capital:
- Loss of dust amounts are QA
- Loss of real amounts depends on specific conditions and likelihood considerations.

## Loss of yield as high

Loss of **matured** yield should be regarded as an impact similar to any other loss of capital:
- Loss of dust amounts are QA
- Loss of real amounts depends on specific conditions and likelihood considerations.

Loss of **unmatured** yield or yield in motion shall be capped to medium severity.

## Approve race condition - NC or Invalid
Notes from [the Fall 2023 Supreme Court decisions](https://docs.code4rena.com/awarding/judging-criteria/supreme-court-decisions-fall-2023/): 
- We have long rejected the finding as anything above NC
- OZ has deprecated increaseAllowance and decreaseAllowance
- We officially confirm:
  - Approve and safeApprove front-run is NOT a valid vulnerability
  - Approve and safeApprove are NOT deprecated
  - increaseAllowance and decreaseAllowance ARE deprecated, although usage of those functions
  is not regarded as a bug report.

## Severity Standardization Process

Judges and the C4 community collaborate in open discussions of severity standards via [the Code4rena Discord server](https://discord.gg/code4rena).