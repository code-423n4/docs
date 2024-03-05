# Audit process

### Before the audit

* If you haven’t already, join the [C4 Discord](https://discord.gg/code4rena) server and let us know you’re interested in sponsoring an audit in the `#💼i-want-c4-to-audit-our-code` channel.
* We'll ask you to share your current smart contracts and answer a few questions about the scope you’d like wardens to focus on. If you decide to move ahead with an open competitive audit, **the relevant code will be made public** at the time of your audit.
* After your code has been reviewed, Code4rena staff will contact you to iron out the details.
* Once we’ve received a deposit, we will finalize scheduling and begin to promote the audit.
* In order to launch your audit on schedule, your audit repo (including the `README`) must be completely set up and shared with us at least 48 business hours (2 business days) before your audit is scheduled to start. This ensures we have time to review it and help you finalize any last-minute details.

### During the audit

* Be prepared for a **code freeze for the duration of the audit** — critical because it maintains a level playing field. We want to ensure everyone's looking at the same code, no matter when they look during the audit. (Note: this includes your own repo, since a PR can leak alpha to our wardens!)
* We ask for a member or members of your engineering team to be available in the C4 Discord server in order to answer wardens’ questions via DM.
* Please avoid discussing any issues submitted by wardens in an open channel, as this could give hints to other wardens.

### After the audit

Your work will play a role in developing a public report of the audit.

* Sponsors review findings, help identify duplicates, and provide comments as you confirm, acknowledge, or dispute wardens’ findings.
* As your team works to mitigate issues, most sponsors will create a PR for each issue addressed in your codebase and link to it in the C4 finding issue.

### How Code4rena mitigation reviews work

- While judging for your audit contest is underway, your team works through whatever mitigations you choose to pursue. For each mitigation, you link them back to the findings in the repo.
- After judging is finalized, the valid findings in the repo will be assigned a set of IDs containing a risk prefix + number (e.g. H-01 for a high-risk issue, M-03 for a medium). Mitigations of all High and Medium issues (we call them "HMs" for short) will be considered in-scope. We don't expect you to mitigate every QA / Gas issue, so we exclude those from mitigation reviews.
- Most mitigation reviews are invitational competitions between 3-5 of the top-performing wardens from your audit. Code4rena staff will post the opportunity for RSVP as soon as judging is finalized for your initial audit. 
- Usually we can kick off the mitigation review within a few days of judging (assuming your mitigations have been completed), and they typically run for 5 days.
- Wardens can submit both reviews of the mitigations (e.g. mitigation confirmed/disputed,) as well as newly-introduced High and Medium risk issues.
- After the mitigation review closes, there's a similar sponsor review and judging phase to how our audit contests work, and then C4 staff will produce a report summarizing your audit and mitigation review. 
