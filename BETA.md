# LapMind beta boundary

## Current status

LapMind is currently at the **0.7.1 beta checkpoint**.

The Android application is still maintained in the private development repository. This public repository is the product-facing home for beta information, documentation, releases and feedback.

No public beta APK is being offered here yet. A release will happen only when the exact candidate and the intended real-world setup are ready.

## Stable beta core

The beta is intentionally focused:

- GT7 telemetry reception over the local network;
- spoken race-engineer callouts;
- named PlayStation profiles;
- local session history and review;
- explicit backup / export / import;
- optional Discord voice output;
- simple shutdown and recovery behaviour;
- experimental Track Lab as a clearly separated preview.

There is no LapMind account, PC companion or telemetry cloud backend required for the core workflow.

## Current product state

The current V4-era product includes:

- shared Drive / Sessions / Settings presentation;
- saved PlayStation cards with explicit Connect and Edit actions;
- simplified Sessions browsing and contextual selection mode;
- per-tab Sessions scroll restoration;
- Session details that open from the top while Back restores the previous list location;
- a lighter Session-details action hierarchy;
- optional Discord setup with local bot-token handling;
- current LapMind branding and root presentation.

Recent owner testing has physically accepted, within the tested scope:

- Sessions presentation and interaction;
- Settings presentation and navigation;
- Discord Companion presentation;
- Race Engineer & alerts UI;
- the Session package round trip **Analyse → Export → Delete → Import → Analyse**.

Physical testing and automated verification remain separate. A passing build is not treated as a substitute for a real user flow.

## Experimental Track Lab

Track Lab remains explicitly **experimental**.

It is a local telemetry workspace for reviewing owned driving evidence. Current development is moving toward a simpler hierarchy:

**Track overview → corner / section focus → point inspect**

The current work can import local telemetry evidence, identify track/lap context, render track views and support descriptive own-lap comparison.

The beta does not present Track Lab as:

- finished coaching;
- an approved stable feature;
- an optimal-racing-line engine;
- a source of unsupported tyre, opponent or weather facts;
- a universal classifier for lockup, wheelspin or oversteer.

Track Lab must never become a dependency for the stable local race-engineer core.

## Corner Lab — planned / researched

Corner Lab is a documented future direction, not a current beta feature.

It has enough research and owner direction to remain an active planning area, while the underlying research mechanism and evidence stay private.

This does **not** authorize production Corner Lab, automatic coaching, universal track knowledge or a public feature promise.

## Evidence discipline

LapMind deliberately keeps these separate:

- **source / implementation evidence** — the feature exists in current code;
- **automated verification** — tests/build checks passed;
- **physical validation** — the behaviour was observed on real hardware;
- **owner decision** — a product direction is binding even if implementation or validation is still pending.

The public product copy describes the supported product and current beta state. Internal release evidence remains stricter and more detailed than the marketing surface.

## Known non-claims

LapMind does not promise data GT7 telemetry does not reliably expose. Silence is preferred to a confident false call.

See [KNOWN_LIMITATIONS.md](KNOWN_LIMITATIONS.md) for the current tester-facing boundary.

## Publication hygiene

Before any public beta candidate is distributed, the exact accepted build still needs ordinary release hygiene:

1. freeze the accepted candidate;
2. run the required final release checks once;
3. verify signing/update continuity;
4. reconcile README / HOWTO / CHANGELOG / limitations against that exact APK;
5. publish the chosen beta package, checksum and release notes through the selected distribution path.

No internal build number or automated test count substitutes for the final candidate itself.
