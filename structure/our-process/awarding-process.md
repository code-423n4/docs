---
description: >-
  This is a high level overview of the C4 awarding process. We have an
  increasingly detailed operational manual in Notion.
---

# Awarding process

At the conclusion of a contest, sponsors review wardens’ findings and express their opinions with regard to severity of issues. Judges evaluate input from both and make the ultimate decision in terms of severity and validity of issues. (See [How to judge a contest](../../roles/judges/how-to-judge-a-contest.md) for more detail.)

In making their determination, judges change labels on GitHub issues and fill out a Google spreadsheet. (The spreadsheet is generated from JSON data created upon form submission. This JSON data serves as a snapshot of the original submission’s severity in order to ensure the sponsors’ labels do not interfere with the originally intended severity indicated by the warden.)

The data in the spreadsheet is used to generate the awards using the [awardCalc script](https://github.com/code-423n4/awardcalc). It should be possible to reverse engineer awards using a CSV of this sheet and this script.

While all results are final and all contest funds are irrevocably disbursed as part of the process, the intent is that results should stand up to scrutiny. The award process current relies on scripts and data sources primarily written by one mediocre developer. As such, the award process is considered in beta and it is not unlikely there are flaws. These scripts and data sources are being actively improved.

Once awards are determined, we generate a CSV file enumerating funds to be sent. Distribution is then initiated using disperse.app and sent to multisig signers for completion of payment.
