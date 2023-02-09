## Estimating Risk

Where **assets** refer to funds, NFTs, data, authorization, and any information intended to be private or confidential:

* **QA (Quality Assurance)** Includes both **Non-critical** (code style, clarity, syntax, versioning, off-chain monitoring (events, etc) and **Low risk** (e.g. assets are not at risk: state handling, function incorrect as to spec, issues with comments). Excludes Gas optimizations, which are submitted and judged separately.
* **2 — Med:** Assets not at direct risk, but the function of the protocol or its availability could be impacted, or leak value with a hypothetical attack path with stated assumptions, but external requirements.
* **3 — High:** Assets can be stolen/lost/compromised directly (or indirectly if there is a valid attack path that does not have hand-wavy hypotheticals).

## Severity Standardization Process

Judges and the C4 community collaborate in open discussions of severity standards, which has created an evolving meta that's unique to C4 and enables both the organizations being audited and the auditors themselves to be part of a platform that is self-reflective and is constantly iterating on its processes for their collective benefit.

The rules above act as a starting point, and these open discussions act as a growing set of case law examples. You can view the open forum where these discussions are held [here](https://github.com/code-423n4/org/issues?q=is%3Aissue+is%3Aopen+label%3Arules).
