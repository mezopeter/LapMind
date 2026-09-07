# Important product decisions

This is not a roadmap or changelog. It records why LapMind deliberately does
some things—and deliberately does not do others.

## D-001 — Why voice first?

**Decision:** Race-critical information should be available without looking at
the phone.

**Why:** LapMind began with a very specific HUD-off VR problem: driving the
**1965 Honda RA272 at Le Mans** in GT7 and wanting nothing between the driver and
the car except the cockpit, track and engine. The HUD could disappear, but fuel,
lap, position and race-state information still mattered. A telemetry dashboard
would simply replace one thing to look at with another.

## D-002 — Why optional Discord?

**Decision:** Discord is a first-class optional output, while local Android TTS
remains independent.

**Why:** The original setup was **PS5 + PSVR2 + Sony INZONE Buds**. In that setup,
the headset cannot simultaneously provide PS5 2.4 GHz audio and Android
Bluetooth audio, so Discord became the practical route for putting the engineer
into the same headset as GT7 without adding a PC.

That does not make Discord a dependency for LapMind itself. It needs internet,
configuration and an external service, and its failure must never stop local
telemetry, local voice or session recording.

## D-003 — Why is there no LapMind account?

**Decision:** LapMind has no product account system for the current core.

**Why:** Telemetry, local voice and sessions are useful locally. A username,
email sign-up, telemetry backend or cloud account would add friction and privacy
cost without solving the core problem. If a future feature ever genuinely needs
an account, that would require a separate product decision.

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

**Why:** Showing maps, traces and charts is technically achievable. Proving that
the workflow genuinely helps someone understand their own driving is a separate
product question. The current direction—**Track overview → corner / section
focus → point inspect**—is being developed and tested without pretending the
product question is already settled.

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

## D-009 — Why separate internal evidence from public product copy?

**Decision:** Internal release evidence can be stricter and more detailed than
public-facing product wording.

**Why:** Physical validation matters for deciding whether something is ready to
ship. It does not mean every product page should read like a QA ledger. If a
supported setup is not ready, LapMind should not be released for that setup. If
it is released, the public copy should explain what the product does clearly
rather than foregrounding internal gate terminology.

## D-010 — Why doesn't the beta wait for a finished Track Lab?

**Decision:** The controlled beta does not wait for a finished Track Lab.

**Why:** The voice engineer, optional Discord path and local session memory form
a useful Drive product on their own. Track Lab can remain experimental while it
earns its place through evidence and real use.

## D-011 — Why isn't practice an incomplete race?

**Decision:** Activity type and session completion are separate concepts.

**Why:** A valid Time Trial or practice session can end without a race-finish
event. Treating every non-finished session as an incomplete race created false
meaning, including inappropriate race-position and P1 behaviour. LapMind now
prefers a conservative recognized practice state and leaves ambiguous activities
unknown rather than inventing certainty.

## D-012 — Why is Corner Lab only planned / researched?

**Decision:** Corner Lab may be discussed publicly as a researched future
direction, but not as a current or promised feature.

**Why:** There is enough private research and owner direction to justify keeping
the direction alive. The mechanism, evidence and implementation path remain
private until there is a reason to publish them. Research does not automatically
become product scope.
