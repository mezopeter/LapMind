# Credits and references

LapMind did not invent GT7 UDP telemetry. It builds on public protocol research,
open-source tools, openly licensed data, direct physical testing and careful
comparison between those sources.

This file records technical and data provenance at a human-readable level. The
formal `THIRD_PARTY_NOTICES.md` shipped with a beta APK will list every component
and licence actually included in that exact build.

## Protocol and behaviour references

### Nenkai / PDTools

- Project: <https://github.com/Nenkai/PDTools>
- Licence: MIT
- Role: simulator interface, packet structure and GT7 cryptography reference.

### MacManley / gt7-udp

- Project: <https://github.com/MacManley/gt7-udp>
- Licence: MIT
- Role: Packet A/B/C structure, offsets and car-code research reference.

### caa1211 / esp32-gt7-dashboard

- Project: <https://github.com/caa1211/esp32-gt7-dashboard>
- Licence: MIT
- Role: comparison reference for fuel-estimation behaviour and telemetry edge
  cases.

These projects were used to verify and cross-check behaviour; LapMind does not
claim their protocol discoveries as original work.

## Offline inventory and Track Lab seed data

### zetetos / gt-telemetry

- Project: <https://github.com/zetetos/gt-telemetry>
- Snapshot used privately: `ba82a67f7d095e44ee112cc93db83c821227f21e`
- Licence: MIT
- Role: vehicle/circuit inventory and normalized circuit skeleton inputs.

### jbhoorasingh / gt7-datalogger-track-data

- Project: <https://github.com/jbhoorasingh/gt7-datalogger-track-data>
- Snapshot used privately: `ea01075a3cc8f67bab7c9110a688d41d6ce3c2f7`
- Data licence: CC0 1.0 for the upstream `tracks/` and `index.json` data
- Role: surveyed ROAD geometry seeds, finish evidence, partial elevation and
  labelled corners.

### RealJean42 / GT7Analyzer

- Project: <https://github.com/RealJean42/GT7Analyzer>
- Snapshot used privately: `6532f706c401e40e091893471570b098b9cec8ce`
- Licence: MIT
- Role: three legacy example geometry seeds used only as separately labelled,
  unvalidated guide/edge data.

Imported geometry is not represented as an official track model, an optimal
racing line or proof of driving quality.

## Discord voice implementation references

### KyokoBot / libdave-jvm

- Project: <https://github.com/KyokoBot/libdave-jvm>
- Pinned development snapshot: `ce725965eb81e4878b474da226ea7cb0053f6cf9`
- Licence: Apache License 2.0
- Role: Java/JNI integration for Discord's DAVE voice encryption.

### Discord / libdave

- Project: <https://github.com/discord/libdave>
- Licence: MIT
- Role: official DAVE/MLS implementation used by the pinned native voice build.

The beta's formal third-party notice will also retain the required notices for
transitive native and Android dependencies.

## Related products and market context

Many GT7 and broader sim-racing projects explore voice engineers, telemetry,
lap comparison, coaching or community reference data. Discovering them helped
clarify that LapMind should not compete by copying a feature list. Mention of a
product in research or project history does not imply affiliation, endorsement
or copied implementation.

## Trademarks

LapMind is independent and unofficial. Gran Turismo, GT7, PlayStation, PS4, PS5
and PSVR2 are trademarks of their respective owners. Discord is a trademark of
Discord Inc. Project and company names above belong to their respective owners.
