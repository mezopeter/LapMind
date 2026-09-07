# LapMind

**Turn off the HUD. Keep what matters.**

LapMind is a local-first race engineer for Gran Turismo 7 on Android. It listens to GT7 telemetry from a PlayStation on your local network, turns supported race events into spoken engineer callouts, and keeps local session history for review.

There is no LapMind account. No username, no email sign-up and no telemetry cloud are required for the core experience.

## Why LapMind exists

LapMind started with one very specific drive.

I wanted to take the **1965 Honda RA272 around Le Mans in VR** and have nothing between me and the car: the cockpit, the track, the engine, me. No floating fuel gauge, no lap counter, no bright interface sitting over a sixty-year-old racing car.

GT7 can give you that feeling beautifully with the HUD out of the way. The problem is that some information still matters: fuel, laps, position, pit timing and the end of the race.

I did not want the HUD back. I wanted someone to tell me the important bits.

That became LapMind.

My own setup is **PS5 + PSVR2 + Sony INZONE Buds**. The Buds cannot simultaneously give me PS5 2.4 GHz audio and Android Bluetooth audio, so for that setup Discord is the practical route that puts LapMind's engineer into the same headset as GT7.

Discord is still optional for LapMind itself. Local Android voice remains part of the core product.

## Current beta status

LapMind is currently at the **0.7.1 beta checkpoint**. The Android source is maintained privately while the public repository remains the product home for beta information, documentation, releases and feedback.

No public beta APK is being offered here yet. When a candidate is ready, it will be released only after the real intended setup and the exact candidate have passed the required checks.

The current beta core is built around:

- local GT7 telemetry over the local network;
- spoken race-engineer callouts;
- named PlayStation profiles;
- local Sessions and review;
- explicit session export, import and backup;
- optional Discord voice output;
- clear shutdown and recovery behaviour;
- experimental Track Lab, kept separate from the stable core.

## What has been physically checked

Physical testing is kept separate from automated tests.

Recent owner testing has accepted the current Sessions, Settings, Discord Companion presentation, and Race Engineer & alerts UI on real hardware within their tested scope. The Session package round trip has also passed the real flow:

**Analyse → Export → Delete → Import → Analyse**

That matters because session portability is not meant to be a decorative export button. The local data should remain genuinely under the user's control.

## Drive

The normal driving workflow is deliberately simple:

1. Save your PlayStation as a named profile.
2. Put the Android device and PlayStation on the same local network.
3. Start GT7 and connect LapMind.
4. Drive.
5. Hear only the supported information you chose.
6. Review the session later if you want to.

Looking at the phone while driving is not the point.

## Sessions

Sessions stay local by default and can be reviewed later. Current workflows include:

- Browse, Interrupted and Rejected session areas;
- session details and timeline review;
- favourite/star handling;
- multi-selection and contextual actions;
- explicit export, import and backup;
- restoration of list position when returning from session details.

Imported data retains its provenance rather than silently pretending it was recorded on the receiving device.

## Experimental Track Lab

Track Lab is an **experimental** local telemetry workspace.

It is being developed around a calmer model:

**Track overview → corner / section focus → point inspect**

The goal is evidence-oriented review of your own driving, not a miniature telemetry dashboard. Current work includes local diagnostics import, track matching, lap selection, map views and descriptive own-lap comparison.

Track Lab is **not an approved finished feature**, not an optimal-racing-line engine, and not finished coaching.

## Corner Lab — planned / researched

Corner Lab is a more mature future direction, but still a plan rather than a current product feature.

Research using owned Circuit Experience captures has shown that repeated short sections can be identified and mapped back onto a longer lap at full telemetry rate. A reusable offline structural prototype has reproduced that result across two owned captures.

That is enough to justify continued research. It is not authorization to claim production Corner Lab, automatic coaching or universal track knowledge.

## Optional Discord Companion

Discord provides an optional external voice route. It is especially useful when the headset or audio setup cannot mix Android audio directly with PlayStation audio.

The intended flow is:

```text
GT7 telemetry → LapMind on Android → private Discord bot voice → PlayStation headset
```

LapMind uses a tester-owned bot in a private Discord server. It does not ask for your Discord password or normal-user token. A Discord problem must not stop local telemetry, local TTS or session recording.

See [HOWTO.md](HOWTO.md) for setup.

## Local-first privacy

LapMind has no LapMind account and no telemetry backend for the core product. Sessions stay on the Android device unless you explicitly export or back them up. Diagnostics are also explicit user actions.

Discord is optional and necessarily uses the internet when enabled.

Never post these publicly:

- Discord bot tokens;
- PlayStation IP addresses;
- private session exports;
- diagnostics ZIPs containing your telemetry.

See [PRIVACY.md](PRIVACY.md) for the current privacy boundary.

## Documentation

- [HOWTO.md](HOWTO.md) — first setup, PlayStation connection and Discord setup
- [BETA.md](BETA.md) — current beta boundary
- [CHANGELOG.md](CHANGELOG.md) — public beta changes
- [KNOWN_LIMITATIONS.md](KNOWN_LIMITATIONS.md) — current limitations and non-claims
- [DECISIONS.md](DECISIONS.md) — product principles and decisions
- [HISTORY.md](HISTORY.md) — how the project got here
- [PRIVACY.md](PRIVACY.md) — privacy boundary

## Website and support

- **Website:** https://lap-mind.com
- **Support:** support@lap-mind.com

## Repository role

This repository is LapMind's **public product home** for beta information, documentation, changelog, release artefacts and feedback.

The Android application source is maintained in a separate private development repository. No source-code licence or open-source release is implied by this public repository.

LapMind is an independent, unofficial project. It is not affiliated with, endorsed by or sponsored by Sony Interactive Entertainment, Polyphony Digital, Discord or the Gran Turismo brand. Gran Turismo, GT7, PlayStation, PS4, PS5 and PSVR2 are trademarks of their respective owners.
