---
description: How competitive audits work at Code4rena
icon: trophy
---

# Competitions

Code4rena invented the competitive audit to provide thorough security reviews for Web3 projects, fast. With a community of over 10,000 auditors and an average of 100+ security researchers participating in each audit, C4's competitive audits provide an unparalleled level of trust, depth, and breadth.

## Who can participate?

The Code4rena community includes both seasoned professionals and emerging researchers, with diverse backgrounds and specializations. Anyone can [register as a Warden](../getting-started/), and [join a competition](../getting-started/how-to-participate.md).

As Wardens build experience on Code4rena's platform, they can advance up the leaderboard and earn credibility through different [roles](../roles/), which unlock a variety of privileges.

## How competitive audits work

C4's competitive audits are designed to uncover bugs that may be overlooked in traditional audits, resulting in more robust security outcomes. Our public competitions follow a process honed by running hundreds of audits:

* [**Sponsors**](../sponsors.md) establish prize pools to attract wardens to audit their project.
* During the **Submission phase,** the project code is opened to the community, and Wardens compete to identify vulnerabilities in the project's codebase.
  * Submissions must be entered before the deadline.
  * This phase typically lasts 1-3 weeks.
* **Triage, review, and judging:** Once the submission deadline passes, all submissions to the audit are quickly triaged and deduped, then judged. The judge determines the severity, validity, and quality of findings.
  * The sponsor team has access to all submissions immediately after submissions close, unless otherwise stated in the audit repo.
  * Wardens usually have access to all submissions during this phase as well, unless the audit's scope includes live/deployed contracts, or the sponsor requests stricter privacy.
  * Wardens may not comment during these stages.
* **Post-judging QA:** Once preliminary judging decisions are reached, there is a 48-hour QA period when the sponsor team and [SR wardens](../roles/sr-wardens.md) may add comments for the judge, to ensure fair and rigorous judging.
  * After the QA period ends, the judge finalizes their decisions.
* **Awards** are calculated and distributed using C4's [awarding algorithm](../awarding/).
  * Awards are distributed in [two batches](../awarding/awarding-process.md), to allow the winners sufficient time to satisfy payout requirements.
* The **Audit report** compiles valid findings from the competition and is typically [published on the Code4rena website](https://code4rena.com/reports) for the benefit of both the project's users and the broader Web3 security community.
  * Audit submissions are usually made public when the report is published.
* **Viewing audit results:** Once an audit's results have been finalized, they’ll be shared in our #c4-updates channel in Discord. The audit's page in the [Audits](https://code4rena.com/audits) section on our website will also be updated to show results.

When sponsors have stricter privacy requirements, they may opt to keep their code and/or findings private; if this is the case, it will be noted in the audit documentation and/or announced in the C4 Discord.
