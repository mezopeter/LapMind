# LapMind

**Local-first race engineer for Gran Turismo 7 on Android.**

LapMind listens to GT7 telemetry from a PlayStation on your local network, turns supported race events into spoken engineer callouts, and keeps session history for review. Local telemetry, local voice and sessions do not require a LapMind account, cloud service or PC.

## Beta status

**The current V4 / post-beta11 product state is the LapMind `0.7.1` beta checkpoint.**

The core beta is now shaped around the product that will be tested publicly: local race-engineer voice, saved PlayStation profiles, local Sessions, optional Discord voice output and the experimental Track Lab.

The public APK is not being published from this repository yet. The final green light is one successful physical end-to-end test of the intended VR path:

```text
PS5 · GT7 telemetry
        ↓ local network
LapMind on Android
        ↓ optional Discord bot voice
PS5 / PSVR2 headset
```

Until that test passes, **PS5 / PSVR2 Discord audio is not claimed as physically validated**. PS4 GT7 telemetry is already physically tested.

See [BETA.md](BETA.md) for the exact boundary.

## Why LapMind exists

LapMind started with a simple problem: driving GT7 with little or no HUD is more immersive, especially in VR, but some race information still matters. Looking at a phone is not the answer. The useful information has to arrive quietly, at the right moment, in the driver's ear.

The project deliberately avoids a feature-count race. Its priorities are:

- useful race-engineer callouts rather than constant speech;
- local-first operation;
- saved sessions that remain under the user's control;
- optional Discord output that never becomes a dependency for the local core;
- conservative interpretation when GT7 telemetry does not support a confident claim.

**Silence is better than stale or invented truth.**

## Current beta experience

### Drive

- named PlayStation profiles with explicit Connect and Edit actions;
- local telemetry receiver and engineer state;
- local Android TTS;
- optional Discord voice output;
- configurable callout behaviour and units;
- clear full-shutdown action when you are finished.

### Sessions

- local session history;
- Browse, Interrupted and Rejected workflows;
- multi-selection with direct contextual actions;
- session details and timeline review;
- export, backup, restore and import;
- scroll position preserved when returning from a session detail.

### Experimental Track Lab

Track Lab is an offline telemetry workspace under active development. It can inspect richer local telemetry and compare owned laps using evidence-oriented, distance-aligned analysis.

It is **not** presented as finished coaching, an optimal-racing-line engine or a source of unsupported tyre/opponent/weather facts.

## Quick start

1. Install a trusted LapMind beta APK.
2. Put the Android device and PlayStation on the same non-isolated LAN/Wi-Fi.
3. Find the PlayStation IPv4 address and save it as a named PlayStation profile in LapMind.
4. Start GT7 and use the profile's **Wi-Fi / Connect** action.
5. Enter a race or practice session and drive normally.
6. Review the result under **Sessions**.
7. Use **Fully close LapMind** when you want the receiver, Discord and LapMind background activity stopped.

For setup details, troubleshooting and Discord bot setup, read [HOWTO.md](HOWTO.md).

## Optional Discord Companion

Discord is an optional output path for the original HUD-off / VR goal. LapMind uses a tester-owned bot in a private Discord server; it does not ask for your Discord password or normal-user token.

The local engineer remains independent. A Discord outage, reconnect or bot problem must not stop local telemetry, local TTS or session recording.

The current final physical beta gate is the PS5 / PSVR2 end-to-end Discord listening path described above.

## Hardware boundary

| Path | Current public claim |
|---|---|
| PS4 → GT7 telemetry → LapMind | Physically tested |
| Android local core | Implemented; Android 8.0+ baseline |
| Optional Discord Companion | Implemented; Android 10+ arm64 path |
| PS5 → GT7 telemetry → LapMind | Awaiting final physical beta gate |
| Discord → PS5 / PSVR2 headset | Awaiting final physical beta gate |

Compatibility claims change only when matching physical evidence exists.

## Local-first privacy

LapMind does not require a LapMind account or telemetry backend. Sessions stay local unless you explicitly export or back them up. Discord is optional and necessarily uses the internet when enabled.

Never post these in a public GitHub issue:

- Discord bot tokens;
- PlayStation IP addresses;
- private session exports;
- diagnostics ZIPs containing your own telemetry.

See [PRIVACY.md](PRIVACY.md) and [CONTRIBUTING.md](CONTRIBUTING.md).

## Documentation

- [HOWTO.md](HOWTO.md) — first setup, PlayStation connection and Discord setup
- [CHANGELOG.md](CHANGELOG.md) — public beta changes
- [BETA.md](BETA.md) — current beta boundary and final green-light gate
- [KNOWN_LIMITATIONS.md](KNOWN_LIMITATIONS.md) — current limitations and non-claims
- [DECISIONS.md](DECISIONS.md) — product principles and decisions
- [HISTORY.md](HISTORY.md) — development story
- [PRIVACY.md](PRIVACY.md) — privacy boundary

## Website and support

- **Website:** https://lap-mind.com
- **Support:** support@lap-mind.com

## Repository role

This repository is LapMind's **public product home** for beta information, documentation, changelog, release artefacts and feedback.

The Android application source is maintained in a separate private development repository. No source-code licence or open-source release is implied by this public repository.

LapMind is an independent, unofficial project. It is not affiliated with, endorsed by or sponsored by Sony Interactive Entertainment, Polyphony Digital, Discord or the Gran Turismo brand. Gran Turismo, GT7, PlayStation, PS4, PS5 and PSVR2 are trademarks of their respective owners.
