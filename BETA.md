# Controlled beta boundary

## Current status

LapMind is being prepared for its first controlled beta. There is no public APK
in this repository yet.

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

Track Lab is an experimental preview. Its current purpose is to let testers
inspect trace, speed, brake and throttle data and help shape the workflow.

The beta does not claim:

- finished analytics;
- an optimal racing line;
- automated coaching;
- reliable downloaded/ranking replay support;
- a community reference database;
- Track Tour or Practice Plan functionality.

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

Before the first APK is published here:

1. the core stabilization build must pass its automated and physical checks;
2. update signing and version identity must be stable and safely backed up;
3. Discord must be tested without weakening the local fallback;
4. PS5/PSVR2 wording must match the physical result, including an honest
   `not yet validated` result if necessary;
5. quick-start, privacy, compatibility, known-limitations and third-party
   notices must match the exact APK;
6. the APK checksum and release notes must be published with a GitHub
   **Pre-release** marker.

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
