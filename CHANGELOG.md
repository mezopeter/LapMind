# LapMind changelog

This is the public product changelog. It summarizes user-visible beta changes without exposing the private development repository or internal diagnostics history.

## 0.7.1 beta — current checkpoint — 2026-09-03

This is the product state intended for the first LapMind beta.

### Drive and PlayStation setup

- Refined the three-root-screen UI: **Drive / Sessions / Settings**.
- Added the shared LapMind root-header mark.
- Reworked saved PlayStation profiles with dedicated profile artwork and clearer actions:
  - profile icon → Edit;
  - Wi-Fi → Connect that PlayStation;
  - pencil → Edit.
- Long PlayStation profile names now support two lines with safe end ellipsis.
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
- Returning from Session details now restores the previous list position.
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
- The corrected single-profile connection paths were physically verified with real PS4 telemetry.
- Two-profile fallback remains automated-only and is not presented as physically validated.

### Discord Companion

- Discord remains optional and isolated from the local core.
- The app can use a tester-owned bot token stored locally to join a selected private server/voice channel.
- Server/channel IDs are resolved internally instead of requiring manual ID entry.
- Discord failure does not become a dependency for local telemetry, local TTS or Sessions.
- The final public-beta green light is a successful physical end-to-end **PS5 + PSVR2 + Discord** test.

### Local-first sessions and portability

- Sessions remain local by default.
- Backup, restore, export and import remain explicit user actions.
- Discord credentials and PlayStation connection details are not part of session export/backup data.

### Experimental Track Lab

- Track Lab remains an explicitly experimental local telemetry workspace.
- It can inspect richer local telemetry and compare owned laps with distance-aligned descriptive analysis.
- It is not presented as finished coaching, an optimal racing line or a source of unsupported GT7 telemetry facts.

### Current physical boundary

- PS4 GT7 telemetry: physically tested.
- Current V4 Session-details bottom presentation: physically owner-reviewed and accepted.
- Broader V4 physical review continues conservatively.
- PS5 / PSVR2 Discord listening path: final physical beta gate, not yet claimed as validated.

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
