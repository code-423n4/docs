---
description: In order to create opportunities for contributions which rely on establishment of trust, Code4rena allows community members to opt into certifying their identity and entering into a simple agreement.

---

Contributors who have provided ID verification and a signed agreement may be eligible to participate in:

- Private or invite-only contests
- Scout role (focused on scoping and pre-contest code intel)
- [Judging](/roles/judges/README.md)
- ["Backstage" warden opportunities](backstage-wardens.md) (post-contest triage and post-judging QA)
- Providing mitigation review services
- Offering solo audit and consulting services through C4

Additional opportunities we are considering include: 
- Certain contest bonus token awards which may be restricted from US persons due to regulations or token grant agreements
- May be a factor in maxing out awards in the future

## **Certification process and constraints**

C4 continues to focus on privacy, so our certification process is done through a third party ([Provenance](https://provenance.company/)) that is bound by confidentiality. The certification process is as follows:

1. An eligible contributor submits the [Certified Contributor Application form](https://code4rena.com/certified-contributor-application/), and agrees to the Certified Contributor Terms and Conditions (see the application form).
1. The DAO's AML/KYC agent, [Provenance](https://provenance.company/), contacts the contributor to certify their identity.
1. Provenance certifies a contributor as having completed their identity verification process, and having signed an agreement binding them to code of conduct and non-disclosure. Code4 Corporation and the Code4rena DAO do NOT have access to personal information, simply the verified knowledge that the contributor was certified.
1. Code4 Corporation contacts the certified contributor to let them know their application has been approved.

### Constraints

- In the event that a certified contributor was alleged to have violated the agreement, the Code4rena Cayman Foundation could hire an attorney to pursue remediation.
- In the event a certified C4 contributor was alleged to be involved in an exploit, Provenance would provide identifying information to authorities.

# FAQ

### What is the purpose behind having an option for wardens to become certified, and why does ID verification factor into that?

Aside from bug reports, most security services are not trustless activities, and there really isn’t a way to make them so without adding immensely unworkable complexity (who audits the auditors?) or putting disproportionate burden on trusted parties ("sorry, cmichel and alex, for the sake of C4, you have to verify this anon advice on this bugfix is legit and not elaborate social engineering")

The wider the surface area of interaction with anonymous wardens, the more we need to manage the complexity of both trust and sybil attacks. Keeping absolute anonymity limited to bug reports is where the line can be comfortably drawn.

But even beyond our own comfort, ultimately a C4 audit is a *productized service* and sponsors are *customers*. Customers of security products and services generally have higher level of anxiety around trust—and justifiably even more so in the dark forest of smart contract security. This approach provides a path for accountability in the extremely unlikely event of malicious behavior, yes, but it also provides a way for us to know that wardens have verifiably signed an agreement regarding non-disclosure, professionalism, and respect for privileged information from sponsors that they presumably intend to honor.

Note that certified wardens are still able to be anon for basically all intents and purposes. Unless the shit hit the fan, the C4 DAO wouldn't know who they were, the Foundation wouldn't know who they were, Code4 Corp wouldn't know who they were—just Provenance and attorneys who'd be required to keep that information confidential.

### What would constitute a warden being alleged to have performed an attack?

First, let’s define “allegation”: an accusation based on circumstantial evidence would not be sufficient, as Provenance (the certifier) would have a duty to keep personal information confidential. There would need to be a formal, legal allegation wherein Provenance was **subpoenaed** to provide the information as verification of identity.

So this is really only relevant in a case where there is sufficient evidence that would stand up in a court of law clearly demonstrating that the specific warden in question was involved in an attack. Provenance would not dox wardens at the request of people grasping at straws in a witch hunt.

### What documents are accepted by Provenance in relation to proof of residence?

Provenance will provide exact details after application submission. As of June 1, 2022, the list of acceptable documents includes: 
- Utility bill clearly stating the service address and mailing address with the individual’s name (note: telephone, cellular and credit card bills are not acceptable as these may be mailed to any address)
- Bank statement
- Rental or lease agreement
- Local authority document (e.g. property tax bill, council tax bill etc.)

Note: the document has to be less than 3 months old.

### How long does it take to get certified? 

Once you submit the [Certified Contributor Application form](https://code4rena.com/certified-contributor-application/), Provenance typically emails you within one business day. (If you don't see an email within that time frame, we recommend checking your spam folder for email from `@provenance.company` or `provenancecompliance.com`.)

Provenance will provide you with detailed instructions. If you have all the available documents, the process can usually be completed within a day. 

It will take longer if you need to assemble the necessary documents.