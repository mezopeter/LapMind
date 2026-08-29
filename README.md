# LapMind

**Mind the Lap.**

LapMind is a local-first Android companion for Gran Turismo 7. It listens to
telemetry from a PlayStation on the local network, turns supported race events
into spoken engineer callouts, and keeps session summaries for later review.

LapMind is being prepared for its first controlled beta. **No public APK is
available yet.**

## Why I built LapMind

I started this project because I wanted to drive GT7 with the HUD off and still
hear the information that matters, especially in VR. I did not want to stop
mid-race, look at another screen, or run a PC beside the PlayStation.

What surprised me while building it was discovering that several other
developers had been working on very similar ideas at almost exactly the same
time. I genuinely did not expect that. LapMind is not an attempt to out-feature
those apps. It is the small, local-first companion I wanted for myself:
race-engineer callouts, optional Discord audio, session history, and a simple
way to inspect telemetry afterwards.

The Track Lab included in the planned beta is deliberately experimental. I do
not yet know where that part of LapMind will lead—and I would rather let real
use shape it than pretend it is finished.

## What the beta is about

The beta is intended to make the existing core simple and dependable:

- local race-engineer voice;
- optional Discord voice output;
- local session history;
- no mandatory LapMind account or cloud service;
- an explicitly experimental Track Lab.

It is **not** a race to add leaderboards, cloud accounts, generic AI coaching,
dozens of charts, or support for every simulator.

## The original workflow

```text
GT7 on PlayStation
        ↓ local-network telemetry
LapMind on Android
        ├── local engineer voice
        ├── local session history
        └── optional Discord voice → private voice channel
```

Local voice and session recording do not require Discord. Discord is an
optional output path for the original HUD-off/VR use case and requires an
internet connection, a Discord account, and a tester-owned bot in a private
server.

## Experimental Track Lab

Track Lab is an offline telemetry viewer under active design. The current
prototype can import a LapMind diagnostics package and display track/trace,
speed, brake and throttle data. It is not a finished analytics product, does
not provide coaching, and does not claim that an imported guide is an optimal
racing line.

The hard question is not whether LapMind can draw more telemetry. It is whether
it can help someone understand and practise one corner with less effort.

## Current hardware truth

- **PS4:** physically tested with GT7 telemetry.
- **PS5 / PSVR2:** planned for physical validation; not currently claimed.
- **Android core:** Android 8.0 or newer.
- **Optional Discord companion:** Android 10 or newer on arm64 hardware.

Compatibility claims will change only after matching physical evidence exists.
See [BETA.md](BETA.md) for the current release boundary.

## Principles

- HUD off. Eyes on track.
- Local-first; no mandatory account.
- The user's telemetry and sessions stay under the user's control.
- Measured first. Interpreted second.
- Silence is better than an unsupported claim.
- Discord is optional and must never break the local engineer.
- Track Lab is experimental until it proves that it helps.

The reasons behind these choices are recorded in [DECISIONS.md](DECISIONS.md),
and the personal development story is in [HISTORY.md](HISTORY.md).

## Feedback

When the controlled beta opens, bugs and focused feedback will be collected
through GitHub Issues. A GitHub account may be needed to submit an issue, but
no account is required to use LapMind itself.

Please do not post Discord tokens, PlayStation IP addresses, private session
exports, or diagnostics ZIPs in a public issue. Read [CONTRIBUTING.md](CONTRIBUTING.md)
and [PRIVACY.md](PRIVACY.md) first.

## Project status and source

This repository is the public home for beta information, release artefacts and
feedback. The application source is currently maintained privately. No source
code licence or open-source release is implied by this repository.

LapMind is an independent, unofficial project. It is not affiliated with,
endorsed by, or sponsored by Sony Interactive Entertainment, Polyphony Digital,
Discord, or the Gran Turismo brand. Gran Turismo, GT7, PlayStation, PS4, PS5 and
PSVR2 are trademarks of their respective owners.
