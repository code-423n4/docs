# Curve Logic for QA and Gas Optimization Reports

[This spreadsheet](https://docs.google.com/spreadsheets/d/1qTQ7PApFMwpUFikcHHtww7p1oncPLj\_y-UY\_SZq6qFg/edit?usp=sharing) includes a demonstration of the curve math, but here is a summary of how it works:

* Start with ‘n’ (100) shares, these go to 1st place.
* The shares for each place are reduced by a multiplier, ‘d’ (0.6), for each position, and ‘d’ is reduced by a multiplier, ‘dd’ (0.2), for each position.
* These shares, divided by the total number of shares, represent the portion of the award pool won.

#### What happens if there are tied report scores?

If two or more QA (or gas optimization) reports have tied scores, they split the _total_ awards for the slots they would otherwise occupy — i.e. if two wardens tie for 3rd place, they split the total awards for 3rd and 4th place. Or if three wardens tie for 3rd, they split the total awards for 3rd, 4th, and 5th place.

#### What if there are no high or medium severity findings?

Total findings pool will be split based on QA report scores unless other arrangements are made.

* Grade-a: outstanding report.
* Grade-b: satisfactory report.
* Grade-c: unsatisfactory report.

#### Can I see some examples of how awards work?

Awards for each contest are [posted on the Code4rena website](https://code4rena.com/contests). See [Numoen](https://code4rena.com/contests/2023-01-numoen-findings), for example. The award calculation for Numoen had the following parameters:

* **Total awards: 50,000 USDC**
* Main award pool: 42,500 USDC
* QA pool: 5,000 USDC
* Gas pool: 2,500 USDC

The table below shows each unique high and medium severity finding (`H-XX`, `M-XX`), QA report (`Q-XX`), gas optimization report (`G-XX`), and the way each submission’s award was calculated:

* `pie` is the number of shares assigned to that report or finding
* `split` is the number of times those shares were divided
* `slice` is the number of shares assigned for that warden’s finding
* each `award` is calculated by `shares * (pot / number_of_shares)`

**Tribe Turbo awards**

| **handle**       | **finding** | **risk** |        **pie**     | **split** |      **slice**      |       **award**        |
| ---------------- | ----------- | -------- | ------------------ | --------- | ------------------- | ---------------------- |
| 'hansfriese'     | 'H-01'      | '3'      |         13         |   1       |         13          | 17615.514252816203     |
| 'RaymondFam'     | 'M-01'      | '2'      | 2.0863980000000004 |   5       | 0.5117580000000002  | 693.4523340763628      |
| '0xhacksmithh'   | 'M-01'      | '2'      | 2.0863980000000004 |   5       | 0.39366000000000007 |  533.424872366433      |
| 'Deivitto'       | 'M-01'      | '2'      | 2.0863980000000004 |   5       | 0.39366000000000007 |  533.424872366433      |
| 'rvierdiiev'     | 'M-01'      | '2'      | 2.0863980000000004 |   5       | 0.39366000000000007 |  533.424872366433      |
| 'peakbolt'       | 'M-01'      | '2'      | 2.0863980000000004 |   5       | 0.39366000000000007 |  533.424872366433      |
| 'hansfriese'     | 'M-02'      | '2'      |        3.9         |   1       | 3.9000000000000004  | 5284.654275844861      |
| 'Allarious'      | 'M-03'      | '2'      |        3.9         |   1       | 3.9000000000000004  | 5284.654275844861      |
| 'hansfriese'     | 'M-04'      | '2'      | 3.1050000000000004 |   2       | 1.7550000000000001  | 2378.0944241301877     |
| 'peakbolt'       | 'M-05'      | '2'      |       2.268        |   3       | 1.0530000000000002  | 1426.8566544781127     |
| 'nadin'          | 'M-04'      | '2'      | 3.1050000000000004 |   2       |        1.35         | 1829.3034031770674     |
| 'adeolu'         | 'M-05'      | '2'      |       2.268        |   3       |        0.405        | 548.7910209531202      |
| 'rvierdiiev'     | 'M-05'      | '2'      |       2.268        |   3       |        0.81         | 1097.5820419062404     |
| 'Breeje'         | 'M-06'      | '2'      | 3.1050000000000004 |   2       |        1.35         | 1829.3034031770674     |
| 'ladboy233'      | 'M-06'      | '2'      | 3.1050000000000004 |   2       | 1.7550000000000001  | 2378.0944241301877     |
| 'Deivitto'       | 'G-01'      | 'g'      |  86.5490783392284  |  15       |  5.76993855594856   | 45.42556528683028      |
| 'Aymen0909'      | 'G-02'      | 'g'      |  86.5490783392284  |  15       |  5.76993855594856   | 45.42556528683028      |
| 'matrix_0wl'     | 'G-03'      | 'g'      |  86.5490783392284  |  15       |  5.76993855594856   | 45.42556528683028      |
| 'RaymondFam'     | 'G-04'      | 'g'      |  86.5490783392284  |  15       |  5.76993855594856   | 45.42556528683028      |
| 'c3phas'         | 'G-05'      | 'g'      |        140         |   2       |         70          | 551.0959153628928      |
| 'Rageur'         | 'G-06'      | 'g'      |  86.5490783392284  |  15       |  5.76993855594856   | 45.42556528683028      |
| 'nadin'          | 'G-07'      | 'g'      |  86.5490783392284  |  15       |  5.76993855594856   | 45.42556528683028      |
| 'IllIllI'        | 'G-08'      | 'g'      |        140         |   2       |         70          | 551.0959153628928      |
| 'cryptostellar5' | 'G-09'      | 'g'      |  86.5490783392284  |  15       |  5.76993855594856   | 45.42556528683028      |
| 'Diana'          | 'G-10'      | 'g'      |  86.5490783392284  |  15       |  5.76993855594856   | 45.42556528683028      |
| 'antonttc'       | 'G-11'      | 'g'      |  86.5490783392284  |  15       |  5.76993855594856   | 45.42556528683028      |
| '0xackermann'    | 'G-12'      | 'g'      |  86.5490783392284  |  15       |  5.76993855594856   | 45.42556528683028      |
| '0xSmartContract'| 'G-13'      | 'g'      |  86.5490783392284  |  15       |  5.76993855594856   | 45.42556528683028      |
| 'ReyAdmirado'    | 'G-14'      | 'g'      |  86.5490783392284  |  15       |  5.76993855594856   | 45.42556528683028      |
| 'NoamYakov'      | 'G-15'      | 'g'      |         91         |   1       |         91          | 716.4246899717607      |
| 'Rolezn'         | 'G-16'      | 'g'      |  86.5490783392284  |  15       |  5.76993855594856   | 45.42556528683028      |
| 'oyc_109'        | 'G-17'      | 'g'      |  86.5490783392284  |  15       |  5.76993855594856   | 45.42556528683028      |
| 'arialblack14'   | 'G-18'      | 'g'      |  86.5490783392284  |  15       |  5.76993855594856   | 45.42556528683028      |
| 'matrix_0wl'     | 'Q-01'      | 'q'      | 38.296345887055885 |   5       |  7.659269177411177  | 142.48406332285143     |
| 'SleepingBugs'   | 'Q-02'      | 'q'      | 38.296345887055885 |   5       |  7.659269177411177  | 142.48406332285143     |
| 'CodingNameKiki' | 'Q-03'      | 'q'      |       69.68        |   1       |        69.68        | 1296.2450205584805     |
| 'IllIllI'        | 'Q-04'      | 'q'      |       160.8        |   3       |        53.6         | 997.1115542757543      |
| '0xAgro'         | 'Q-05'      | 'q'      | 38.296345887055885 |   5       |  7.659269177411177  | 142.48406332285143     |
| '0xSmartContract'| 'Q-06'      | 'q'      |       160.8        |   3       |        53.6         | 997.1115542757543      |
| 'btk'            | 'Q-07'      | 'q'      |       160.8        |   3       |        53.6         | 997.1115542757543      |
| 'chrisdior4'     | 'Q-08'      | 'q'      | 38.296345887055885 |   5       |  7.659269177411177  | 142.48406332285143     |
| 'Rolezn'         | 'Q-09'      | 'q'      | 38.296345887055885 |   5       |  7.659269177411177  | 142.48406332285143     |
