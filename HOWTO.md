# LapMind beta — setup and how-to

This guide describes the latest identified development candidate, `0.7.2-beta37` (versionCode 95). It has not been released as Public Beta; labels can change before release.

LapMind is local-first. There is no LapMind account and the core race engineer does not require a PC or cloud service. Discord is optional.

## 1. What you need

For the local core:

- an Android device;
- Gran Turismo 7 on PlayStation;
- the Android device and PlayStation on the same non-isolated local network;
- the PlayStation IPv4 address.

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

Local Android TTS is part of the core voice path and does not depend on Discord.

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

The current session-package flow has been physically checked through the full round trip:

**Analyse → Export → Delete → Import → Analyse**

That means exported session data can genuinely leave the local store, be removed, then return and remain useful for review.

---

# Optional Discord setup

Discord is not required for telemetry or local Android voice.

The Discord Companion main screen links to two native guides: **Discord beginner guide** for bot and channel setup, and **PS5 / PS5 Pro Discord guide** for console voice chat. The PS5 and PS5 Pro instructions are the same unless the console itself presents a different system prompt.

It becomes especially useful when your headset cannot mix PlayStation audio and Android audio directly.

LapMind originally grew out of exactly that situation: **PS5 + PSVR2 + Sony INZONE Buds**. In that setup, Discord provides the practical route for the race engineer to reach the same headset as GT7.

The intended flow is:

```text
GT7 telemetry → LapMind on Android → private Discord bot voice → PlayStation headset
```

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

1. Open **Settings → Discord Companion → Set up Discord**.
2. Paste the bot token and choose **Validate token**. LapMind stores it encrypted on this device, clears the text field, then checks it while loading your available servers.
3. Select your private server and voice channel by name. LapMind resolves their identifiers internally.
4. Choose **Connect Discord** and wait for **Connected**.
5. Join the same voice channel with your normal Discord account on another device. On PS5 or PS5 Pro, use the separate console guide to link your account and join from the console.
6. Choose **Test voice** and confirm that you actually hear: “Discord connected. Voice test successful. Hopefully.” A Connected status alone does not confirm audible delivery.

The saved bot token remains on this Android device and is not part of session exports/backups. Keep it private.

## 9. Listen on PlayStation / PSVR2

For a PlayStation headset path:

1. Link your normal Discord account to PlayStation Network. On PS5, press the PS button, open **Game Base → Discord**, select **Link Account**, and follow the prompts. If the accounts were linked before Discord voice chat became available on PS5, relink only if prompted or voice chat is unavailable.
2. Join the same private Discord voice channel on the console. Your normal Discord account must be a member of the server; LapMind's bot is a separate participant.
3. Return to GT7 and check that both game audio and Discord voice are audible through your chosen headset or console output. Use the Discord voice-chat card's **Audio Balance** and member-volume controls if needed; this is a check, not a guarantee that every audio setup will mix both sources.

The console guide also covers joining from Discord on another device, leaving/rejoining voice chat and troubleshooting. No PSVR2 audio-mixing behavior or physical validation is claimed here.

## 10. Disconnect, close and revoke

- Choose **Disconnect** in LapMind to stop the bot's Discord voice connection. Choosing **Leave** on PS5 leaves your personal Discord account's voice chat; these are separate actions.
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
