# Validator role

> Validators decentralize triage by reviewing submissions from wardens with accuracy rates below the qualifying threshold (eg 50%).
> 

All open competitive audits at Code4rena that begin on or after April 30, 2024 will include Validators.

## Validator tl;dr

- Each competition has a **qualifying threshold** that allows wardens to bypass validators. This threshold is based on your submission accuracy rate, as well as being established as a quality contributor and as non-sybil. (For those familiar with ‘backstage warden’ criteria, it is essentially that plus an acceptable accuracy rate.)
- Qualified wardens’ submissions go directly to the usual findings repo.
- All other wardens’ submissions are routed to a Validation repo.
- 3-5 **Validators** review submissions in the Validation repo immediately after the audit closes
    - Satisfactory submissions are forwarded to the findings repo
    - Unsatisfactory submissions are closed
    - Validators may also enhance submissions (add PoC, increase quality of report, etc.) in exchange for a percentage of the finding’s payout. (See “Awarding” section below.)
- The judge reviews all submissions in the findings repo.

The new **Validator** role replaces the Lookout role, so the Lookout pool will be distributed to Validators instead; Validators can earn additional awards by enhancing submissions they review. More details on compensation follow below. 

## Whose submissions require Validator review?

- At launch, the criteria are simple:
    - Submissions from wardens who meet the qualifying threshold go directly to the usual findings repo.
    - All other wardens’ submissions are routed to a Validation repo.
- How to qualify:
    - Improve your accuracy rate (ratio of submissions judged to be satisfactory). Over time, C4’s accuracy metrics will be weighted towards recent audits.

## Validation Round (for RSVP’d Validators) — first 48 hours

- 3-5 Validators are selected for each audit, via RSVP in #rsvp-judging
- Validators who participate in the audit will be automatically assigned a first batch of 5 issues
- Each Validator can label an issue as `sufficient quality`, `insufficient quality` , `unknown`, or `improved`
    - `sufficient quality` - issue is valid; forwards submission to the findings repo
    - `insufficient quality` - closes issue and does not forward
    - `unknown` - returns issue to the Validator pool
    - `improved` - Validator enhanced issue; forwards submission to the findings repo
- Validator can edit (improve) an issue and submit it (see below for more detail)
- After completing 5 issues, another set of 5 will be assigned to you.
- Reviewing 1 submission (adding any label other than `unknown`) from within the `unknown` queue will assign you another 5 issues. This incentivizes picking up issues that other validators passed on in order to capture more of the pool since you can only have a limited number of issues assigned to you at a given time.
- In addition to the initial set of 5 HM issues, each Validator is assigned a share of QA and Gas reports to review: `total_reports / total_validators`
    - Each validator should forward all satisfactory QA/Gas reports to the findings repo for judging.
- ⏰ **Timeline:** goal is for Validators to complete work within 48h after the audit closes.

## Limbo Round (for any Judges/Validators) — after 48 hours

After 48 hours, any issues in the validation repo that have not yet been reviewed are in “Limbo” and available for ***any* judge or lookout(`*`)** to review. 

Once the audit is finalized: 

- Validators are awarded for each validation.
- Validators’ awards are reduced for:
    - incorrect validations
    - “passing” on assigned submissions (labeling as `unknown`)

Each round's validations have different values.

(`*`) Note: After April 30, 2024, the Lookout role will be retired in favour of the new Validator role. All current judges and lookouts will be granted the Validator role by default. Going forward, the Validator role will be granted to community members who meet the eligibility criteria. 

---

## De-duping

- Submissions in the validator repo will have C4’s AI deduper run on them
    - Each dupe set is assigned to a single Validator
    - Within each dupe set, the Validator chooses from the following paths:
        1. If high quality, valid submissions are present that do not need editing → forward *these submissions only* to the findings repo; all other dupes are discarded. 
        2. If condition (1) is not met, Validator selects 1-3 best submissions within the dupe set. Any edits/enhancements are applied to the entire set. 
            
            N.B. In such cases, the judge should review edit history to confirm whether all were of the same quality to start with.
            
- The findings repo (for high-performing wardens’ submissions + Validated submissions) will also have duplicate submissions.
    - The Judge is responsible for reviewing and finalizing dupe sets, and assessing quality.

## Validators can improve HM submissions

Validators may improve High and Medium-risk submissions (HMs); they may not improve QA or Gas reports.

If a validator chooses to improve a submission:

- The original submission is preserved for the judge to see
- The judge evaluates validators’ enhancements and whether they validated, proved, or enhanced them. (See “Awarding” section below.)
- Improved submissions must share the same root cause as the original submission.

*N.B. If the finding is already present in the findings repo, then improved submissions will be judged in their original versions, and Validator improvements will be disregarded.* Validators should check the findings repo for duplicates prior to improving a submission.

## Awarding

- The Validator pool takes the place of the Lookout pool
- Validators earn their share of the Validator pool based on:
    - Number of issues triaged,
    - The phase during which the issues were triaged, and
    - Final accuracy.
- For Validator-improved submissions:  if the judge believes the validator added a measurable enhancement, they get a split of the value of the issue:
    - 25% cut → small enhancement
    - 50% cut → med enhancement
    - 75% cut → large enhancement
- Phases and points:
    - **Round 1** validations are worth 1 point each
    - **Round 2 (”limbo”)** validations are assigned a value on a curve based on the order of the submission (the "nonce") such that the later the submission is validated the more it is worth. The function for this is `steepness ^ (totalNonces - nonceOrder)` where steepness is set to `1.015`
    - Passing costs `0.5` (ie passing twice neutralizes the value of 1 successful validation)
    - The validator's accuracy in this competition has an impact on their overall point total. `points = ((roundOneTotal + limboTotal - (pass*y)) * (accuracy ^x)` where `y` is the `pass cost` (`0.5` by default) and `x` is the accuracy decrementer (`3` by default).
        - For Round 2 (”limbo”) submissions, the value of the accuracy decrementer is 50% of the nonce value.
    - Then the payout is just like shares of other award pools: `validatorPayout = (thisValidatorPoints / allValidatorPoints) * validatorPool`

## Miscellaneous

- Judges can play the Judge and Validator role on the same audit, but are not eligible for any HM pool payouts on audits they judge — even if they enhance an issue.
- If a Warden plays the Validator role on an audit in which they competed as a Warden, they must forgo any Warden awards they would have received for their findings in said audit.
- Both the Validation repo and the Findings repo will be open to wardens with the SR role, for the purposes of post-judging QA.
    - All PJQA requests must be posted in the Github Discussion in the findings repo.
    - QA and Gas reports closed by Validators (i.e. *not* added to the findings repo) are NOT eligible 
- Both repos will be made public when the audit report is published.
- Validators’ accuracy score as a warden is impacted by their accuracy as Validators:
    - 50% of Validators’ *round 1* validator accuracy is applied to their personal accuracy score.
    - Limbo phase accuracy only has a 25% impact on their accuracy.
    - All report types (High, Medium, QA, and Gas) are counted towards accuracy scores.
    - False positives count 50% toward Validators' submission accuracy
    - False negatives count 100% toward Validators' submission accuracy
    - In other words, each false negative is double the negative value of false positives in the ‘incorrect’ count.
- [Certified Security Researchers](../certified-contributors/sr-backstage-wardens.md) may appeal improvements made by Validators, and request that the judge review their original submission during post-judging QA.

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

Complete [this application form](https://code4rena.com/lookout-application/) and share:

- Short bio/intro and summary of relevant experience
- Links that help demonstrate your expertise
- 3 example submissions to Code4rena audits that you’re especially proud of
- Description of how each submission demonstrates your depth of knowledge

**Note:** Validator applications are reviewed during a one-week period each month. Notices of application and review windows will be posted in the C4 Discord server.

**Validator selection process**

Being a Validator is a critical role and we only have so many spots.

Validator applications are reviewed monthly by a group of C4 judges and Validators. The group will review your application and give you a "yes" or "not yet".