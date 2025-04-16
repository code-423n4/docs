---
icon: filters
---

# Validators

## Validators

Validators triage submissions from wardens with accuracy rates below the qualifying threshold; they also de-dupe all submissions.

* Each competition has a [**qualifying threshold**](signal.md#validation-process) that allows wardens to bypass validators. This threshold is based on your [signal score](signal.md), as well as being established as a quality contributor and as non-sybil.
* Qualified wardens’ submissions are shared with the sponsor team immediately after submissions close.
* All other wardens’ submissions are routed through a Validator.

**Validators** review submissions immediately after submissions close.

* Satisfactory submissions are forwarded to the sponsor
* Unsatisfactory submissions (either `invalid` or `insufficient quality`) are not shown to the sponsor team.

The judge reviews all submissions except those the Validator marked as `spam`. (Note: this includes submissions that the Validator marked as `invalid` and/or `insufficient quality`.)

### Validator evaluations

* The Validator evaluates each submission's **quality** and **validity,** and groups **duplicate submissions** into findings (groups of submissions with shared root cause).
* **This input is advisory and does not constitute a final evaluation;** the Judge reviews and finalizes all Validator evaluations regarding validity, quality, and duplicate sets. Only submissions marked as `spam` (very low quality) are not reviewed by the Judge.
* Quality is evaluated as one of three possible levels:
  * `sufficient quality` - submission meets C4's standards for quality. (For information about quality standards, see the ["Good citizenship"](../competitions/submission-guidelines.md#good-citizenship-is-a-requirement-for-compensation) and ["Burden of proof"](../competitions/submission-guidelines.md#burden-of-proof) section of the [Submission guidelines](../competitions/submission-guidelines.md))
  * `insufficient quality` - submission does not meet C4's standards for quality (but will be reviewed by the judge)
  * `spam` - submission appears to be spam (and will not be reviewed by the sponsor or judge)
* Validity is evaluated as either:
  * `valid`
  * `invalid`, or
  * `out of scope`
* The Validator de-dupes all `sufficient quality` High- and Medium-risk submissions by selecting a `primary` and grouping duplicates with that primary finding.
* ⏰ **Timeline:** The goal is for Validators to complete work within 48h after the audit closes. This timeline varies depending on the volume of submissions.

For more information on the judging criteria used by Validators and Judges, see [Judging criteria](../competitions/judging-criteria.md).

### Miscellaneous

* Judges can play the Judge and Validator role on the same audit.
* If a Warden plays the Validator role on an audit in which they competed as a Warden, they must forgo any Warden awards they would have received for their findings in said audit.
* QA reports marked as low quality by the Validator are NOT eligible for post-judging QA discussions.

## Becoming a Validator

To become a Validator, you may be nominated by a Judge or Validator in good standing, or nominate yourself.

### Minimum criteria

The minimum criteria to become a Validator are as follows:

1. Compete in at least 3 Code4rena audits;
2. Be an [SR warden](sr-wardens.md) in good standing.

### Non-technical criteria

* **Sense of fairness**—i.e. evidence suggests you don't show favoritism, but instead aim for a fair competition where quality is rewarded.
* **Clear written communication**—your English does not need to be perfect, but you should be able to engage in technical discussions with judges and sponsors via written English.

### How to apply

Complete [this application form](https://code4rena.com/validator-application) and share:

* Short bio/intro and summary of relevant experience
* Links that help demonstrate your expertise
* 3 example submissions to Code4rena audits that you’re especially proud of
* Description of how each submission demonstrates your depth of knowledge

**Note:** judge applications are reviewed on an as-needed basis. Notices of application and review windows will be posted in the C4 Discord server.

### Validator selection process

Being a Validator is a critical role and we only have so many spots.

Validator applications are reviewed regularly by senior C4 staff. We will review your application and give you a "yes" or "not yet".
