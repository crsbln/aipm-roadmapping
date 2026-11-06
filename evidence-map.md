# Evidence and Opportunity Map

**Reference date:** 2026-11-06 · Labels as defined in `strategy-brief.md`.

## Research Question and Scope

> What do we actually know, and not know, about (a) whether a pre-launch funding-chance check would help Kickstarter
> creators, and (b) whether the current Launch Check estimate can be trusted and lawfully used?

**Scope:** evidence already available from the Week 9 project repository and from public pages checked on the
reference date. No new research was run for this map. The biggest limitation is stated up front: **there is no
evidence from creators at all** (no interviews, surveys or usage data). Everything about what creators want is an
assumption until I01 in the initiative register returns.

## Sources

| Source ID | Source type | Participants / sample | Date | Limitations |
|---|---|---|---|---|
| **S01** Kickstarter Projects dataset (Kaggle, kemical), file `ks-projects-201801.csv`; aggregated numbers in the project's `reports/results.json` | Observational platform data, scraped by a third party | 378,661 raw rows; 372,293 finished campaigns after cleaning (133,956 funded, 238,337 not) | Campaigns 2009 to January 2018; numbers generated 2026-10-21 | Ends in January 2018; no campaign content (video, rewards, updates, promotion); no creator experience or identity; canceled campaigns counted as not funded; associations, not causes |
| **S02** Model evaluation in the project notebook `01_kickstarter_eda_and_modeling.ipynb` | Quantitative evaluation | 297,834 training and 74,459 held-out test campaigns; time-based test trained before 2016, tested from 2016 | October 2026 | Test set was looked at across review rounds (project decision D17); one dataset, one platform |
| **S03** Independent reviews of the project: `CRITIQUE.md`, `CRITIQUE_2.md`, `CRITIQUE_3.md`, `DESIGN_REVIEW.md` | Expert review (method, slides, design) | Three method reviews and one design review | October 2026 | Reviewers were not creators; they judged method and communication, not product value |
| **S04** Kaggle dataset page for S01, read in the browser | Public web page | — | Read 2026-11-06 | Page text only: "License CC BY-NC-SA 4.0", "Updated 9 years ago", "Data are collected from Kickstarter Platform". Not legal advice; Kickstarter's own terms not reviewed |
| **S05** Course assignment brief `01_assignment.md`, Option B | Project brief | — | October 2026 | A course framing ("help potential creators assess their chances"), not a market observation |
| **S06** Project decision record (`docs/SUMMARY.md`, decisions D1 to D19) and the presenter cheat sheet | The team's own documentation | — | October 2026 | Self-reported; written by the same team |
| **S07** Owner's project note of 2026-10-23: the client deck was to be shown to an agency and to government officials | Stakeholder context, reported | — | 2026-10-23 | Identity of the agency and any reaction are not recorded; nothing can be built on it |
| **GAP** Creator research | — | 0 creators | — | No interviews, surveys, support tickets or usage logs exist |

## Findings and Insights

| ID | Finding `[observed]` | Source IDs | Interpretation / insight `[interpreted]` | Contradictions or gaps |
|---|---|---|---|---|
| **F01** | 36 % of 372,293 finished campaigns were funded (133,956); 64 % got nothing (238,337). | S01 | Two of three creators invest weeks for nothing; the decision to launch is the high-stakes moment. | How much work and money a failed campaign costs a creator is not in the data `[unknown]`. |
| **F02** | Funding rate falls steadily with the goal: up to 1k USD 49 %, 1k to 2.5k 46 %, 2.5k to 5k 40 %, 5k to 10k 35 %, 10k to 25k 30 %, 25k to 50k 21 %, 50k to 100k 14 %, over 100k 6 %. Median goal 5,500 USD. | S01 | The goal is the largest lever a creator fully controls. | A smaller goal also caps what can be raised (S06); goal and category are entangled (Technology median 20,000 USD). |
| **F03** | By category: Dance 62 %, Theater 60 %, Comics 54 %, Music 49 % at the top; Crafts 24 %, Journalism 21 %, Technology 20 % at the bottom. The gap survives at equal goals: 1k to 5k USD goals, Dance 69 % vs Technology 26 %. Funded Technology campaigns asked a median 10,000 USD, unfunded ones 20,200 USD. | S01, S06 | Category is the model's strongest input; low-rate categories over-ask. | Cause unproven: the "few, generous backers from the creator's own circle" pattern in Dance, Theater and Music is a hypothesis from S06, not a finding. |
| **F04** | 166,483 campaigns (45 %) run exactly 30 days and are funded 32 % of the time, vs 46 % at 29 days and 50 % at 31. Every round length checked (15, 20, 25, 30, 35, 40, 45, 60 days) dips below its neighbours; 60 days is lowest at 19 %. The pattern holds within each goal band. | S01 | Round numbers mark the default or a habit, not a plan; "chose on purpose" is a proxy for planning quality. | It cannot be turned into "pick 29 days": changing that one input moves the estimate from 51 % to 72 % without changing real odds (S06 D19, S03 review 2). |
| **F05** | Country and launch month add little: permutation importance country 7, launch weekday 2, launch month 1 (category = 100). | S01, S02 | Where and when a campaign launches barely matters once goal, category and length are known. | Non-US countries have small samples (Germany 4,096 campaigns, 23 %). |
| **F06** | Final model (gradient boosting) on 74,459 unseen campaigns: ROC-AUC 0.754 vs 0.637 for the rule "goal under 5,500 USD"; F1 0.619 vs 0.524; at equal share labelled "promising", precision 53 vs 45 of 100; Brier score 0.189. Logistic regression 0.728 and random forest 0.718 in cross-validation. | S02 | Meaningfully better than a rule of thumb, far from certain; the plan alone explains a limited part of success. | Tuning changed cross-validated log loss by 0.0003, i.e. within noise (S06). |
| **F07** | Probabilities are calibrated on average (predicted 35 % → 35 % funded; 5 → 5, 65 → 65, 91 → 94). Per launch year they are off by up to about 4 points. Chance bands: under 25 % → 14 of 100 funded (34 % of campaigns); 25 to 50 % → 37 (39 %); 50 % or more → 62 (27 %). | S02 | The number can honestly be shown as a probability relative to the 36 % average; the low band is a good warning; the high band is no guarantee. | Calibration was not redone on the latest year on purpose (prototype, not deployed; S06). |
| **F08** | Time-based test (train before 2016, test 2016 onwards): ROC-AUC 0.757, but recall falls from 81 to 75 and rates drift. Yearly funding rate: 46 % (2011), 43 % (2013), 28 % (2015), 33 % (2016), 37 % (2017). | S01, S02 | The ranking holds across years; the levels do not. Anything shown to a 2026 creator rests on data that ends in January 2018. | No data after January 2018 exists in the project `[unknown: today's levels]`. |
| **F09** | Biggest misses: small board-game campaigns that failed and large technology or food campaigns that succeeded. Importance: category 100, goal 84, length 32, title words 7. | S02 | The model is blind to campaign quality (video, rewards, audience, promotion), which often decides the outcome. | Whether any of that is observable before launch is open `[unknown]`. |
| **F10** | Reviews found: class weighting inflated probabilities by about 11 points (fixed); the what-if feature produced misleading advice (removed); 51 % must not be called "high" (bands renamed relative to 36 %); the test set had been reused across rounds (disclosed, D17). | S03, S06 | The main product risk is misinterpretation and false precision, not raw accuracy. | Reviewers reasoned about creators; no creator was observed reading the output. |
| **F11** | The dataset page states licence CC BY-NC-SA 4.0 (attribution, non-commercial, share-alike), "Updated 9 years ago", data "collected from Kickstarter Platform". The project's decision D3 already noted "licence restrictions". | S04, S06 | The current data cannot support a commercial product, nor current estimates. Any new data basis needs its own licence and terms check. | Kickstarter's own terms for collecting data were not reviewed `[unknown]`. |
| **F12** | No creator has been interviewed, surveyed or observed. The "potential creator" stakeholder comes from the assignment brief. | GAP, S05 | Every statement about creator needs, moments of use and willingness to change a plan is an assumption. | S07 (agency and officials) adds context but no recorded reaction. |

## Opportunities

Written as problems and outcomes, not features. Confidence reflects the evidence behind the problem **and** the
intended outcome; where the outcome rests on an assumption the confidence says so.

| ID | Affected group and problem | Intended outcome | Supporting findings | Confidence | Unknowns |
|---|---|---|---|---|---|
| **O01 Choosing by default** | Creators keep the 30-day default and round numbers; such campaigns are funded less often than their neighbours, and creators have no way to see this before launch. | Creators pick goal and campaign length on purpose, with their odds in view. | F02, F04 | Medium: the pattern is strong `[observed]`; the benefit to a given creator is `[assumption]`. | Do creators know the default costs them? Would they change it? Is length a cause or only a marker? |
| **O02 Over-asking in hard categories** | Technology, Food, Journalism and Crafts creators set goals their category rarely reaches. | Creators set a realistic goal for their category, or decide to build an audience before launching. | F02, F03 | Medium: category gap is robust at equal goals; the feasibility of lower goals is `[unknown]`. | Can hardware or food projects lower their goal (cost floors)? Is community, not category, the driver? |
| **O03 Trust decays with time** | A creator in 2026 would get an estimate learned from 2009 to 2018 campaigns; funding levels moved by up to 18 points between years. | Estimates reflect current platform conditions, with a known calibration error. | F07, F08, F11 | High that it is a problem; low on how to solve it (no lawful current data identified). | Is there a lawful, current source of campaign data? How much did levels drift since 2018? |
| **O04 Misreading and gaming the number** | Creators may read 51 % as "high", or re-run the check with tweaked inputs until the number rises, acting on habits the model learned rather than on real odds. | The estimate is understood as calibrated starting odds relative to the average, not as a verdict and not as a lever. | F04, F07, F10 | Medium-high: reviewers found it and the team fixed the prototype; real creators have not been observed. | How do real creators read bands and percentages? Do they re-run? |
| **O05 Blind to campaign quality** | A creator with a strong campaign but an average plan receives an average number; the biggest model errors are exactly these cases. | The estimate distinguishes campaign quality where quality is observable before launch and lawful to use. | F09 | Low: the limitation is observed; the remedy is speculative. | Is campaign content available and final before launch? Is collecting it lawful? Does it add signal? |
| **O06 Unvalidated demand** | Nobody has asked creators whether, when and why they would use a pre-launch check; the product idea comes from a course brief. | Evidence on demand, moment of use and the decision the check informs, before anything is built further. | F12, S05, S07 | Not applicable: this is the gap itself. | Everything about users: who, when, what they do next, what they would pay (if anything). |

**Contradictions kept visible:** F02 vs the cap on money raised; F04 vs the what-if trap (the strongest pattern is
also the easiest to misuse); F06 vs F09 (good ranking, blind to what matters most in the hardest cases).

**Missing groups:** creators who never launched because they judged their odds too low (not in the data);
non-English and non-US creators (small samples); creators after 2018 (no data).
