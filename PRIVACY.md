# Privacy

LapMind is designed as a local-first application. This document describes the
current beta design; the exact notice will be checked again against every
published APK.

## No mandatory LapMind account

The core app does not require a LapMind username, email address or cloud
account. A GitHub account may be needed to submit public feedback, and Discord
requires its own account and service, but neither is a LapMind account.

## Local telemetry and sessions

GT7 telemetry travels from the PlayStation to the Android device over the local
network. The core processes it on the device. Session summaries and user-entered
notes are stored locally.

LapMind does not require telemetry or session history to be uploaded to a
LapMind server. Session backup/export occurs only when the user requests it.

Saved PlayStation profiles contain a local console address needed for telemetry
reception. That address is not included in normal session backup packages or
diagnostics exports.

## Optional Discord output

Discord is an external network service and is not part of offline core use.
When the user explicitly configures and connects the optional companion:

- a dedicated Discord bot token is used to authenticate with Discord;
- the selected server and voice-channel identifiers are used for connection;
- generated engineer speech is sent to the selected private Discord voice
  channel;
- Discord and the network necessarily process connection metadata according to
  their own services and policies.

The app does not ask for a normal Discord-user password or user token. The bot
token is stored as ciphertext in app-private preferences using an
Android-Keystore key and is excluded from Android backup/device transfer.
`Forget token` removes the saved token and target from the app.

Discord failures are isolated from telemetry, local TTS, haptics and sessions.

## Diagnostics

Diagnostics recording is optional and off by default. An export may contain
telemetry samples, timing, decoded vehicle/track fields and application
decisions. The current format excludes:

- PlayStation IP addresses;
- Discord tokens and target identifiers;
- Discord or PSN passwords;
- unnecessary device identifiers.

Diagnostics may still reveal how, when, where and with which virtual vehicle a
session was driven. Treat them as personal files.

## Public bug reports

GitHub Issues and their attachments may be public. Do not post:

- diagnostics ZIPs unless a safe handoff has been agreed separately;
- private session exports;
- Discord tokens or bot configuration secrets;
- PlayStation IP addresses;
- screenshots containing private server, account or device information.

Start with the text-only issue template. If raw evidence is necessary, a
private transfer method should be agreed before sharing it.

## User control

The user can stop telemetry and the optional Discord link with the app's Close
App flow, disconnect Discord separately, forget the stored bot token, delete
local sessions, and export or back up selected data deliberately.

Questions or suspected privacy/security problems should be reported without
including the sensitive value itself.
