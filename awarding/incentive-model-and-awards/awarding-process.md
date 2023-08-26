---
description: >-
  This is a high level overview of the C4 awarding process. 
---

# Awarding process

At the conclusion of an audit, sponsors review wardens’ findings and express their opinions with regard to severity of issues. Judges evaluate input from both and make the ultimate decision in terms of severity and validity of issues. (See [How to judge an audit](../../roles/judges/how-to-judge-a-contest.md) for more detail.)

In making their determination, judges add labels to Github issues, while the original submission data (including the warden's proposed severity rating) is preserved via a JSON data file. 

The judge's decisions are reviewed by the sponsoring project team and by [+backstage wardens](https://docs.code4rena.com/roles/certified-contributors/backstage-wardens) via a 48-hour QA process, to ensure fairness and quality. 

Judging data is used to generate the awards using Code4rena's award calculation script, which factors in:

- Risk level
- Validity
- Number of duplicates
- Grade (A, B, C; Satisfactory/Unsatisfactory)
- In some cases, "partial duplicate" status

 It should be possible to reverse engineer awards using a combination of two CSV files:
 
 - [`findings.csv`](https://code4rena.com/community-resources/findings.csv): valid Code4rena findings
 - [`contests.csv`](https://code4rena.com/community-resources/contests.csv): Code4rena audits 

Once awards are determined, we generate a CSV file enumerating funds to be sent. Distribution is then initiated using disperse.app and sent to multisig signers for completion of payment.

## If you don't see your award in your wallet:

For most Code4rena contests, awards are sent on the Polygon network (usually in USDC) within 1-2 weeks of the awards announcement.

If awards have been sent, and you don’t see them in your wallet, please verify that you have imported the USDC token into your Polygon wallet. (MetaMask instructions [here](https://support.metamask.io/hc/en-us/articles/360015489031-How-to-display-tokens-in-MetaMask).)

If you still don’t see the award in your wallet, please [open a help desk ticket](https://code4rena.com/help).

# Tax and legal questions

> *Note: Do your own research; this is not legal or tax advice. You should consult a professional in your area.*

We are occasionally asked how wardens should declare Code4rena earnings for tax (or other financial/legal) purposes. Due to the nascent nature of DAOs, we are unable to provide reliable information in this area. You must assess and determine your own best course of action.

Audit contest rewards are distributed by the DAO, which does not have a legal personality.

The DAO has designated Code4rena Foundation as its agent via [a governance action](https://github.com/code-423n4/org/discussions/13) [approved by DAO members](https://polygonscan.com/tx/0x8fbe178e34a7ae03a5e0d1f49f23e38f3a1c0d1186a67920d33196a89f79da98) for purposes of entering into contractual agreements. However, wardens are not in any contractual agreement with the Foundation [unless they are certified](https://code4rena.com/certified-contributor-summary/).

[Documentation of Code4rena Foundation can be found here.](https://github.com/code-423n4/org/tree/main/foundation)

Code4rena Foundation may or may not be able to provide further information; their contact information is below.

Code4rena Foundation

[Campbell Law](mailto:campbell@silversidemanagement.ky)

P.O. Box 31489
2nd Floor Whitehall House
238 North Church Street
George Town
Cayman Islands KY1-1206
