# Known limitations

This document describes the current LapMind `0.7.1` beta checkpoint.

The goal here is simple: document what LapMind should stay quiet about, where the current beta is deliberately conservative, and which development areas are still experimental.

## Local voice and race semantics

LapMind intentionally avoids unsupported callouts.

Timed-race Final Lap remains disabled where the current session cannot establish a trustworthy final-lap state from GT7 telemetry.

Android audio focus and interruptions can affect local speech playback. The app contains stale-call protection and finish barriers, but external audio events can still change what the phone is able to play at a given moment.

## Session and activity recognition

Practice recognition is deliberately conservative.

- confidently recognized practice is separated from ordinary race completion;
- practice does not intentionally produce a false P1 result;
- partial or unusual GT7 activities may remain `UNKNOWN`.

Automatic classification is not promised for every specialized GT7 activity such as License, Drift or Rally events.

## GT7 telemetry non-claims

LapMind does not invent fields GT7 does not reliably provide.

The current beta does not claim dependable live access to:

- weather radar;
- track wetness as a trustworthy live field;
- opponent coordinates or gaps;
- tyre wear;
- tyre pressure;
- tyre compound;
- penalties;
- damage state;
- active fuel-map value.

Where LapMind derives descriptive observations from motion/telemetry, they remain conservative interpretations rather than direct GT7 facts.

## Experimental Track Lab

Track Lab is **experimental**.

It is a local telemetry review workspace under active development, not a finished coaching product or an optimal-racing-line engine.

Its current descriptive analysis does not establish reliable general-purpose classification of:

- lockup;
- wheelspin;
- oversteer / rear breakaway.

It does not claim verified tyre wear, pressure or compound information.

The current product direction is moving toward a simpler hierarchy:

**Track overview → corner / section focus → point inspect**

That direction is still experimental and should not be read as an approved final feature contract.

## Corner Lab

Corner Lab is **planned / researched**, not a current beta feature.

The underlying research mechanism and evidence remain private. Publicly, the only claim is that the direction has enough research and owner support to continue planning.

It does not imply production coaching, universal track knowledge or a finished Corner Lab implementation.

## Discord

Discord is optional.

LapMind requires a dedicated tester-owned bot token for the private voice path. It does not require the user's Discord password or normal-user token.

Discord failure must not disable local telemetry, local voice or local Sessions.

Discord naturally depends on internet access and the Discord service while enabled.

## Sessions and storage

Sessions are local by default. Backup, import and export are explicit user actions.

The current Session package round trip **Analyse → Export → Delete → Import → Analyse** has passed owner physical testing.

Users should still keep backups once session history becomes valuable. Beta software can expose migration or edge-case defects that automated tests do not catch.

## Public support boundary

Do not post Discord bot tokens, PlayStation IP addresses, private session exports or diagnostics ZIPs in public issues.

See [HOWTO.md](HOWTO.md) for setup, [PRIVACY.md](PRIVACY.md) for privacy, and [BETA.md](BETA.md) for the current beta boundary.
