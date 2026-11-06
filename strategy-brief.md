# Strategy Brief: Kickstarter Launch Check

**Reference date:** 2026-11-06 · **Decision owner:** Christian Balan (AI Project Manager, neuefische AIPM) ·
**Roadmap audience:** the sponsor review (the people who decide whether Launch Check gets a next phase or stays a course prototype)

**How to read the labels.** Every claim in these files carries one of these tags:
`[observed]` evidence from data, code or a page we looked at · `[interpreted]` our reading of observed evidence ·
`[assumption]` something we believe but have not checked · `[scenario]` a fictional element introduced for the exercise ·
`[constraint]` a rule, licence or obligation · `[AI suggestion]` an idea Claude proposed that nobody has validated ·
`[unknown]` a question we cannot answer yet. Source IDs (S01 …) and finding IDs (F01 …) point into `evidence-map.md`.

## Product Context

Launch Check is the data product idea from our Week 9 machine-learning project (neuefische AIPM, October 2026,
team Kashif Kazmi, Furkan Yurttepe, Christian Balan). It estimates the chance that a Kickstarter campaign reaches its
funding goal, using only what a creator knows **before** launch: funding goal, category, country, campaign length,
launch date and title length. `[observed, S02, S06]`

- **Why it matters:** Kickstarter is all-or-nothing. Of 372,293 finished campaigns (2009 to January 2018) only 36 %
  were funded; the other 64 % got nothing for weeks of work. `[observed, F01]`
- **State today:** a notebook, a command-line check (`uv run kickstarter-check`), a saved gradient-boosting model, a
  16-slide client deck and a technical deck, three independent reviews. Not deployed, no users, no creator research.
  `[observed, S02, S03, S06]`
- **Data basis:** the public Kaggle dataset "Kickstarter Projects" (kemical), licensed CC BY-NC-SA 4.0
  (non-commercial, share-alike), last updated about nine years ago. `[observed, S04]` `[constraint]`
- **Previous prioritization project:** none exists for this context; the roadmap starts from the project's own
  decision record (D1 to D19 in the project summary) and the review findings. `[observed, S06]`
- **Who took part in this roadmap exercise:** the decision owner alone. The two teammates were not consulted; nothing
  here claims their agreement. `[constraint]`

## Vision

> Creators decide to launch, to change their plan, or to wait, with an honest picture of their odds instead of a hope.

The beneficiary is the creator. The change is an informed launch decision. The vision does not prescribe a tool:
an estimate, a pattern explainer, a checklist or a conversation could all serve it. `[interpreted]`

## Target Groups and Priority Needs

| Group | Priority need | What we know | What we do not know |
|---|---|---|---|
| **Primary: first-time and small creators** planning a Kickstarter campaign | Know their chances and which parts of the plan they can still change `[assumption]` | 45 % of all campaigns keep the 30-day default and are funded less often than campaigns one day shorter or longer; the median goal is 5,500 USD `[observed, F04, F02]` | Whether creators know this, want to know it, and would change a plan because of it `[unknown, F12]` |
| **Secondary: creators in low-success categories** (Technology 20 %, Journalism 21 %, Crafts 24 %, Food 25 %) | Set a goal their category can realistically reach, or decide to build an audience first `[assumption]` | Technology campaigns ask for a median 20,000 USD; funded ones asked 10,000 USD, unfunded ones 20,200 USD `[observed, F03]` | Whether hardware and food projects can lower their goal at all (cost floors) `[unknown]` |
| **Out of focus** | Backers, Kickstarter as a company, agencies running many campaigns, other platforms | — | — |

## Strategic Choices

| Choice | Decision | Evidence or rationale |
|---|---|---|
| **Where we focus** | Kickstarter creators, before launch, using plan-level inputs only. One platform, one moment of decision. | The data covers only Kickstarter and only plan-level fields `[observed, S01]`; the all-or-nothing rule makes the pre-launch decision the high-stakes one `[interpreted, F01]`; the assignment named potential creators as the stakeholder `[observed, S05]`. |
| **How we intend to create value** | An honest, calibrated chance of funding, shown relative to the 36 % average, plus the three evidence-backed patterns (goal, length, category) presented as patterns, never as a recipe. | The model beats a rule of thumb (ROC-AUC 0.754 vs 0.637) and its probabilities are calibrated on average `[observed, F06, F07]`; the reviews showed that a what-if optimizer misleads creators `[observed, F10]`. |
| **Capabilities or advantages** | A documented, reproducible pipeline with leakage checks, calibration and a time-based test; three review rounds; a team habit of saying what the number cannot see. | Project repository, reviews and decision record `[observed, S02, S03, S06]`. This is a method advantage, not a data advantage: the data is public and old `[interpreted]`. |
| **What we will not pursue** | A what-if optimizer or "best settings" recommender; any promise of success; other crowdfunding platforms; a commercial service on the current dataset; predicting the amount pledged; a paid tier before creators have been heard. | What-if rejected in project decision D19 and review 2 `[observed, S06, F10]`; no data for other platforms `[observed, S01]`; licence is non-commercial `[constraint, F11]`; no demand evidence `[unknown, F12]`. |

## Objectives and Signals

| Objective | Outcome signal | Baseline | Target or direction | Evidence source |
|---|---|---|---|---|
| **O1 Creators make informed launch decisions** | Share of creators who, after a check, deliberately change goal or length, or decide to postpone, and can say why | None: no users yet `[unknown]` | Establish a baseline in discovery (I01); direction: up. No number is set because none can be supported. | F12 (gap), S05 |
| **O2 The estimate stays trustworthy on today's campaigns** | Calibration error per chance band on recent campaigns; ranking quality (ROC-AUC) on recent campaigns | Calibrated on average on 2009 to 2018 data; per-year error up to about 4 points; time-based test ROC-AUC 0.757 with recall falling from 81 to 75 `[observed, F07, F08]` | Calibration within 5 points per band and ROC-AUC at or above 0.75 on recent data, once recent data exists `[AI suggestion: thresholds proposed, not validated]` | S02 |
| **O3 Launch Check can be used legitimately and run sustainably** | A data basis whose licence and terms permit the intended use; measured cost per check before any deployment | Dataset is CC BY-NC-SA 4.0; nothing deployed; running cost 0 `[observed, F11]` | A lawful basis for the intended use (commercial or not) is decided and documented; cost per check at 50,000 visits is measured and approved by the owner before anything goes live | S04, owner's cost rule `[constraint]` |

Two objectives are about the creator's outcome and the estimate's quality; O3 is a guard-rail objective. A revenue
objective was proposed and rejected: there is no lawful commercial data basis and no demand evidence
(see `ai-collaboration-log.md`, entry A02).

## Constraints, Risks, and Unknowns

**Constraints**

- `[constraint]` The training data is licensed CC BY-NC-SA 4.0: no commercial use, derivatives under the same licence.
  Any other use needs a different data basis or a legal opinion. (F11)
- `[constraint]` Kickstarter's own terms of use for collecting campaign data have not been reviewed. (S04 limitation)
- `[constraint]` No personal data of creators goes into the repository or into Claude. Creator names exist in the
  dataset's title column and must not be surfaced.
- `[constraint]` Owner's cost rule: nothing is deployed until the cost per visit at today's traffic and at 50,000
  visitors is measured and approved.
- `[constraint]` Capacity for this exercise: one person, part time, no budget. `[assumption]` for anything beyond.

**Risks**

- The estimate is misread as a verdict ("51 % is high") or gamed by re-running with tweaked inputs. (F10, F04)
- The model has learned creator habits, not causes; guidance derived from it can mislead. (F04, F10)
- Levels drift: funding rates moved between 28 % and 46 % per year; data ends January 2018. (F08)
- The model cannot see campaign quality (video, rewards, network), its biggest misses. (F09)
- Teammates and the agency shown the deck have not agreed to any of this. (S07)

**Unknowns**

- Do creators want a chance estimate, when, and what would they do with it? (F12)
- Is there a lawful, current source of campaign data for the intended use? (F11)
- Do the 2009 to 2018 patterns still hold in 2026? (F08)
- Can creators in hard categories lower their goals at all? (F03)
