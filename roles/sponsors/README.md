---
description: >-
  Sponsors purchase a competitive audit, which includes an award pot to incentivize
  wardens to audit their project.
---

# Sponsors

## Sponsoring an audit

Any project can submit a request to sponsor a C4 audit. Just [complete this form](https://code4rena.typeform.com/i-want-an-audit) and we will reach out to set up a meeting or send over a scoping questionnaire to get the ball rolling.

One of our team members will review your repo, assess your responses and contracts, and recommend which audit package would be appropriate for your scope. 

**If you decide to move ahead with an audit, all relevant code will be made public at the time of your audit in most cases.** We also offer KYC and private competitions if privacy is a need; just let our team know.  

### Scoping

Our scoping form asks for several technical details to help our team assess the scope of your audit. There are several scoping considerations beyond a simple sLOC count. Here are two we're often asked about: 

1. **Lines of Code count:** Please [run the `prettier` plugin](https://github.com/prettier-solidity/prettier-plugin-solidity) configured to a 100-character line length before counting LOCs. (You don't need to commit these changes to your repo; it's just for getting a standardized LOC count.) 
2. **Test coverage %:** If you have less than 80% test coverage on your contracts, we strongly advise booking a [Test Coverage competition](https://code4rena.com/test-coverage) immediately prior to your Code4rena audit. Doing this can drastically reduce the number of invalid submissions, and the time invested in a C4 test coverage competition is more than saved by speeding up the judging and review phase of your audit -- both of which lead to a higher quality outcome for you as a sponsor, and quite often a faster turnaround time overall. 

There are other benefits, too, [all outlined here](https://medium.com/code4rena/new-to-code4rena-test-coverage-c548645404f9). 

#### Running `prettier` to provide a standardized LOC count

The default command to run `prettier` is `prettier --write contracts/**/*.sol` or `npx prettier -w $(find contracts src -name "*.sol" | grep -v \.t\.sol)`

We use a 100-character line length standard for scoping, and our default `.prettierrc` is: 

```
{
  "overrides": [
    {
      "files": "*.sol",
      "options": {
        "printWidth": 100,
        "tabWidth": 4,
        "useTabs": false,
        "singleQuote": false,
        "bracketSpacing": false,
      }
    }
  ]
}
```


### Determining pot size

We work together with you as the sponsor to set the appropriate award pool amount for your audit pool at or above current audit floor prices. To attract warden participation in the highly competitive engineering market, we work with standard award pool sizes. We regularly evaluate and adjust audit pricing to ensure incentive alignment with wardens. Sponsors always have the option of providing a larger-than-floor pot size, which tends to attract more warden talent and attention.

### Gas optimization pool

By default, 2.5% of the award pool is allocated to valid gas optimizations. We encourage all sponsors to keep this in place, as we can help each other be conscious of ways to minimize gas fees for users -- and indeed some sponsors may which to allocate a higher percentage of the award pool to this purpose. 

Some projects may not wish to create a separate incentive for gas optimizations, and removing it should be discussed with Code4rena staff during the pre-audit setup phase.

### Org fee

There is a fee on top of the determined audit pool, which goes to the Code4rena DAO to cover the costs associated with organizing, promoting, and reporting on audits.

### Audit scheduling

Our standard, one-week audits start and end on weekdays at 20:00:00 UTC. Due to high demand, we only lock audits into the schedule after receiving a deposit for the audit; we are unable to make scheduling commitments otherwise.

Note that in order to provide your team with the most efficient and effective code review, we require your team to add ALL code, documentation, and notes to your audit repo at least 48 hours prior to your audit start time. 
