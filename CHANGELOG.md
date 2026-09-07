# LapMind changelog

This is the public product changelog. It summarizes user-visible beta changes without exposing the private development repository or internal diagnostics history.

## 0.7.1 beta — current product checkpoint — 2026-09-07

The current beta presentation and product boundary have moved beyond the earlier beta11-era public snapshot.

### Current physically reviewed areas

Recent owner testing has physically accepted, within the tested scope:

- Sessions presentation and interaction;
- Settings presentation and navigation;
- Discord Companion presentation;
- Race Engineer & alerts UI;
- the full Session package round trip:
  **Analyse → Export → Delete → Import → Analyse**.

Physical testing remains distinct from automated checks.

### Sessions and portability

- Session browsing, detail presentation and navigation restoration have been refined.
- Export / import remains explicit and local-first.
- The real export-delete-import round trip now has owner physical confirmation.
- Imported session data remains distinguishable from locally recorded data rather than silently changing provenance.

### Race Engineer and Settings

- The current Race Engineer & alerts presentation is physically accepted in its tested phone/tablet scope.
- Voice & sound, Race callouts, Timed-race announcements, Lap-time comparison and Haptics are presented as one calm settings category with focused sections.
- Settings navigation and adaptive presentation have also passed owner physical review within the tested scope.

### Discord Companion

- Discord remains optional and isolated from the local core.
- The embedded Settings flow and current presentation have passed owner physical review.
- LapMind continues to use a dedicated private bot-token path rather than asking for a normal Discord-user token or password.
- Discord is especially useful for headset setups that cannot directly mix PlayStation and Android audio. The original LapMind setup is PS5 + PSVR2 + Sony INZONE Buds.

### Experimental Track Lab

- Track Lab remains explicitly **experimental**.
- The beta UI direction has been reworked around a calmer hierarchy:
  **Track overview → corner / section focus → point inspect**.
- Empty-state, loaded-state hierarchy, map/inspection structure and evidence-oriented review have received a focused product pass.
- Track Lab is still not presented as an approved finished feature, coaching system or optimal-racing-line engine.

### Corner Lab research

- Corner Lab remains **planned / researched**, not a current beta feature.
- Owned Circuit Experience research has established a repeatable full-rate structural method across two captures.
- A reusable offline prototype has reproduced the bounded repeated-section → longer-lap mapping result.
- This supports continued research only; production Corner Lab and coaching are not implied.

---

## 0.7.1 beta — V4 checkpoint — 2026-09-03

This checkpoint established the first V4-era public product shape.

### Drive and PlayStation setup

- Refined the three-root-screen UI: **Drive / Sessions / Settings**.
- Added the shared LapMind root-header mark.
- Reworked saved PlayStation profiles with dedicated profile artwork and clearer actions:
  - profile icon → Edit;
  - Wi-Fi → Connect that PlayStation;
  - pencil → Edit.
- Long PlayStation profile names support two lines with safe end ellipsis.
- Fixed a root-navigation state bug that could leave `Edit PlayStation` in the header after returning to a root tab.
- Added a clearer full-shutdown action: **Fully close LapMind**.

### Sessions

- Simplified the normal Sessions toolbar to one right-side vertical `⋮` overflow.
- Moved multi-session selection into a cleaner contextual mode with selected count, Cancel and direct relevant actions.
- Removed the old per-card `Select / Selected` text row.
- Added compact circle/check selection state without changing card height.
- Stabilized card text position so entering selection mode does not shift the title/metadata block.
- Preserved semantic card backgrounds while adding a subtle selected-state accent.
- Added separate in-memory scroll positions for Browse / Interrupted / Rejected.
- Returning from Session details restores the previous list position.
- Every newly opened Session details page starts at the top rather than inheriting the previous detail scroll position.
- Refined Session details actions into a clear hierarchy:
  - primary **EDIT DETAILS**;
  - lightweight **Export this session**;
  - lightweight destructive **Reject session**.

### Shared UI foundation

- Standardized normal bounded actions around one shared visual system:
  - 42 dp visible action surface;
  - minimum 48 dp interaction target;
  - shared label typography;
  - semantic primary / secondary / destructive treatment.
- Applied the same foundation across the main app, Diagnostics, Track Lab and Discord surfaces where appropriate.

### PlayStation connection stability

- Fixed a foreground-service startup race that could crash all PlayStation connect entry paths in an earlier beta candidate.
- Corrected single-profile connection paths were physically checked with real GT7 telemetry.
- Two-profile fallback remained automated-only at this checkpoint.

### Discord Companion

- Discord remained optional and isolated from the local core.
- The app could use a tester-owned bot token stored locally to join a selected private server/voice channel.
- Server/channel IDs were resolved internally instead of requiring manual ID entry.
- Discord failure remained independent from local telemetry, local TTS and Sessions.

### Local-first sessions and portability

- Sessions remained local by default.
- Backup, restore, export and import remained explicit user actions.
- Discord credentials and PlayStation connection details were excluded from session export/backup data.

### Experimental Track Lab

- Track Lab remained an explicitly experimental local telemetry workspace.
- It could inspect richer local telemetry and compare owned laps with distance-aligned descriptive analysis.
- It was not presented as finished coaching, an optimal racing line or a source of unsupported GT7 telemetry facts.

---

## Earlier 0.7.1 beta preparation

### Session/activity truth

- Separated session activity type from completion/termination state.
- Confident solo practice no longer masquerades as an ordinary failed race.
- Practice does not produce a false P1 result.
- Ambiguous activities remain unknown rather than being forced into a confident label.

### Voice and race lifecycle

- Added lifecycle-aware callout prioritization and stale-call protection.
- Strengthened finish barriers, interruption handling and conservative track identity.
- Timed-race final-lap speech remains disabled when the available telemetry cannot support a trustworthy final-lap claim.

### Diagnostics

- Added explicit diagnostics workflows for physical validation and richer full-rate local telemetry capture.
- Diagnostics remain opt-in and local unless the user explicitly exports them.

### Discord integration

- Integrated the optional Discord Companion into the same Android application package.
- Added private bot-token handling, selected server/channel flow and optional reconnect behavior.
- Kept Discord isolated so it cannot become a failure dependency for the local race engineer.

---

For the current release boundary see [BETA.md](BETA.md). For setup see [HOWTO.md](HOWTO.md). For non-claims and known limits see [KNOWN_LIMITATIONS.md](KNOWN_LIMITATIONS.md).
