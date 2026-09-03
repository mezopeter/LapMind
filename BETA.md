# LapMind beta boundary

## Current status

The current V4 / post-beta11 product state is the **LapMind `0.7.1` beta checkpoint**.

This is the product state intended for the first public beta. The Android source remains in the private development repository; no public APK has been published from this repository yet.

## Final green-light gate

The final publication green light is one successful physical end-to-end test of the intended VR audio path:

```text
PS5 · GT7 telemetry
        ↓ local network
LapMind on Android
        ↓ optional Discord bot voice
PS5 / PSVR2 headset
```

The test must prove the real user path, not merely a build, emulator or automated test.

Until it passes:

- PS5 / PSVR2 Discord audio is **not** claimed as physically validated;
- the public beta APK remains unpublished here.

PS4 GT7 telemetry is already physically tested and remains the strongest current console evidence.

## Stable beta core

The beta is intentionally small:

- GT7 telemetry reception over the local network;
- local race-engineer callouts;
- named PlayStation profiles;
- local session history and review;
- explicit backup / restore / export / import;
- optional Discord voice output;
- simple shutdown and recovery behaviour;
- experimental Track Lab as a clearly separated preview.

LapMind does not require a LapMind account, PC companion or telemetry cloud backend for the core workflow.

## Current V4 product state

The beta checkpoint includes:

- shared Drive / Sessions / Settings root presentation;
- saved PlayStation cards with explicit Connect and Edit actions;
- shared bounded-action visual foundation;
- simplified Sessions overflow and contextual selection mode;
- per-tab Sessions scroll restoration;
- Session details that open from the top while Back restores the prior list location;
- a lighter Session-details action hierarchy;
- optional Discord setup with local bot-token handling;
- the transparent LapMind root-header mark.

The final Session-details bottom presentation has been physically reviewed and accepted by the owner. Broader V4 physical approval is not implied by that statement.

## Experimental Track Lab

Track Lab remains explicitly experimental.

It can inspect richer local telemetry and compare owned laps with distance-aligned descriptive analysis, but the beta does not claim:

- finished coaching;
- an optimal racing line;
- reliable lockup / wheelspin / oversteer classification;
- verified tyre wear, pressure or compound telemetry;
- opponent-gap or weather-radar information unsupported by GT7 telemetry;
- a community reference database.

Track Lab must not become a dependency for the stable local race-engineer core.

## Evidence discipline

LapMind keeps these separate:

- **source/implementation evidence** — the feature exists in current code;
- **automated verification** — tests/build checks passed;
- **physical validation** — the behaviour was observed on real hardware;
- **owner decision** — a product direction is binding, even when future implementation or physical validation is still pending.

Automated tests never substitute for a physical PS5 / PSVR2 headset test.

## Current hardware boundary

| Path | Status |
|---|---|
| PS4 → GT7 telemetry → Android core | Physically tested |
| Android local core | Implemented |
| Optional Discord Companion | Implemented; physical coverage incomplete |
| PS5 → GT7 telemetry → LapMind | Awaiting final physical beta gate |
| Discord → PS5 / PSVR2 headset | Awaiting final physical beta gate |

## Known non-claims

The beta deliberately does not promise data GT7 telemetry does not reliably expose. Silence is preferred to a confident false call.

See [KNOWN_LIMITATIONS.md](KNOWN_LIMITATIONS.md) for the current tester-facing boundary.

## Publication step after the green light

After the PS5 / PSVR2 Discord path passes physically, the exact beta APK still needs ordinary publication hygiene:

1. freeze the accepted candidate;
2. run the final release gate once;
3. verify signing/update continuity;
4. reconcile README / HOWTO / CHANGELOG / limitations against the exact APK;
5. publish the APK/checksum/release notes as a GitHub pre-release or through the chosen beta distribution path.

No earlier internal build number or automated test result should be treated as a substitute for this final candidate step.
