# Important product decisions

This is not a roadmap or changelog. It records why LapMind deliberately does
some things—and deliberately does not do others.

## D-001 — Why voice first?

**Decision:** Race-critical information should be available without looking at
the phone.

**Why:** HUD-off and VR driving created the project. A telemetry dashboard alone
does not solve that problem.

## D-002 — Why optional Discord?

**Decision:** Discord is a first-class optional output, while local Android TTS
remains independent.

**Why:** Discord may provide a practical path toward PlayStation/PSVR2 audio.
It also needs internet, configuration and an external service. Its failure must
never stop the local engineer, telemetry or session recording.

## D-003 — Why no mandatory LapMind account?

**Decision:** Core telemetry, local voice and sessions must not require a
LapMind account or cloud service.

**Why:** Telemetry is useful locally. An account would add friction and privacy
cost before it added product value. Optional community contribution may come
later, but contribution is not the price of using the app.

## D-004 — Why is timed-race Final Lap disabled?

**Decision:** Do not announce timed-race Final Lap until the current race
duration and final-lap state can be established reliably.

**Why:** GT7 telemetry has not provided sufficient verified evidence for a
universal timed-race final-lap rule. A confident but false call is worse than
silence.

## D-005 — Why no opponent-gap, radar or tyre-wear claims?

**Decision:** Do not invent values that are absent from the verified GT7
telemetry path.

**Why:** The current evidence does not provide reliable opponent gaps or
coordinates, weather radar, exact track wetness, tyre wear/compound, penalties,
damage or the active fuel-map value. Shared UI examples from multi-game apps are
not GT7 evidence.

## D-006 — Why is Track Lab experimental?

**Decision:** Track Lab is clearly labelled `EXPERIMENTAL` in the beta.

**Why:** Showing maps and charts is technically achievable. Proving that the
workflow genuinely helps a phone user understand and practise a corner is a
separate product question. The beta must not pretend that question is settled.

## D-007 — Why not copy every competitor feature?

**Decision:** LapMind will not compete on feature count.

**Why:** Track maps, overlays, charts, leaderboards, cloud accounts, Discord and
coaching already exist in different products. LapMind should require less
attention while driving and less interpretation afterwards.

## D-008 — Why a separate public repository?

**Decision:** Public beta information, releases and feedback live here; the
application source remains private for now.

**Why:** Testers need a clear release surface, not access to internal evidence,
scratch material, private diagnostics, signing information or the development
repository.

## D-009 — Why only claim physically tested hardware?

**Decision:** Compatibility wording follows physical evidence, not protocol
similarity or expectation.

**Why:** PS4 telemetry has been tested directly. PS5 and PSVR2 are plausible and
important targets, but they become release claims only after their own physical
tests.

## D-010 — Why can Track Lab wait?

**Decision:** The controlled beta does not wait for a finished Track Lab.

**Why:** The voice engineer, optional Discord path and session memory already
form a useful Drive product. Real testers can validate that core while the Learn
product remains experimental.

## D-011 — Why isn't practice an incomplete race?

**Decision:** Activity type and session completion are separate concepts.

**Why:** A valid Time Trial or practice session can end without a race-finish
event. Treating every non-finished session as an incomplete race created false
meaning, including inappropriate race-position and P1 behaviour. LapMind now
prefers a conservative recognized practice state and leaves ambiguous activities
unknown rather than inventing certainty.
