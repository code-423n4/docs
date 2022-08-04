
What constitutes “fairness” in Code4rena?

# Fundamental principles

These are the fundamental principles that underly how we look at the question of “fairness” in Code4rena.

1. Code4rena aims to be a fair and impartial system.
1. Where the system is insufficient or vague, we depend on the judgment of fair and impartial individuals.
1. When we depend too heavily on the judgment of individuals, we work to improve the system long-term in iterative and sustainable ways.
1. Because we are working every day within the constraints of the systems we have, we aim to be patient with the time and consideration that improvement takes and gracious toward the individuals tasked by the system with making difficult decisions.

# Expectations of participants

- Sponsors should be able to trust that Code4rena as a system is working to help them secure their code and that their funds are a good investment toward that end.
- Wardens should be able to have clear rule expectations of contests they contribute to—as clear as possible within the constraints.
- Judges should be impartial and free to act independently to do what they see best in a given contest within the guidelines they are provided.

# Role of hired staff (Code4 Corporation)

The role of staff is regulatory, supportive, and administrative:

- Code4 is a neutral party in contests dedicated to serving and collaborating with all sides of the market in driving the success of Code4rena as a platform.
- Code4 is responsible for improving documentation, process, and tools in support of the goals and expectations of each of the parties involved in Code4rena, providing information, context, and guidance to sponsors, judges, and wardens within the rules.
- Code4 has no role in determining the outcomes of findings and does not put its hand on the scale in individual contests.
- Code4 does have a role to provide sponsors, judges, and wardens with historical context on the intent of rules so that those rules can be applied appropriately when ambiguity is present.

# Ambiguity and evolution

In all cases of ambiguity that exist within rules and the application of those rules (including tools provided), judges have been and will be called upon to make judgment calls which some set of the community may disagree with.

Making these decisions is the most important and difficult part of their role.

There are generally two poles of legal interpretation:

- strict construction (“letter of the law”)
- liberal construction (“spirit of the law”)

Both apply interpretation of “intent” and “meaning”. People have their preferences and are entitled to those, but both ends of the spectrum are logically valid.

Given the nascence of Code4rena as a completely new idea, judges have been encouraged to take a liberal construction approach given so much of the ‘law’ of C4 is not documented, but must be interpreted based on context and intent.

Early on, we decided that judges would be given absolute discretion to allocate awards based on their view of wardens’ comparative performance using the tools, documentation, and methodology provided.

At the same time, Code4 (staff) are constantly trying to make improvements to tools, documentation, and process which allow for the continued scaling of the community and platform.

As Code4rena scales and as more wardens have joined who do not have full historical context, it becomes clear that reliance on that undocumented context and intent is insufficient for purposes of fairness.

It is increasingly important to codify consensus on how decisions are and will be made so that wardens have the ability to make their best decisions.

# What constitutes ‘valid’ and ‘consistent’?

The validity of an audit report submission is not based on whether it is ‘true’ or not. A report may contain a finding which is factually 'true' (the most literal interpretation of 'valid'), but if it does not add value or if it is not presented in such a way that adds value to a sponsor, it may be deemed invalid by a judge.

This may seem harsh and exclusive, but it is essential to consider that Code4rena runs audit contests, not gotcha-hunts, and Code4rena offers guaranteed payout for valid submissions. This means that wardens are providing a service to sponsors and the product of those services should meet what judges feel is a minimum standard in order to be deemed of value.

Auditing is serious, disciplined work that should provide high value consultative expertise to the people paying for the work.

In that light, judges are right to have high standards. Some judges have always had higher standards than others, and some judges have applied higher standards in later contests than they did in earlier ones.

While this may be seen as ‘inconsistent’, it is also true that standards within a specific contest will always be informed by the overall quality of a contest’s submissions, and that the standard in a judge’s mind is always going to be evolving based on the aggregate quality of submissions that judge has been exposed to and the decisions other judges have made.

The correct assessment when this happens is not that a judge is being inconsistent, it is that they have objectively observed that the quality of competition has increased, and that observation shapes their view of the whole set of submissions; they are consistent in valuing submissions in the context of each other, which is a central way that performance in a competition is measured.

# Continued evolution of rules

## Rubric

Because wardens should be able to have clear rule expectations of contests they contribute to, and because newer wardens do not have historical context on the intent of various rules, it is important that we continue to document a rubric of what constitutes the subjective threshold of validity.

An initial rubric has been outlined [here](https://github.com/code-423n4/org/discussions/34) and a finalized version of this rubric will soon be added to formal documentation and judging procedure.

Note well:

- the purpose of this proposed rubric is not to be 'more strict'. It's to continue to work toward a standard and mutually agreed expectations as to what constitutes the base level of quality for a submission.
- the scale of this rubric hasn't been used yet (someone who scored a 5 or a 10 or a 3 on some prior QA report was doing so on a band where 1 to 100 is the equivalent of 60 to 100 in the new rubric)
- by the time we ask judges to implement this, we will have a Chrome extension in place that will aid them in scoring and which will have the rubric visible to them as they grade so they are aware of the implied meaning of their grade per the rubric.

## Limiting the scope of judges’ role

Since day 1 of C4, the website and docs has described the judge's role as:

> Judges allocate awards to wardens based on performance.

In this, combined with judges’ say being final, it is not unreasonable to interpret judges as being weighted with the task of doing their best to make a fair judgment on a contest's award allocation, causing them at times to question the tooling and process and whether they are correctly interpreting the spirit of the law.

This language puts too much burden on judges and it's going to be eliminated in favor of the more explicit:

> Judges decide the severity, validity, and quality of findings and rate the performance of wardens.

This ensures that award amounts themselves cannot be brought into the discussion or the judges feel compelled by circumstances to have an opinion on whether the award allocation itself is fair; they are simply making a determination and rating warden’s submissions based on severity, validity, and quality.

We will henceforth make it clear that when judges encounter a nuanced case where the letter of the law is being followed by a warden’s submission but seems to be gamed against the spirit of the law, judges have a right to indicate that in their assessment of a warden’s submission, but will be bound by the letter of the law.

At the same time, wardens must note that codifying the above-mentioned [rubric](https://github.com/code-423n4/org/discussions/34) as a part of our rules and documentation will significantly expand judges’ ability to assess findings as invalid.

We will also ensure that any changes to rules and documentation made by Code4 are only effective for contests that have not yet started. However, note well that both announcements of clarifications of rules interpretation and application of the results of those rules will not ever be considered 'changes' to rules. If a rule or guideline exists and has only been weakly suggested and not strictly enforced, it may be applied or enforced to a greater extent in any contest with zero notice since the rule was already fully communicated.

As a result, wardens should be able to increasingly rely on judges taking a “strict construction” (“letter of the law”) method of interpretation of the rules.

## Further clarification notes

We will be working to continue to document how wardens can expect judges will interpret the meanings of “severity”, “validity”, and “quality” and we encourage wardens to raise issues where they feel the rubric on these is unclear.

While the QA award curve’s asymptotic floor could be seemingly interpreted to pay regardless of content (and in fact, it seems the coded implementation of the curve did just that), but the intent was not for invalid, low-quality, and/or solely non-critical submissions to receive guaranteed pay. Judges may have applied this inconsistently either through a lack of consistency in their process or a lack of understanding of the tool, but going forward these types of submissions will not be awarded.

If you benefited from this oversight in the past, count yourself lucky! But when future outcomes deviate from past precedent on this, understand that awarding invalids at the asymptotic floor was not the intent of the curve.
