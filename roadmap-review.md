# Roadmap Review R1

**Date:** 2026-11-06 · **Reviewer / decision owner:** Christian Balan (analysis prepared by Claude; decisions
proposed, owner review pending) · **Roadmap version reviewed:** the first version of `roadmap.md` of the same day.

## Review Context

Two things arrived together, and they are labelled differently on purpose:

1. **Observed, new to the roadmap:** the Kaggle page of the training dataset states the licence **CC BY-NC-SA 4.0**
   (attribution, non-commercial, share-alike) and "Updated 9 years ago" `[observed, S04, F11]`. The project had
   noted "licence restrictions" in decision D3 but never spelled out what they were.
2. **Scenario, fictional, introduced for this exercise:** the sponsor who saw the client deck asks the team to
   offer Launch Check as a **paid pre-launch service** to creators in the next phase, ideally "in time for the spring
   campaign season" `[scenario]`. No real sponsor has said this.

This is review trigger **T4** (a stakeholder request to commit to a feature, a date or a commercial launch). It is
handled through the request process of module 05: clarify the problem, record evidence and urgency, check fit and
constraints, compare with current initiatives, decide, record, communicate.

## Outcomes and New Evidence

- The request's underlying problem is legitimate and already on the roadmap: **O3, legitimate and sustainable use.**
  What is new is the pressure to decide the intended use now.
- The new fact (F11) makes one thing certain: **the current dataset cannot be the basis of a paid product.**
  Non-commercial is a licence term, not a preference. Share-alike additionally binds any derivative dataset.
- The request also contains a **date** (a season). No contract, regulation or coordinated launch stands behind it;
  module 04's test for a genuine date fails.
- No new evidence about creators arrived. F12 still holds: nobody knows whether creators would pay, or use, a check.

## Assumptions Confirmed or Rejected

| Assumption | Status | Evidence |
|---|---|---|
| "The data can be reused for whatever product we build" (implicit in the Week 9 data-product slide) | **Rejected** | F11: CC BY-NC-SA 4.0 |
| "Recent data will be available when we need it" (implicit in the first draft of I03, see A04) | **Still unconfirmed** | No lawful current source identified; I02 open |
| "The ranking holds over time" | Confirmed only up to January 2018 | F08: time-based test ROC-AUC 0.757 |
| "A sponsor wants a paid product" | Scenario, not evidence | `[scenario]`; even if real, a request is not demand evidence (module 06) |
| "Creators want a pre-launch chance" | Still an assumption | F12 |

## Initiative Decisions

| Initiative | Continue / adapt / advance / pause / stop | Reason | Approved change | Communication impact |
|---|---|---|---|---|
| I01 Learn from creators | **Continue** | The request makes the demand question more urgent, not less; interviews need no dataset | None | Sponsor hears that demand is unknown and is the first thing we learn |
| I02 Lawful and current data basis | **Advance** (first in order within Now; scope extended) | It is now the gate for the sponsor's wish as well as for I03 and I06; the intended use (commercial or not) must be decided with the sponsor before any data work | Description extended: "a written decision on the intended use, taken with the sponsor"; sponsor informed that no paid offering exists before I02 resolves (D-09) | Plain message: "a paid service is not possible on the current data; here is what we need to find out first" |
| I03 Trustworthy estimate on current campaigns | **Continue as Next, blocked** | Nothing changed except that the block is now explained by a licence term, not only by missing data | None; blocked status already recorded | "We intend to retrain, subject to a lawful data basis" (not "we will") |
| I04 Honest presentation of the estimate | **Continue as Next** | A paid product would raise the stakes of misreading (F10), which strengthens I04's case, but it still needs creators from I01 | None | None beyond the roadmap view |
| I05 Deliberate choices on goal and length | **Continue as Later** | No new evidence | None | None |
| I06 See beyond the plan | **Pause** | Any content collection carries the same licence and terms questions, plus privacy; spending learning effort on it now would suggest an activity nobody can lawfully start | Marked "paused until T2" (D-10) | Not mentioned to the sponsor as a direction |
| The request itself: "paid Launch Check by spring" | **Not added** | No lawful data basis (F11), no demand evidence (F12), no genuine date; adding it would turn an option into a promise | Recorded as a stakeholder request in the decision log (D-08); exclusion added for a paid launch or a date in the next phase (D-11) | The sponsor is told what would have to be true first: T2 (lawful basis) and T1 (demand) |

No previous commitment was rewritten: the roadmap had, and still has, nothing at the "committed" level. The
commitment table in `roadmap.md` is unchanged.

## Updated Risks, Dependencies, and Commitments

- **New risk:** the sponsor hears "not possible" and loses interest before I01 and I02 return. Mitigation: show
  the walkthrough's section 6 (what the review changed and why) rather than a bare refusal.
- **New dependency:** I02 now depends on a conversation with the sponsor about the intended use, not only on a legal
  reading.
- **Unchanged constraint:** the owner's cost gate applies to any serving path, paid or not.
- **Commitments:** none added. Exploring: I01, I02. Intending: I03, I04. Options: I05, I06 (I06 paused).

## Next Review Trigger

- **T2:** I02 returns a legal reading of CC BY-NC-SA 4.0 for the intended use and at least one assessed alternative
  source. This decides whether I03 unblocks and whether any paid offering can ever be discussed.
- **T1:** I01 returns its first analysed creator conversations. This decides whether I04 enters Now and whether a
  product, paid or free, is worth building at all.
- Whichever fires first triggers review R2.
