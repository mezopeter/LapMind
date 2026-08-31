# Controlled beta boundary

## Current status

`0.7.1-beta2` is the current controlled-beta candidate. Its engineering build
exists internally, but no APK has been published from this repository and no
GitHub Pre-release has been created. Publication waits for the remaining
physical release checks.

## Stable-core target

The beta is intended to validate a small product:

- receiving GT7 telemetry over the local network;
- local race-engineer callouts;
- optional Discord voice output;
- local session history and portable session backup;
- simple setup, shutdown and recovery behaviour.

“Stable core” describes the target for the beta, not a promise that every edge
case is already solved. Beta feedback exists to find those cases.

## Explicitly experimental

Track Lab is an experimental preview. It now supports richer offline telemetry
inspection, distance-aligned owned-lap comparison, automatically derived
analytic driving segments and descriptive telemetry signals.

The beta does not claim:

- finished analytics;
- an optimal racing line;
- automated coaching;
- reliable downloaded/ranking replay support;
- a community reference database;
- Track Tour or Practice Plan functionality.
- reliable lockup, wheelspin, oversteer or rear-breakaway classification;
- verified tyre wear, pressure or compound information.

Track Lab must not delay release of an otherwise ready core.

## Out of scope for the first beta

- mandatory cloud accounts or telemetry upload;
- leaderboards and social profiles;
- generic AI coaching;
- support for every racing simulator;
- opponent-gap or weather-radar features unsupported by GT7 evidence;
- a large visual redesign or decorative animation programme.

## Hardware claims

| Path | Status |
|---|---|
| PS4 → GT7 telemetry → Android core | Physically tested |
| Android local TTS | Implemented; beta physical coverage will continue |
| Android → private Discord voice channel | Experimental and undergoing physical validation |
| PS5 telemetry | Not yet claimed |
| Discord → PS5/PSVR2 headset/mixing | Not yet claimed |

## Release gates

Current candidate status:

- **Satisfied:** debug and release JVM verification; private owned-lap replay
  coverage; candidate version identity; release-note/checksum draft; public
  privacy and limitation wording.
- **Pending:** actual Android launcher-mask appearance.
- **Pending:** Settings and Sessions navigation smoke on physical Android,
  including more than one relevant display size where practical.
- **Pending:** a genuine multi-car race position smoke confirming valid
  position and P1 callouts still work.
- **Pending / not claimed:** PS5/PSVR2 physical validation and complete Discord
  beta validation.
- **At publication:** verify signing/update continuity, re-check every public
  document against the exact APK, then publish the checksum and notes with a
  GitHub **Pre-release** marker.

See [KNOWN_LIMITATIONS.md](KNOWN_LIMITATIONS.md) for the current tester-facing
boundary and [RELEASE_NOTES_0.7.1-beta2.md](RELEASE_NOTES_0.7.1-beta2.md) for
the prepared, not-yet-published candidate notes.

## What changed in `0.7.1-beta2`

- Confidently recognized solo Time Trial/practice sessions no longer masquerade
  as ordinary incomplete races.
- Practice sessions do not show or announce a false P1 result.
- Activity type and completion/termination semantics are separated more clearly;
  ambiguous activities remain unknown.
- Settings uses a cleaner hierarchy, Sessions is browse-first, and
  Backup/Restore is secondary.
- `Delete All Incomplete` was removed.
- The launcher icon was updated.
- Experimental Track Lab gained richer telemetry analysis and descriptive,
  distance-aligned owned-lap comparison.

## Feedback requested

The beta will primarily ask:

- Did setup work without unnecessary friction?
- Were callouts timely, useful and trustworthy?
- Did local voice continue when Discord was unavailable?
- Were sessions saved and understandable?
- Did the app recover cleanly from Pause, Exit, backgrounding and connection
  interruption?
- Did Track Lab help you inspect anything, and where did it become confusing?

Feature-count requests are welcome as context, but stability and workflow
evidence take priority during the first beta.
