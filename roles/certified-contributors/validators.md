# Validator role

> Validators triage submissions from wardens with accuracy rates below the qualifying threshold; they also de-dupe all submissions.
> 

All open competitive audits at Code4rena that begin on or after April 30, 2024 will include Validators.

## Validator tl;dr

- Each competition has a **qualifying threshold** that allows wardens to bypass validators. This threshold is based on your submission accuracy rate, as well as being established as a quality contributor and as non-sybil. (For those familiar with ‘backstage warden’ criteria, it is essentially that plus an acceptable accuracy rate.)
- Qualified wardens’ submissions go directly to the usual findings repo.
- Any assigned Pro League wardens' submissions go directly to the findings repo.
- All other wardens’ submissions are routed to a Validation repo.
- **Validators** review submissions in the Validation repo immediately after the audit closes
    - Satisfactory submissions are forwarded to the findings repo
    - Unsatisfactory submissions are closed
    - ~~Validators may also enhance submissions (add PoC, increase quality of report, etc.) in exchange for a percentage of the finding’s payout. (See “Awarding” section below.)~~ (Validator enhancements are paused until further notice.)
- The judge reviews all submissions in the findings repo.

The **Validator** role replaces the Lookout role.

## Whose submissions require Validator review?

- At launch, the criteria are simple:
    - Submissions from wardens who meet the qualifying threshold go directly to the usual findings repo.
    - All other wardens’ submissions are routed to a Validation repo.
- How to qualify:
    - Improve your accuracy rate (ratio of submissions judged to be satisfactory). Over time, C4’s accuracy metrics will be weighted towards recent audits.

## Validation Round (for RSVP’d Validators) — first 48 hours

- A Validator is selected for each audit, via RSVP in #rsvp-judging
- The Validator can label an issue as `sufficient quality` or `insufficient quality` 
    - `sufficient quality` - issue is valid; forwards submission to the findings repo
    - `insufficient quality` - closes issue and does not forward
- The Validator de-dupes all `sufficient quality` High- and Medium-risk submissions by selecting a `primary` and grouping duplicates with that primary finding. 
    - The Judge is responsible for reviewing and finalizing dupe sets, and assessing quality.
- All satisfactory submissions are forwarded to the findings repo for judging.
    - Validators' decisions are batch-processed via .csv file upload in the validation repo
    - The .csv processing tool is called `howlbot`
- ⏰ **Timeline:** goal is for Validators to complete work within 48h after the audit closes.

---

## Miscellaneous

- Judges can play the Judge and Validator role on the same audit.
- If a Warden plays the Validator role on an audit in which they competed as a Warden, they must forgo any Warden awards they would have received for their findings in said audit.
- Both the Validation repo and the Findings repo will be open to wardens with the SR role, for the purposes of post-judging QA.
    - All PJQA requests must be posted in the Github Discussion in the findings repo.
    - QA and Gas reports closed by Validators (i.e. *not* added to the findings repo) are NOT eligible 
- Both repos will be made public when the audit report is published.
- Validators’ accuracy score is tracked by C4 as a separate metric from their warden accuracy score. 

# Becoming a Validator

To become a Validator, you may be nominated by a Judge or Validator in good standing, or nominate yourself.

## Minimum criteria

The minimum criteria to become a Validator are as follows: 

1. Compete in at least 3 Code4rena audits;
2. Be a [Certified C4 contributor](https://docs.code4rena.com/roles/certified-contributors) in good standing; and
3. Find at least 1 high severity finding OR 3 medium severity findings OR score A on at least 3 QA or Gas reports

## Non-technical criteria

- **Sense of fairness**—i.e. evidence suggests you don't show favoritism, but instead aim for a fair competition where quality is rewarded.
- **Clear written communication**—your English does not need to be perfect, but you should be able to engage in technical discussions with judges and sponsors via written English.

## How to apply

Complete [this application form](https://code4rena.com/validator-application) and share:

- Short bio/intro and summary of relevant experience
- Links that help demonstrate your expertise
- 3 example submissions to Code4rena audits that you’re especially proud of
- Description of how each submission demonstrates your depth of knowledge

**Note:** Validator applications are reviewed during a one-week period each month. Notices of application and review windows will be posted in the C4 Discord server.

## Validator selection process

Being a Validator is a critical role and we only have so many spots.

Validator applications are reviewed monthly by a group of C4 judges and Validators. The group will review your application and give you a "yes" or "not yet".
