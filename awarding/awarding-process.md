# Awarding process

At the conclusion of an audit, sponsors review wardens’ findings and express their opinions with regard to severity of issues. Judges evaluate input from both and make the ultimate decision in terms of severity and validity of issues. (See [Judging criteria](/competitions/judging-criteria.md) for more detail.)

In making their determination, judges add labels to Github issues, while the original submission data (including the warden's proposed severity rating) is preserved via a JSON data file. 

The judge's decisions are reviewed by the sponsoring project team and by [certified Security Researchers](/roles/sr-wardens.md) via a 48-hour QA process, to ensure fairness and quality. 

Judging data is used to generate the awards using Code4rena's [award calculation script](/awarding/), which factors in:

- Risk level
- Validity
- Number of duplicates
- Rank (1st, 2nd, 3rd; Satisfactory/Unsatisfactory)
- In some cases, "partial duplicate" status

 It should be possible to reverse engineer awards using a combination of two CSV files:
 
 - [`findings.csv`](https://code4rena.com/community-resources/findings.csv): valid Code4rena findings
 - [`contests.csv`](https://code4rena.com/community-resources/contests.csv): Code4rena audits 

Once awards are determined, we generate a CSV file enumerating funds to be sent. Distribution is then initiated using disperse.app and sent to multisig signers for completion of payment.

## Award distribution requirements and schedule

All participants in Code4rena audits must provide C4 with [tax reporting information](#tax-information-for-code4rena-contributors-wardens-judges-etc) in order to receive payment.

Awards are sent in two batches:
 1. Participants who have already submitted their tax info when awards are announced will receive awards with 1 week of the announcement. 
 2. Once the 30-day window (after the announcement) passes, C4 will review any newly submitted tax info and send the second and final batch of awards within 1 week. *If your tax info is not received within 30 days of the award announcement, you will not be eligible to receive that award.*

From a timing standpoint, it is sufficient to have *submitted* your tax information by the allotted deadline; it does not need to have been reviewed or approved by us by the deadline. However, your submission must be reviewed and approved in order for Code4rena to pay you. 

Registered users can [submit their tax information here](https://code4rena.com/tax-info).

## If you don't see your award in your wallet:

1. Review the award distribution requirements and schedule above.
1. Double-check that your tax information was successfully submitted, by visiting [your C4 account settings page](https://code4rena.com/account), under "Tax information."
1. If awards have been sent, and you don’t see them in your wallet, verify that you have imported the USDC token into your Polygon wallet. (MetaMask instructions [here](https://support.metamask.io/hc/en-us/articles/360015489031-How-to-display-tokens-in-MetaMask).)
1. If you still don’t see the award in your wallet, please [open a help desk ticket](https://code4rena.com/help).

# Tax information for Code4rena contributors (wardens, judges, etc)

Code4rena has tax reporting responsibility as a US entity. As such, we have created a system and process for enabling tax reporting which also ensures confidentiality and privacy.

Wardens and other contributors (e.g. judges, validators, scouts, etc.) who are eligible to receive awards from Code4rena must [complete a questionnaire](/getting-started#tax-reporting-information) to determine what, if any, U.S. reporting or withholding obligations exist.

[Warden teams](/getting-started#registering-a-team) must ensure that all team members have submitted their tax information in order to receive awards. 

Based on our obligations to operate within tax regulation, completing that questionnaire is required by participants in order to receive awards.

Wardens are encouraged to review Code4rena's [Submission Policy](/legal/submission-policy.md), particularly the "Representations and Warranties" section.

# Tax and legal questions

> *Note: Do your own research; this is not legal or tax advice. You should consult a professional in your area.*

We are occasionally asked how wardens should declare Code4rena earnings for tax (or other financial/legal) purposes. You must assess and determine your own best course of action.

Legal entity details for invoices, which can be sent to admin (at) code4rena [dotcom]:

ZC Security Holdings, LLC  
228 Park Ave S #97576
New York NY USA
