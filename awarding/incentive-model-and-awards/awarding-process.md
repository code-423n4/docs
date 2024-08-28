---
description: >-
  This is a high level overview of the C4 awarding process. 
---

# Awarding process

At the conclusion of an audit, sponsors review wardens’ findings and express their opinions with regard to severity of issues. Judges evaluate input from both and make the ultimate decision in terms of severity and validity of issues. (See [How to judge an audit](https://docs.code4rena.com/roles/judges/how-to-judge-a-contest.md) for more detail.)

In making their determination, judges add labels to Github issues, while the original submission data (including the warden's proposed severity rating) is preserved via a JSON data file. 

The judge's decisions are reviewed by the sponsoring project team and by [certified Security Researchers](https://docs.code4rena.com/roles/certified-contributors/sr-backstage-wardens) via a 48-hour QA process, to ensure fairness and quality. 

Judging data is used to generate the awards using Code4rena's award calculation script, which factors in:

- Risk level
- Validity
- Number of duplicates
- Rank (1st, 2nd, 3rd; Satisfactory/Unsatisfactory)
- In some cases, "partial duplicate" status

 It should be possible to reverse engineer awards using a combination of two CSV files:
 
 - [`findings.csv`](https://code4rena.com/community-resources/findings.csv): valid Code4rena findings
 - [`contests.csv`](https://code4rena.com/community-resources/contests.csv): Code4rena audits 

Once awards are determined, we generate a CSV file enumerating funds to be sent. Distribution is then initiated using disperse.app and sent to multisig signers for completion of payment.

## If you don't see your award in your wallet:

For most Code4rena contests, awards are sent on the Polygon network (usually in USDC) within 1-2 weeks of the awards announcement.

If awards have been sent, and you don’t see them in your wallet, please verify that you have imported the USDC token into your Polygon wallet. (MetaMask instructions [here](https://support.metamask.io/hc/en-us/articles/360015489031-How-to-display-tokens-in-MetaMask).)

If you still don’t see the award in your wallet, please [open a help desk ticket](https://code4rena.com/help).

# Tax information for Code4rena contributors (wardens, judges, etc)

Code4rena has tax reporting responsibility as a US entity. As such, we have created a system and process for enabling tax reporting which also ensures confidentiality and privacy.

Wardens and other contributors (e.g. judges, validators, scouts, etc.) who are eligible to receive awards from Code4rena will be provided with a link to a questionnaire to determine what, if any, U.S. reporting or withholding obligations exist.

Based on our obligations to operate within tax regulation, completing that questionnaire will be required by participants in order to receive awards.

Detailed information about the process, background, and specific requirements by region can be found [here](https://github.com/code-423n4/org/discussions/146).

# Tax and legal questions

> *Note: Do your own research; this is not legal or tax advice. You should consult a professional in your area.*

We are occasionally asked how wardens should declare Code4rena earnings for tax (or other financial/legal) purposes. You must assess and determine your own best course of action.

Legal entity details for invoices, which can be sent to admin (at) code4rena [dotcom]:

ZC Security Holdings, LLC  
PO Box 2349  
Richland WA 99352 USA
