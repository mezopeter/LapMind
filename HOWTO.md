# LapMind beta — setup and how-to

This guide is for the current LapMind `0.7.1` beta checkpoint.

LapMind is local-first. The core race engineer does not require a LapMind account, PC or cloud service. Discord is optional.

## 1. What you need

For the local core:

- an Android device;
- Gran Turismo 7 on PlayStation;
- the Android device and PlayStation on the same non-isolated local network;
- the PlayStation IPv4 address.

Current physical evidence is strongest on PS4. PS5 / PSVR2 is the final physical beta gate and is not yet claimed as validated.

For optional Discord voice:

- internet access;
- your normal Discord account;
- a private Discord server;
- one normal voice channel;
- a dedicated Discord bot token.

LapMind never needs your Discord password, normal-user token, PSN password, Client Secret, Application ID, Guild ID or Channel ID.

---

# PlayStation setup

## 2. Find the PlayStation IP address

On the PlayStation, open the network connection information and note the console's current IPv4 address.

Example format:

`192.168.1.42`

Do not publish this address in a GitHub issue.

## 3. Create a PlayStation profile in LapMind

1. Open LapMind.
2. Add a PlayStation profile.
3. Give it a useful name, for example `PS5 Living Room` or `PS4 Copenhagen`.
4. Enter the console IPv4 address.
5. Choose a profile icon if you want one.
6. Save/back out of the editor.

Saved profile actions are deliberately simple:

- **profile icon** → Edit;
- **Wi-Fi icon** → Connect that PlayStation;
- **pencil icon** → Edit.

Long profile names can use two lines on the saved card; the full name remains editable in the profile editor.

## 4. Start a GT7 session

1. Make sure the Android device and PlayStation are still on the same LAN/Wi-Fi.
2. Start Gran Turismo 7.
3. In LapMind, use the saved profile's **Wi-Fi / Connect** action.
4. Enter a GT7 race, practice or Time Trial.
5. Drive normally.

LapMind separates console contact from actual GT7 telemetry. A reachable PlayStation does not necessarily mean GT7 telemetry is already active.

If telemetry does not appear, first check:

- the saved IPv4 address;
- guest Wi-Fi / AP isolation;
- whether the PlayStation and Android device can actually reach each other locally;
- whether GT7 is running and has entered a telemetry-producing state.

## 5. Local voice

Local Android TTS is the core voice path and does not depend on Discord.

Use the voice preview in LapMind to check the installed voice before driving. LapMind intentionally stays quiet when it cannot support a callout confidently.

## 6. Sessions

Open **Sessions** to review locally stored sessions.

Normal mode uses the right-side vertical `⋮` menu for global actions such as selection, import and backup.

Selection mode shows direct contextual actions instead of the normal overflow menu.

Session details include:

- **EDIT DETAILS** as the main action;
- **Export this session** as a lightweight utility action;
- **Reject session** as a destructive utility action where applicable.

When you open a session from lower down the list and go Back, LapMind returns to the same list position. Each newly opened Session details page starts at the top.

Use **Backup all** once your local session history becomes valuable.

---

# Optional Discord setup

Discord is not required for telemetry or local voice.

The intended VR workflow is:

```text
GT7 telemetry → LapMind on Android → private Discord bot voice → PS5 / PSVR2 headset
```

The final PS5 / PSVR2 end-to-end path is still the last physical beta gate.

## 7. Create the private Discord bot

Use your Discord account, or create one.

1. Create a private Discord server for LapMind.
2. Create one normal voice channel, for example `Race Engineer`.
3. Open the Discord Developer Portal.
4. Create a new application.
5. Open its **Bot** section and create/add the bot.
6. Install the bot only to your private server.
7. Give the bot only the voice-channel permissions it needs:
   - **View Channel**
   - **Connect**
   - **Speak**
8. Generate or reset the **bot token**.

Treat the bot token like a password.

Do not give the bot Administrator, moderation or message-management permissions for LapMind.

## 8. Configure Discord in LapMind

1. Open **Settings → Discord Settings**.
2. Paste the dedicated bot token.
3. Save the token locally.
4. Load your private servers.
5. Select the intended server.
6. Load voice channels.
7. Select the intended voice channel.
8. Connect the Discord output.
9. Use the built-in voice preview/test before relying on it in a race.

LapMind resolves server/channel identifiers internally. You do not need to copy Guild IDs or Channel IDs manually.

The saved bot token is local to the Android device and is not part of session exports/backups.

## 9. Listen on PlayStation / PSVR2

For the intended PS5 path:

1. Link your normal Discord account to PlayStation Network using Sony/Discord's normal account-linking flow.
2. Join the same private Discord voice channel on PS5.
3. LapMind's bot should appear as a separate participant.
4. Route/mix the Discord voice into the headset using the normal PS5 / PSVR2 audio controls.

**This exact PS5 / PSVR2 listening path is the final physical beta gate.** Until it has passed, the public project does not claim it as validated.

## 10. Disconnect, close and revoke

- Disconnect the Discord output when you only want to stop Discord voice.
- **Fully close LapMind** when you want LapMind's receiver, Discord connection and LapMind background activity stopped.
- Use the token-forget/remove action if you no longer want LapMind to retain the bot token locally.
- Reset the token in Discord Developer Portal if you believe it has been exposed.
- Remove the bot from the private server to revoke its access to that server.

---

# Privacy and troubleshooting

LapMind does not automatically upload telemetry, sessions or diagnostics.

Do not post these publicly:

- Discord bot tokens;
- PlayStation IP addresses;
- private session exports;
- diagnostics ZIPs containing your telemetry.

For current product boundaries see [KNOWN_LIMITATIONS.md](KNOWN_LIMITATIONS.md), [BETA.md](BETA.md) and [PRIVACY.md](PRIVACY.md).

Support: **support@lap-mind.com**
