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

1. **Lines of Code count:** Please [run the `prettier` plugin](https://github.com/prettier-solidity/prettier-plugin-solidity) configured to a 120-character line length before counting LOCs. (You don't need to commit these changes to your repo; it's just for getting a standardized LOC count.) 
2. **Test coverage %:** If you have less than 80% test coverage on your contracts, we strongly advise booking a [Test Coverage competition](https://code4rena.com/test-coverage) immediately prior to your Code4rena audit. Doing this can drastically improve the quality of your audit by reducing the number of invalid submissions, incentivizing top-performing wardens, and typically saves you time overall by speeding up the judging and review phase of your audit.


There are other benefits, too, [all outlined here](https://medium.com/code4rena/new-to-code4rena-test-coverage-c548645404f9). 

#### Running `prettier` to provide a standardized LOC count

The default command to run `prettier` is `prettier --write contracts/**/*.sol` or `npx prettier -w $(find contracts src -name "*.sol" | grep -v \.t\.sol)`

We use a 120-character line length standard for scoping, and our default `.prettierrc` is: 

```
{
  "overrides": [
    {
      "files": "*.sol",
      "options": {
        "printWidth": 120,
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

To attract warden participation in the highly competitive engineering market, we work with standard award pool sizes based on the scope of the audit. We regularly evaluate and adjust audit pricing to ensure incentive alignment with wardens. Sponsors always have the option of boosting their award pool, which tends to attract more warden talent and attention.

#### Gas optimization pool

You may opt to allocate a portion of your award pool to gas optimizations; typically we recommend 2.5% of the award pool, but the amount is discretionary. 

### Org fee

There is a fee on top of the determined audit pool, which goes to Code4rena to cover the costs associated with organizing, promoting, and reporting on audits.

### Audit scheduling

Our standard, one-week audits start and end on weekdays at 20:00:00 UTC. Due to high demand, we only lock audits into the schedule after receiving a deposit for the audit; we are unable to make scheduling commitments otherwise.

Note that in order to provide your team with the most efficient and effective code review, we require your team to add ALL code, documentation, and notes to your audit repo at least 2 business days prior to your audit start time. 
