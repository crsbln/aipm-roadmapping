# AI Collaboration Log

**Working mode, stated plainly.** On 2026-11-06 the owner (Christian Balan) asked Claude Code to read the lessons and
templates and to produce the seven artifacts in one delegated pass, without being available for an interview. Claude
therefore (1) used only evidence it could point to (the Week 9 project repository, its reviews, the Kaggle page), (2)
labelled every assumption, unknown and AI suggestion, (3) audited its own first draft against the Phase 5 list, and
(4) recorded here what it proposed, what it corrected or rejected in that audit, and why. **Every disposition below is
Claude's proposal; the owner's review is the final decision.** Where the owner later accepts, corrects or rejects an
entry, the last column is updated. The log records material interventions, not the whole session.

| # | Claude contribution | Accepted, corrected, or rejected? | Evidence or reason | Artifact affected | Owner review |
|---|---|---|---|---|---|
| A01 | Proposed the Week 9 project Launch Check as the roadmap context instead of a new fictional context | Accepted (by Claude's audit) | Only context with shareable quantitative evidence (S01 to S06); a fictional context would have required inventing all evidence | all | pending |
| A02 | First objective draft contained "O4 revenue from a paid tier" `[AI suggestion]` | **Rejected** | No lawful commercial data basis (F11) and no demand evidence (F12); a revenue objective would have made the paid-tier request in R1 look pre-approved | `strategy-brief.md` | pending |
| A03 | First plan for the material change was a **fictional** "legal review finds the dataset unusable" scenario | **Corrected:** replaced by the observed licence after checking the Kaggle page in the browser (S04); only the sponsor's commercial intent stays fictional and is labelled `[scenario]` | A fact that can be observed must not be presented as fiction; the handout requires scenario evidence to be labelled | `evidence-map.md` (F11), `roadmap-review.md` | pending |
| A04 | Drafted I03 as "Retrain on 2024 to 2026 campaigns" in **Now** | **Corrected:** moved to Next, dependency on I02 added, the year range removed | No lawful current dataset exists in the project; the year range implied data availability that nobody has established (F08, F11) | `initiative-register.md`, `roadmap.md` | pending |
| A05 | Suggested a Later item "Extend to Indiegogo and other platforms" `[AI suggestion]` | **Rejected**, recorded as an exclusion | No data, no evidence, outside the focus (S01, strategic choice "where we focus") | `roadmap.md` exclusions | pending |
| A06 | First placement had three initiatives in Now (I01, I02, I04) | **Corrected:** I04 moved to Next | Capacity is one part-time person (assumption stated in the brief); I04's learning question (do creators read the band correctly?) cannot be answered before I01 delivers creators to test with | `roadmap.md` | pending |
| A07 | Audit question "what is absent because it was forgotten?" surfaced that generated campaign advice (AI-written pitch or rewards) was neither included nor excluded | Accepted: exclusion row added | A likely stakeholder request; no evidence; outside the launch-decision focus; would make the check look like a success recipe | `roadmap.md` exclusions | pending |
| A08 | Audit flagged I04 and I05 as possible duplicates | Accepted: kept separate, overlap note added | Different questions (reading the number vs choosing goal and length) and different stop signals; I05 inherits I04's presentation rules | `roadmap.md` | pending |
| A09 | Wrote O2 targets "calibration within 5 points per band, ROC-AUC at or above 0.75 on recent data" | **Turned into an unknown:** kept as thresholds but labelled `[AI suggestion: proposed, not validated]` | The baseline (0.754, drift up to 4 points) is observed; the thresholds are a proposal nobody has approved | `strategy-brief.md` | pending |
| A10 | Carried the assignment's framing "creators want to know their chances" as a user need in the first brief draft | **Corrected:** labelled `[assumption]`, with F12 recording that no creator has been asked | S05 is a course brief, not research; module 02: a stakeholder framing is not evidence | `strategy-brief.md`, `evidence-map.md` | pending |
| A11 | Proposed naming the agency from the owner's note as the roadmap audience | **Rejected:** audience defined as "the sponsor review"; the agency appears only as `[scenario]` in R1 | The note (S07) records that the deck was to be shown, not who decided what; naming them would claim an agreement that does not exist | `strategy-brief.md`, `roadmap.md` | pending |
| A12 | Drafted I01 with "8 to 12 creator interviews" | **Corrected:** number removed, "a small set of conversations" kept | A sample size without a recruiting plan is false precision; the register now states the learning question and the stop signal instead | `initiative-register.md` | pending |
| A13 | Walkthrough draft said "we will retrain the model once the data is available" | **Corrected** to "we intend to retrain, subject to I02" | Module 05 commitment language: an intention with an open gate is not a "will" | `walkthrough.md` | pending |
| A14 | Review R1 analysis: identified affected evidence (F11, F12), objectives (O3, O2), initiatives (I02, I03, I06), dependencies and the sponsor message | Accepted as analysis; the decisions (D-08 to D-11) are proposals | Each decision lists the options considered; the owner can pick differently | `roadmap-review.md`, `roadmap-decision-log.md` | pending |
| A15 | A web-fetch helper reported that the Kaggle page returned no content; Claude did not fall back to memory for the licence but read the rendered page in the browser | Accepted (process) | The licence is the central fact of R1; it had to be observed, not recalled | `evidence-map.md` S04 | pending |

## What Claude Was Not Allowed to Do, and Did Not Do

- Invent creator quotes, personas, survey results, usage numbers or stakeholder agreement. The only user-side
  evidence is the explicit gap F12.
- Add a date, a launch quarter or a commitment. None exists in any file; the one requested date in R1 is a labelled
  scenario and was refused.
- Promote the course brief (S05) or the owner's note (S07) into evidence of demand.
- Pick the final roadmap. Every horizon placement and exclusion is a recorded proposal with options and reasons.

## Quality Check

- [x] Claude did not invent user evidence, targets, feasibility, or commitments.
- [ ] Material interpretations and roadmap changes received human approval. *Pending: the owner reviews entries
      A01 to A15 and decisions D-01 to D-12 and marks each accepted, corrected or rejected.*
- [x] At least one meaningful contribution was corrected or rejected (A02, A03, A04, A05, A06, A09 to A13).
- [x] Sensitive information and full chat transcripts are excluded.
