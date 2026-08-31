# Known limitations

This document describes the current `0.7.1-beta2` controlled-beta candidate.
The APK is not yet publicly released.

## Experimental Track Lab

Track Lab is an experimental telemetry workspace, not finished coaching or an
optimal-racing-line engine. Its automatic analytic segments are descriptive
evidence units, not a stable named-corner database.

LapMind does not currently claim reliable classification of:

- lockup;
- wheelspin;
- oversteer or rear breakaway.

Tyre temperature can be inspected where available, but verified tyre wear,
pressure and compound are not claimed.

## Session and activity recognition

Practice recognition is deliberately conservative. Confidently recognized
practice is separated from race completion, but partial or unusual GT7
activities may remain `UNKNOWN`.

Automatic classification is not yet promised for Circuit Experience, License,
Drift, Rally or other specialised GT7 activities.

## Voice and race semantics

Timed-race Final Lap remains deliberately disabled where the current session's
final-lap state cannot be established reliably. Silence is preferred to a
confident false call.

The beta2 solo-practice P1 fix has automated and owned physical evidence. A
final genuine multi-car race position smoke is still required before public
release.

## Hardware and optional services

- PS4 telemetry is physically tested.
- PS5 and PSVR2 support is not yet physically validated or claimed.
- Android local TTS is implemented; physical beta coverage will continue.
- Discord voice is optional and still has incomplete physical beta validation.
  Discord failure must not disable local telemetry, voice or sessions.

## Release state

The remaining candidate gates are physical launcher-mask appearance, Settings /
Sessions navigation on representative Android displays, and the genuine
multi-car position smoke. See [BETA.md](BETA.md) for current gate status.
