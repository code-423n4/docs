---
description: Signal is Code4rena's accuracy metric for wardens and teams.
---

# Signal metrics

The `signal` metric is a means of identifying wardens and teams who have consistently submitted valid findings. For a warden or team, it is the ratio between the number of valid high or medium findings versus all of the high and mediums they've submitted.

`signal = findings / submissions`

A signal of 1 means that the warden has consistently submitted valid H and M whereas a signal of 0 means the warden has either submitted only invalid findings or has submitted none.

## Validator process

signal is used in the validation process to decide how your submissions are routed.

We use the following threshold:

- signal >= 0.68
- participated in at least 3 audits
- submitted at least 5 findings

If your submissions meet this threshold, then they will be submitted directly to the sponsor team. Otherwise, they will be held for validation.

## High/Medium submissions downgraded to QA

Currently, all High- and Medium-risk submissions that are downgraded to Low-risk (QA) are excluded from `signal` calculations. 

We expect this to change in future, and will update this documentation as the formula evolves.

## FAQ

**Q. How can I view my signal?** 
A. You can view your `signal` score on [your account settings screen](https://code4rena.com/account).

**Q. How can I view my team's signal?**
A. You can view the score on the [teams page](https://code4rena.com/account/teams) in your account settings

**Q. Who else can see my signal?** 
A. [Judges](https://docs.code4rena.com/roles/judges) and [sponsors](https://docs.code4rena.com/roles/sponsors) can see the `signal` score of wardens and teams alongside their submissions. Your `signal` score is not visible to other wardens.

**Q. How often is the signal updated?** 
A. It is updated daily. 

**Q. What happens if my signal changes — and crosses the threshold — during an audit?** 
A. Submissions are flagged for [validation](https://docs.code4rena.com/roles/certified-contributors/validators) at the time they’re submitted. Therefore: 

- if a warden’s signal increases to 0.68 or higher during an audit, submissions that they make beyond that point would be shown to the sponsor team immediately after the submission deadline;
- conversely, if their signal decreases to < 0.68 during an audit, submissions that they make beyond that point would be held for validation.

**Q. How much historical data does the `signal` calculation use?**
A. The score is calculated with data from March 2023 to present.