---
description: Signal is Code4rena's accuracy metric for wardens and teams.
---

# Signal metrics

The `signal` metric is a means of identifying wardens and teams who have consistently submitted valid findings. For a warden or team, it is the ratio between the number of valid High- or Medium-risk findings versus all of the high and mediums they've submitted.

`signal = findings / submissions`

A signal of 1 means that the user has consistently submitted valid H and M, whereas a signal of 0 means the user has either submitted only invalid findings or has not yet met the participation threshold to calculate signal.

Contributors' `signal` will display as `0` (i.e. `null`) until they have:
- participated in at least 3 audits, and
- submitted at least 5 findings

## Validation process

`signal` is used in the validation process to decide how your submissions are routed.

We currently use the following threshold: `signal >= 0.68`

If your submissions meet this threshold, then they will be submitted directly to the sponsor team. Otherwise, they will be held for validation.

## Submission limits based on `signal`

To reduce spam while keeping C4 competitions open to all, `signal` determines the maximum number of submissions wardens/teams can make to each audit.

- The higher your signal , the more submissions you get.
- Low- or no-signal users' submissions are capped, to disincentivize "spray and pray" behavior and encourage newer wardens to focus on their highest-risk, highest-quality findings.
- Earn bonus (or uncapped) submissions by verifying your Github account and submitting your tax information.
- Unrestricted submissions unlock at 0.2 (20%) signal + verified GH/tax info.

These limits are subject to change, based on the volume of low-quality/spam submissions we receive over time.

| User's `signal` | Max # of submissions per audit | Verified Github + submitted tax info | 
| --------------- | ------------------------------ | ------------------------------------ |
| n/a (*)         | 7                              | 10                                   |
| < 0.2           | 7                              | 10                                   |
| 0.2-0.3999      | 25                             | unrestricted                         |
| 0.4+            | unrestricted                   | unrestricted                         |

- If (( signal = `null` (e.g. you are a newly-registered user, or have participated in < 3 audits) OR signal  < 0.2 )) and you have not verified your Github account and submitted tax info, then you will be limited to 7 submissions per audit.
  - If you meet these criteria, and have both:
    - verified Github, and
    - submitted tax info, 
    then you will unlock 3 bonus submissions per audit (i.e. max 10 submissions in total)
- If your `signal` = 0.2-0.3999 and you have not verified your Github account and submitted tax info, then you will be limited to 25 submissions per audit.
    - If you meet these criteria, and have both:
    - verified Github, and
    - submitted tax info, 
    then you will have unrestricted submissions.
- If your `signal`  >/= 0.4, you will have unrestricted submissions (regardless of Github verification or tax info submission status). 

**How do submission limits apply to teams?**
- Warden teams are subject to the same criteria as individual wardens.
- Submission limits apply to both teams and individual wardens.
- To unlock bonus submissions, *all* members of a team must verify their Github account and submit tax info.


## High/Medium submissions downgraded to QA

Currently, all High- and Medium-risk submissions that are downgraded to Low-risk (QA) are excluded from `signal` calculations. 

We expect this to change in future, and will update this documentation as the formula evolves.

## FAQ

**Q. How can I view my signal?** 

A. You can view your `signal` score on [your account settings screen](https://code4rena.com/account).

**Q. How can I view my team's signal?**

A. You can view the score on the [teams page](https://code4rena.com/account/teams) in your account settings

**Q. Who else can see my signal?** 

A. Authenticated users can see the `signal` score of wardens and teams alongside their submissions, while logged in to [Code4rena.com](https://code4rena.com). 

**Q. How often is the signal updated?** 

A. It is updated daily. 

**Q. What happens if my signal changes — and crosses the threshold — during an audit?** 

A. Submissions are flagged for [validation](/roles/validators) at the time they’re submitted. Therefore: 

- if a warden’s signal increases to 0.68 or higher during an audit, submissions that they make beyond that point would be shown to the sponsor team immediately after the submission deadline;
- conversely, if their signal decreases to < 0.68 during an audit, submissions that they make beyond that point would be held for validation.

**Q. How much historical data does the `signal` calculation use?**

A. The score is calculated with data from March 2023 to present.
