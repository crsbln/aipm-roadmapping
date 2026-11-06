# Initiative Register

**Reference date:** 2026-11-06 · Labels as defined in `strategy-brief.md`. Objectives O1 to O3 are in the strategy
brief; opportunities O01 to O06 and findings F01 to F12 are in `evidence-map.md`.

An initiative here is a problem area with an intended outcome and a learning signal. It is **not** a feature.
Possible solutions are kept separately in "Candidate Approaches" below, so that the initiative survives if a
particular solution fails. Each initiative names the signal that decides whether it continues, adapts or stops.

| ID | Opportunity / problem | Objective | Evidence | Expected outcome | Confidence | Risks / gates | Dependencies | Next learning |
|---|---|---|---|---|---|---|---|---|
| **I01 Learn from creators** | O06 (no creator evidence), feeding O01 and O04 | O1 | F12 (the gap itself); S05 names creators as the stakeholder; S07 reports two audiences that saw the deck but no reaction | We know whether creators want a pre-launch chance, at which moment, what decision it would inform, and how they read a percentage and a band. A baseline for O1 exists. | High that it is needed; no confidence on what it will show `[unknown]` | Recruiting creators without a platform relationship; bias toward successful creators who are easy to find; **privacy gate:** no names or transcripts in the repository or in Claude; the prototype may shape what people say | None: the existing prototype and deck can be shown | Do creators want this, when, and what would they do with the number? **Stop signal:** if most creators say the number would not change any decision, stop building the estimate as a creator product and reconsider the context (for example as teaching material). |
| **I02 Lawful and current data basis** | O03 (trust decays), gate for everything that touches data | O3, O2 | F11 (CC BY-NC-SA 4.0, nine years old); S06 D3 ("licence restrictions"); F08 (levels drift) | A written decision on the intended use (non-commercial educational tool, or a product), taken with the sponsor after review R1, and a data basis whose licence and terms allow that use and cover recent campaigns; or an explicit decision to stay non-commercial on the current data. | Medium that lawful options exist `[AI suggestion]`; the legal reading is `[unknown]` | **Legal gate:** licence of any source, Kickstarter terms of use for collection, attribution and share-alike duties; **privacy gate:** creator names in titles; collection cost and effort unknown | Owner decision on commercial intent (see `roadmap-review.md`) | Which candidate sources exist, under which terms, at which cost? **Stop signal:** if no lawful current source is found, I03 and I06 stop and Launch Check stays an educational prototype on the 2018 data. |
| **I03 Trustworthy estimate on current campaigns** | O03 | O2 | F07 (calibrated on average, per-year error up to 4 points); F08 (time test 0.757, recall 81 to 75, yearly rate 28 to 46 %) | The estimate shown to a creator reflects recent campaigns; calibration error per band and ranking quality are measured and published alongside the number; drift is checked on a trigger, not forgotten. | Medium: the method is proven on the old data; the result on new data is `[unknown]` | Retraining can silently change what the bands mean (communication risk); **cost gate:** training is offline and near free, but any serving path must pass the owner's cost check before deployment | I02 (no current data, no retraining) | How far did levels drift since 2018 and does the ranking still hold? **Stop signal:** if ranking on recent data falls to the level of the goal rule (about 0.64), the plan-only model is no longer worth showing. |
| **I04 Honest presentation of the estimate** | O04 (misreading and gaming) | O1 | F07 (bands: 14, 37, 62 of 100); F10 (what-if misled, "high" misread); S06 D13, D18, D19 | Creators read the number as calibrated starting odds relative to the 36 % average, understand what it cannot see, and do not treat inputs as levers. | Medium-high: the fixes exist in the prototype; comprehension by real creators is `[unknown]` | Creators can still re-run with tweaked inputs; the presentation must stay honest if the model is retrained (I03); **accessibility gate** for any public page | I01 (to test comprehension with real creators, not reviewers) | Do creators correctly interpret the band and the "what the check cannot see" note? **Stop signal:** if creators consistently read the band as a verdict despite the wording, the estimate should not be shown as a single number at all. |
| **I05 Deliberate choices on goal and length** | O01, O02 | O1 | F02 (goal bands), F03 (category gap at equal goals), F04 (round-number dips in every goal band) | Creators see their category's funding rate and goal distribution and the round-number pattern as patterns, and choose goal and length on purpose; some decide to build an audience first. | Medium: patterns are strong `[observed]`; behaviour change is `[assumption]` | Easily collapses into advice ("pick 29 days") that the evidence does not support; confounding between goal and category; must never become an optimizer (exclusion) | I01 (what creators actually ask), I04 (same presentation rules) | Does seeing the pattern change the chosen plan, and do creators find it fair rather than manipulative? **Stop signal:** if creators mainly use it to game the number, stop. |
| **I06 See beyond the plan** | O05 (blind to campaign quality) | O2 | F09 (biggest misses are quality-driven; title words add only 7 of 100) | Where campaign content is available before launch and lawful to use, the estimate distinguishes campaign quality and its biggest misses shrink. | Low: the limitation is observed; the remedy is speculative `[AI suggestion]` | **Legal gate:** content collection and licence; **privacy gate:** creator-identifying content; **cost gate:** text or image models cost far more per check than a tabular model; pre-launch content may not be final | I02 (data basis), I03 (a current baseline to beat) | Is campaign text available pre-launch, and does it add ranking quality in an offline test against the plan-only model (0.754)? **Stop signal:** gain within noise, or no lawful content source. |

## Candidate Approaches

Kept separate from the initiatives on purpose. None of these is approved; they are `[AI suggestion]` unless marked.

**I01 Learn from creators**

- Short interviews with creators who launched (funded and not funded) and with creators who are planning; ask about
  the launch decision before mentioning the prototype.
- Show the existing command-line result or the deck's board-game example and watch how the person reads it.
- A short survey in a creator community, only with the community's permission.
- Use the deck's "what the check cannot see" slide as a conversation starter.

**I02 Lawful and current data basis**

- Read the CC BY-NC-SA 4.0 terms and decide what "non-commercial" means for the intended use `[constraint]`.
- Check Kickstarter's terms of use and public pages for what may be collected and how.
- Look for licensed or openly licensed recent datasets, or a data partnership; record each option with its terms.
- Fallback that is always available: stay an educational, non-commercial tool on the 2018 data and say so.

**I03 Trustworthy estimate on current campaigns**

- Retrain the same pipeline on recent data; recalibrate on the latest year (recommended but not done in the project,
  S06); publish per-band calibration next to the estimate.
- Keep the time-based test (train on older, test on newer) as the standard check before any model change.
- A drift check triggered by a date or by a change in the published funding rate.

**I04 Honest presentation of the estimate**

- The current rules from the project: probability first, bands named relative to the 36 % average, no what-if, a
  "based on" list of factors, the "cannot see" note `[observed, S06]`.
- Show the band before the exact number, or the band only, and test which one creators read correctly.
- A one-run design (one check per plan) to discourage tweaking.

**I05 Deliberate choices on goal and length**

- Show the category's funding rate and the goal distribution of funded campaigns in that category.
- Show the round-number pattern as a pattern with its caveat, not as a recommendation.
- A goal-only what-if with a monotonic constraint, named in review 2 as the condition for any future what-if; still
  excluded until I01 shows a need `[observed, S06]`.

**I06 See beyond the plan**

- Offline experiment: add campaign text (description, reward list) as features and compare against 0.754 with the same
  split, metrics and leakage rules. A text model or a neural network is an option here, not before.
- Image or video signals (thumbnails) with a convolutional network: only if text already adds signal and the cost gate
  allows it. See the study notes for what these methods are and what they would need.
