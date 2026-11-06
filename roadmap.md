# Product Roadmap: Kickstarter Launch Check

## Purpose, Audience, and Reference Date

- **Purpose:** show which problem areas Launch Check should work on next, how confident we are, what we have excluded,
  and what would change the direction. It is a direction and confidence record, not a delivery plan.
- **Audience:** the sponsor review (the people who decide whether Launch Check gets a next phase or stays a course
  prototype). In the course setting this is the instructors and the team; in the scenario of `roadmap-review.md` it
  is the agency leadership that saw the client deck `[scenario]`.
- **Decision owner:** Christian Balan. **Reference date:** 2026-11-06. **Status:** proposed by Claude in a delegated
  pass on 2026-11-06 and accepted by the owner the same day (see `roadmap-decision-log.md`, `ai-collaboration-log.md`).
- **Format and why:** Now-Next-Later as **confidence horizons**. Compared in `roadmap-decision-log.md` (D-04)
  against an outcome-based roadmap, a theme roadmap and a timeline: nothing here has a genuine date, two of six
  initiatives rest on unknowns, and the audience needs to see confidence, not sequence.
- **Capacity:** one person, part time, no budget `[assumption for anything beyond the course]`. Now therefore holds at
  most two active initiatives.

## Horizon Definitions

| Horizon | Entry condition | Expected evidence and detail | Exit or review condition |
|---|---|---|---|
| **Now** (active learning, commitment level: exploring) | Problem understood well enough to learn from; objective named; owner named; the next learning step is defined; critical gates identified; fits capacity (max two) | Strongest available evidence; a named learning question; a stop signal | The learning question is answered: continue, adapt, advance, pause or stop is recorded in the decision log |
| **Next** (intended direction, commitment level: intending) | Strategic fit shown; credible evidence for the problem; at least one named unknown, dependency or gate still open | Evidence for the problem; the open questions listed; dependencies named | Dependency or gate resolved and capacity free → Now; or evidence against → Later or removed |
| **Later** (options we watch, commitment level: option) | Relevant to an objective; evidence for the problem or a plausible hypothesis; low confidence on the remedy | An early signal and named unknowns only; no detail | A review trigger fires (new evidence, I01 or I02 result) or relevance is lost → removed |

Items do not slide left with time. They move only on evidence or on a recorded decision. Relabelling these columns
as quarters would not work: no column has a date, and two columns hold work that cannot start until a gate opens.

## Roadmap

| Horizon | Initiative | Objective and expected outcome | Evidence / confidence | Dependencies / gates | Next learning or review trigger |
|---|---|---|---|---|---|
| **Now** | **I01 Learn from creators** | O1: we know whether creators want a pre-launch chance, when, what it would change, and how they read a band; a baseline for O1 exists | F12 (gap), S05, S07 / needed: high; result: unknown | Privacy gate (no names, no transcripts in the repo) | First conversations analysed → review trigger T1 |
| **Now** | **I02 Lawful and current data basis** (first in order after R1) | O3, O2: a written decision on intended use, taken with the sponsor, and a data basis whose terms allow it; or an explicit stay-non-commercial decision | F11, S06 D3, F08 / options exist: medium; legal reading: unknown | Legal gate, privacy gate; owner decision on commercial intent; sponsor informed that no paid offering exists before this resolves | Candidate sources and their terms listed, legal reading obtained → review trigger T2 |
| **Next** | **I04 Honest presentation of the estimate** | O1: creators read the number as calibrated starting odds relative to the average and do not treat inputs as levers | F07, F10, S06 D13/D18/D19 / medium-high | Needs I01 (comprehension tested with creators); accessibility gate for any page | Moves to Now when T1 fires; blocked from Now by capacity today |
| **Next** | **I03 Trustworthy estimate on current campaigns** | O2: estimate reflects recent campaigns; calibration per band and ranking quality measured and shown | F07, F08 / method proven: medium; result on new data: unknown | **Blocked by I02**; cost gate before any serving path | Moves to Now when T2 opens a lawful current source; stays blocked otherwise |
| **Later** | **I05 Deliberate choices on goal and length** | O1: creators choose goal and length on purpose, some build an audience first | F02, F03, F04 / patterns: strong; behaviour change: assumption | Needs I01 and I04; must never become an optimizer | Reviewed at T1: promoted only if creators ask for it |
| **Later** | **I06 See beyond the plan** (paused after R1) | O2: biggest misses shrink where campaign content is lawful and available pre-launch | F09 / low; remedy is an AI suggestion | Legal, privacy and cost gates; needs I02 and I03 | Paused at R1: no learning step is spent on it until T2; removed if no lawful content source exists |

**Review triggers**

- **T1:** I01 returns its first analysed creator conversations.
- **T2:** I02 returns a legal reading of the current licence and at least one assessed alternative source.
- **T3:** any new evidence on current funding rates (for example a published Kickstarter statistic) that contradicts
  the 2017 level of 37 %.
- **T4:** a stakeholder request to commit to a date, a feature or a commercial launch (handled through the request
  process in module 05, never by adding it to a horizon directly).

## Explicit Exclusions

| Excluded | Why | Could it come back? |
|---|---|---|
| A what-if optimizer or "best settings" recommender | Review 2 showed it gives misleading advice: one day less moved the example from 51 % to 72 % without changing real odds (F04, F10, S06 D19) | Only a goal-only what-if with a monotonic constraint, and only if I01 shows creators need it |
| Any promise or wording of guaranteed success, "coming soon" or a launch date | No commitment is resourced; the estimate is calibrated odds, not a verdict (F07) | No |
| Other crowdfunding platforms | No data, no evidence, outside the focus (S01) | Only with a lawful dataset and creator evidence for that platform |
| A commercial service on the current dataset | Licence is CC BY-NC-SA 4.0: non-commercial (F11) | Only via I02 with a different data basis or a legal opinion |
| Predicting the amount pledged or the number of backers | Those are the leakage columns; the project removed them (S06 D5); a different problem | No, not in this roadmap |
| A paid tier, accounts or a mobile app before I01 | No demand evidence (F12); building before learning | After T1, if evidence supports it |
| Deploying anything before the owner's cost check | Owner's cost rule: cost per visit at today's traffic and at 50,000 visitors must be measured and approved first | Yes, once measured and approved |
| Generated campaign advice (for example an AI that writes the pitch or picks the rewards) | Added in the audit (A07): no evidence, outside the focus on the launch decision, and it would make the check look like a success recipe | Only as its own initiative with its own evidence, never inside Launch Check |
| A paid launch, or any launch date, in the next phase | Added after review R1: the sponsor's request `[scenario]` has no lawful data basis (F11) and no demand evidence (F12); a date has no genuine constraint behind it | Only after T2 (I02 resolved) and T1 (I01 shows demand), as a new decision |

**Overlap note (audit A08):** I04 and I05 both concern what a creator sees. They stay separate because they answer
different questions (how the number is read vs which patterns help a choice) and have different stop signals; I05
inherits every presentation rule of I04.

## Commitment Language

| Level | Applies to | Wording we use |
|---|---|---|
| **Exploring** | I01, I02 | "We are investigating this problem and its evidence." |
| **Intending** | I03, I04 | "This is a priority direction, subject to the named gate or dependency." |
| **Option** | I05, I06 | "We are watching this; it has evidence for the problem but not for the remedy." |
| **Committed** | nothing | No bounded scope has approved resources beyond the course exercise. |
| **Forecast** | nothing | No date or result is forecast. The only numbers with confidence attached are measured model metrics on 2009 to 2018 data. |
| **Fixed obligation** | the data licence (CC BY-NC-SA 4.0), the privacy rule, the owner's cost gate | Binding constraints with owner Christian Balan. |

Customer-facing or sponsor-facing views of this roadmap may hide detail but may not strengthen any of these levels.

## Changes Since the First Version

| Date | Change | Reason | Record |
|---|---|---|---|
| 2026-11-06 | Exclusion added: generated campaign advice | Audit finding A07 | `ai-collaboration-log.md` |
| 2026-11-06 | Review R1: I02 placed first in order and extended with the intended-use decision; I06 paused; exclusion added for a paid launch or date in the next phase; T4 fired and handled as a request | Sponsor request `[scenario]` plus the observed licence (F11) | `roadmap-review.md`, decision log D-08 to D-11 |

No commitment level was raised by these changes. Nothing moved into Now; nothing was promised.
