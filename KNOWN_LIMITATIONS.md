# Known limitations

This document describes the current LapMind `0.7.1` beta checkpoint.

The public APK is not yet published from this repository. The final physical green-light gate is the PS5 / PSVR2 end-to-end Discord listening path described in [BETA.md](BETA.md).

## Hardware boundary

- **PS4 telemetry:** physically tested.
- **PS5 / PSVR2:** not yet claimed as physically validated for the final intended Discord headset path.
- **Android local core:** implemented; Android 8.0+ baseline.
- **Optional Discord Companion:** implemented; Android 10+ arm64 path, with incomplete final physical coverage.

A successful build or automated test is not treated as PS5 / PSVR2 physical evidence.

## Local voice and race semantics

LapMind intentionally avoids unsupported callouts.

Timed-race Final Lap remains disabled where the current session cannot establish a trustworthy final-lap state from GT7 telemetry.

Physical evidence for local voice reliability has had route/interruption-dependent gaps during development. Public claims therefore remain conservative until the exact final beta candidate has matching physical coverage.

## Session and activity recognition

Practice recognition is deliberately conservative.

- confidently recognized practice is separated from ordinary race completion;
- practice does not intentionally produce a false P1 result;
- partial or unusual GT7 activities may remain `UNKNOWN`.

Automatic classification is not promised for every specialized GT7 activity such as Circuit Experience, License, Drift or Rally events.

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

Track Lab is an experimental local telemetry workspace, not finished coaching or an optimal-racing-line engine.

Its current descriptive analysis does not establish reliable general-purpose classification of:

- lockup;
- wheelspin;
- oversteer / rear breakaway.

It does not claim verified tyre wear, pressure or compound information.

## Discord

Discord is optional.

LapMind requires a dedicated tester-owned bot token for the private voice path. It does not require the user's Discord password or normal-user token.

Discord failure must not disable local telemetry, local voice or local Sessions.

The exact **Discord → PS5 / PSVR2 headset** path remains the final physical beta gate and must not be described as validated before that real test succeeds.

## Sessions and storage

Sessions are local by default. Backup, restore, import and export are explicit user actions.

Users should keep backups once session history becomes valuable. Beta software can still expose migration or edge-case defects that automated tests did not catch.

## Public support boundary

Do not post Discord bot tokens, PlayStation IP addresses, private session exports or diagnostics ZIPs in public issues.

See [HOWTO.md](HOWTO.md) for setup, [PRIVACY.md](PRIVACY.md) for privacy, and [BETA.md](BETA.md) for the release boundary.
