In order to create opportunities for contributions which rely on establishment of trust, Code4rena allows community members to opt into certifying their identity and entering into a simple agreement.

Wardens who have provided ID verification and a signed agreement may be eligible for:

- Immediate access to repo after contest concludes;
- Contributing to post-contest triage and QA;
- Scout role (new, focused on scoping and pre-contest code intel)
- Judge role

Additional opportunities we are considering include: 

- Providing mitigation review services (compensated)
- Offering consulting services through C4
- Certain contest bonus token awards which may be restricted from US persons due to regulations or token grant agreements
- Private or invite-only contests if we offer in the future
- May be a factor in maxing out awards in the future

## Who is eligible to be a certified contributor?

In order to justify the investment of paying our legal team to certify a warden, applicants must meet the following criteria:

1. Participate as a warden in at least 3 Code4rena contests, and submit at least 1 high severity finding OR at least 3 contests with a top-3 finish in either the QA or gas report;
2. Complete the [Certified Contributor Application form](https://code4rena.com/certified-contributor-application/); and
3. Agree to the Certified Contributor Terms and Conditions (see [application form](https://code4rena.com/certified-contributor-application/)).

## **Certification process and constraints**

C4 continues to focus on privacy, so our certification process is done through a third-party that is bound by confidentiality. The certification process is as follows:

1. An eligible warden submits the [Certified Contributor Application form](https://code4rena.com/certified-contributor-application/).
2. The DAO's AML/KYC agent, [Provenance](https://provenance.company/), contacts the warden to certify their identity.
3. Provenance certifies a warden as having completed their identity verification process, and having signed an agreement binding them to code of conduct and non-disclosure. Code4 Corporation and the Code4rena DAO do NOT have access to personal information, simply the verified knowledge that the warden was certified.
4. Code4 Corporation contacts the certified warden to let them know their application has been approved.

### Constraints

- In the event that a certified warden was alleged to have violated the agreement, the Code4rena Cayman Foundation could hire an attorney to pursue remediation.
- In the event a certified C4 warden was alleged to be involved in an exploit, Provenance would provide identifying information to authorities.

# **Certified warden professional conduct guidelines**

Wardens may lose the privilege of participating in post-contest triage and inconsistency bounties by violating the code of professional conduct which will be outlined in the certified warden agreement. This code will ask wardens to:

- take an objective, collegial, and intellectually open tone in considering and discussing all findings
- treat wardens and sponsors with respect and an assumption of positive intent
- avoid engaging in any discussion and evaluation of issues they submitted themselves except to answer a question or provide additional context requested by a judge or sponsor
- treat the contents of all findings as private and confidential until the contest report is made public.

# FAQ

### What is the purpose behind having an option for wardens to become certified, and why does ID verification factor into that?

Aside from bug reports, most security services are not trustless activities, and there really isn’t a way to make them so without adding immensely unworkable complexity (who audits the auditors?) or putting disproportionate burden on trusted parties ("sorry, cmichel and alex, for the sake of C4, you have to verify this anon advice on this bugfix is legit and not elaborate social engineering")

The wider the surface area of interaction with anonymous wardens, the more we need to manage the complexity of both trust and sybil attacks. Keeping absolute anonymity limited to bug reports is where the line can be comfortably drawn.

But even beyond our own comfort, ultimately a C4 audit is a *productized service* and sponsors are *customers*. Customers of security products and services generally have higher level of anxiety around trust—and justifiably even more so in the dark forest of smart contract security. This approach provides a path for accountability in the extremely unlikely event of malicious behavior, yes, but it also provides a way for us to know that wardens have verifiably signed an agreement regarding non-disclosure, professionalism, and respect for privileged information from sponsors that they presumably intend to honor.

Note that certified wardens are still able to be anon for basically all intents and purposes. Unless the shit hit the fan, the C4 DAO wouldn't know who they were, the Foundation wouldn't know who they were, Code4 Corp wouldn't know who they were—just Provenance and attorneys who'd be required to keep that information confidential.

### What would constitute a warden being alleged to have performed an attack?

First, let’s define “allegation”: an accusation based on circumstantial evidence would not be sufficient, as Provenance (the certifier) would have a duty to keep personal information confidential. There would need to be a formal, legal allegation wherein Provenance was **subpoenaed** to provide the information as verification of identity.

So this is really only relevant in a case where there is sufficient evidence that would stand up in a court of law clearly demonstrating that the specific warden in question was involved in an attack. Provenance would not dox wardens at the request of people grasping at straws in a witch hunt.
