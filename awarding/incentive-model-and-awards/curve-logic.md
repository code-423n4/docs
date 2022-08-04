# Curve Logic for QA and Gas Optimization Reports

[This spreadsheet](https://docs.google.com/spreadsheets/d/1qTQ7PApFMwpUFikcHHtww7p1oncPLj\_y-UY\_SZq6qFg/edit?usp=sharing) includes a demonstration of the curve math, but here is a summary of how it works:

* Start with ‘n’ (100) shares, these go to 1st place.
* The shares for each place are reduced by a multiplier, ‘d’ (0.4), for each position, and ‘d’ is reduced by a multiplier, ‘dd’ (0.2), for each position.
* These shares, divided by the total number of shares, represent the portion of the award pool won.

#### What happens if there are tied report scores?

If two or more QA (or gas optimization) reports have tied scores, they split the _total_ awards for the slots they would otherwise occupy — i.e. if two wardens tie for 3rd place, they split the total awards for 3rd and 4th place. Or if three wardens tie for 3rd, they split the total awards for 3rd, 4th, and 5th place.

#### What if there are no high or medium severity findings?

Total findings pool will be split based on QA report scores unless other arrangements are made.

#### Can I see some examples of how awards work?

Awards for each contest are [posted on the Code4rena website](https://code4rena.com/contests). See [Tribe Turbo](https://code4rena.com/contests/2022-02-tribe-turbo-contest), for example. The award calculation for Tribe Turbo had the following parameters:

* **Total awards: 75,000 USDC**
* Main award pool: 63,750 USDC
* QA pool: 7,500 USDC
* Gas pool: 3,750 USDC

The table below shows each unique high and medium severity finding (`H-XX`, `M-XX`), QA report (`Q-XX`), gas optimization report (`G-XX`), and the way each submission’s award was calculated:

* `pie` is the number of shares assigned to that report or finding
* `split` is the number of times those shares were divided
* `slice` is the number of shares assigned for that warden’s finding
* each `award` is calculated by `shares * (pot / number_of_shares)`

**Tribe Turbo awards**

| **handle**   | **finding** | **risk** | **pie**     | **split** | **slice**   | **award**   |
| ------------ | ----------- | -------- | ----------- | --------- | ----------- | ----------- |
| cmichel      | H-01        | 3        | 6.561       | 5         | 1.3122      | 2964.20219  |
| Picodes      | H-01        | 3        | 6.561       | 5         | 1.3122      | 2964.20219  |
| Ruhum        | H-01        | 3        | 6.561       | 5         | 1.3122      | 2964.20219  |
| CertoraInc   | H-01        | 3        | 6.561       | 5         | 1.3122      | 2964.20219  |
| 0xliumin     | H-01        | 3        | 6.561       | 5         | 1.3122      | 2964.20219  |
| WatchPug     | H-02        | 3        | 8.1         | 3         | 2.7         | 6099.181461 |
| CertoraInc   | H-02        | 3        | 8.1         | 3         | 2.7         | 6099.181461 |
| cccz         | H-02        | 3        | 8.1         | 3         | 2.7         | 6099.181461 |
| cmichel      | M-01        | 2        | 2.43        | 3         | 0.81        | 1829.754438 |
| Picodes      | M-01        | 2        | 2.43        | 3         | 0.81        | 1829.754438 |
| CertoraInc   | M-01        | 2        | 2.43        | 3         | 0.81        | 1829.754438 |
| cmichel      | M-02        | 2        | 2.43        | 3         | 0.81        | 1829.754438 |
| hyh          | M-02        | 2        | 2.43        | 3         | 0.81        | 1829.754438 |
| WatchPug     | M-02        | 2        | 2.43        | 3         | 0.81        | 1829.754438 |
| cmichel      | M-03        | 2        | 2.7         | 2         | 1.35        | 3049.59073  |
| gzeon        | M-03        | 2        | 2.7         | 2         | 1.35        | 3049.59073  |
| cmichel      | M-04        | 2        | 3           | 1         | 3           | 6776.86829  |
| gzeon        | M-05        | 2        | 3           | 1         | 3           | 6776.86829  |
| csanuragjain | Q-01        | q        | 100         | 1         | 100         | 1796.661426 |
| asgeir       | Q-02        | q        | 47.99317244 | 4         | 11.99829311 | 215.5687041 |
| IllIllI      | Q-03        | q        | 115.4772656 | 4         | 28.8693164  | 518.6838717 |
| cmichel      | Q-04        | q        | 47.99317244 | 4         | 11.99829311 | 215.5687041 |
| hyh          | Q-05        | q        | 115.4772656 | 4         | 28.8693164  | 518.6838717 |
| Picodes      | Q-06        | q        | 10.80972451 | 1         | 10.80972451 | 194.2141505 |
| 0x1f8b       | Q-07        | q        | 22.12439422 | 2         | 11.06219711 | 198.7502283 |
| Dravee       | Q-08        | q        | 47.99317244 | 4         | 11.99829311 | 215.5687041 |
| kenta        | Q-09        | q        | 22.12439422 | 2         | 11.06219711 | 198.7502283 |
| robee        | Q-10        | q        | 47.99317244 | 4         | 11.99829311 | 215.5687041 |
| catchup      | Q-11        | q        | 61.03636405 | 4         | 15.25909101 | 274.1542022 |
| defsec       | Q-12        | q        | 61.03636405 | 4         | 15.25909101 | 274.1542022 |
| Ruhum        | Q-13        | q        | 61.03636405 | 4         | 15.25909101 | 274.1542022 |
| WatchPug     | Q-14        | q        | 61.03636405 | 4         | 15.25909101 | 274.1542022 |
| samruna      | Q-15        | q        | 115.4772656 | 4         | 28.8693164  | 518.6838717 |
| pauliax      | Q-16        | q        | 115.4772656 | 4         | 28.8693164  | 518.6838717 |
| nascent      | Q-17        | q        | 60          | 1         | 60          | 1077.996855 |
| nascent      | G-01        | g        | 100         | 1         | 100         | 975.2753344 |
| IllIllI      | G-02        | g        | 60          | 1         | 60          | 585.1652006 |
| WatchPug     | G-03        | g        | 40.8        | 1         | 40.8        | 397.9123364 |
| CertoraInc   | G-04        | g        | 30.3552     | 1         | 30.3552     | 296.0467783 |
| Dravee       | G-05        | g        | 61.86016997 | 3         | 20.62005666 | 201.1023265 |
| gzeon        | G-06        | g        | 61.86016997 | 3         | 20.62005666 | 201.1023265 |
| Picodes      | G-07        | g        | 61.86016997 | 3         | 20.62005666 | 201.1023265 |
| catchup      | G-08        | g        | 30.08126563 | 2         | 15.04063282 | 146.687582  |
| csanuragjain | G-09        | g        | 30.08126563 | 2         | 15.04063282 | 146.687582  |
| kenta        | G-10        | g        | 13.41699406 | 1         | 13.41699406 | 130.8526337 |
| Tomio        | G-11        | g        | 12.69667468 | 1         | 12.69667468 | 123.8275364 |
| 0v3rf10w     | G-12        | g        | 35.29649777 | 3         | 11.76549926 | 114.7460122 |
| robee        | G-13        | g        | 35.29649777 | 3         | 11.76549926 | 114.7460122 |
| samruna      | G-14        | g        | 35.29649777 | 3         | 11.76549926 | 114.7460122 |
