# Audit process

## During the submission phase

* Be prepared for a **code freeze for the duration of the audit** — critical because it maintains a level playing field. We want to ensure everyone's looking at the same code, no matter when they look during the audit. (Note: this includes your own repo, since a PR can leak alpha to our wardens!)
* We ask for a member or members of your engineering team to be available in the C4 Discord server in order to answer wardens’ questions via DM.
* Please avoid discussing any issues submitted by wardens in an open channel, as this could give hints to other wardens.

## After submissions close

Your work will play a role in developing a public report of the audit.

* Sponsors review findings and provide comments as you confirm, acknowledge, or dispute wardens’ findings.
* As your team works to mitigate issues, most sponsors will create a PR for each finding addressed in your codebase and link it to the relevant Code4rena finding.

## How Code4rena mitigation reviews work

- While judging for your audit is underway, your team works through whatever mitigations you choose to pursue. For each mitigation, you link them back to the findings in the repo.
- After judging is finalized, the valid findings in the repo will be assigned a set of IDs containing a risk prefix + number (e.g. H-01 for a high-risk issue, M-03 for a medium). Mitigations of all High and Medium issues (we call them "HMs" for short) will be considered in-scope. We don't expect you to mitigate every QA / Gas issue, so we exclude those from mitigation reviews.
- Most mitigation reviews are invitational competitions between 3-5 of the top-performing wardens from your audit. Code4rena staff will post the opportunity for RSVP as soon as judging is finalized for your initial audit. 
- Usually we can kick off the mitigation review within a few days of judging (assuming your mitigations have been completed), and they typically run for 5 days.
- Wardens can submit both reviews of the mitigations (e.g. mitigation confirmed/disputed,) as well as newly-introduced High and Medium risk issues.
- After the mitigation review closes, there's a similar sponsor review and judging phase to how our audit contests work, and then C4 staff will produce a report summarizing your audit and mitigation review. 
