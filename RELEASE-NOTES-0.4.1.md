**Current application build: 0.4.1 — published 28 September 2026.**

## Download

- [Windows installer — VR Pit Crew 0.4.1](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/download/v0.4.1/VR-Pit-Crew-0.4.1-Setup-x64.exe)
- [Portable ZIP — VR Pit Crew 0.4.1](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/download/v0.4.1/VR-Pit-Crew-0.4.1-Windows-x64.zip)
- [SHA256 checksums](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/download/v0.4.1/SHA256SUMS-0.4.1.txt)
- [Per-archive checksum file](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/download/v0.4.1/VR-Pit-Crew-0.4.1-Windows-x64.sha256)
- [Release page](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/tag/v0.4.1)

These are the current versioned assets. GitHub's automatic Source code archives contain public documentation, not application source.

## Your rig, your profiles

Fresh installations contain **no developer profiles, personal settings, recorded
sessions, telemetry exports, backups, logs or selected devices**. Setup opens on
first launch and scans your PC. Profiles, History and recordings start empty.
Quest automation, Windows startup, voice and hotkeys start off. Opening the app
does not apply tuning. Save your own baseline in Tune and create your own Quest
game/idle profiles. Optional built-in presets are suggestions for review.

## New since 0.3.2

- Independent Quest profiles: ASW, supersampling, FOV, mipmaps, HUD, delays,
  audio routing, process priorities and session power plans.
- Native tray, opt-in Windows startup, hotkeys and offline voice controls.
- Per-game automation, chosen idle reset and durable PC-setting recovery records.
- Read-only migration from Oculus Tray Tool; it is optional, not a runtime dependency.
- More Link controls and a fix for stale idle status after Tray Tool closes.
- Exact release allowlists and checks that reject recordings, profiles and user data.

Full historical Tray Tool parity is still incomplete. See the
[feature/validation matrix](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/blob/main/TRAY-TOOL-PARITY.md).
Meta Link remains required. The app retains version/configuration checks for AC,
Content Manager, CSP and Pure; it does not bundle or automatically upgrade mods.

## Validation and limits

67 automated tests passed. An isolated installer test verified all 256 payload
files, empty compiled defaults, and preservation of another user's profiles and
recordings during update and uninstall. Archive and compressed-code audits found
no developer data or baseline identifiers. First-use Setup and empty profile and
recording views were checked through the local interface.

Earlier local acceptance confirmed the Quest HUD, an audible smooth AC session,
automatic game detection, delayed runtime dispatch, idle reset and a real power
plan change/restore. Numerical headset setting readback, reboot acceptance,
microphone switching, hotkey/voice interaction and wider second-PC coverage remain
outstanding. No universal compatibility or FPS improvement is guaranteed.
PresentMon measures application presentations, which can be the desktop mirror;
it is not headset FPS.

**Updating:** Close Pit Crew and install into the same folder. Existing users keep
their own PitCrewData: profiles, preferences, backups and recordings. A clean
release does not wipe existing data. There is no automatic updater.

**Requirements:** Windows 10/11 x64, .NET Framework 4.8+ and Microsoft Edge WebView2
Runtime. Python is bundled. Game/mod/vendor installations remain separate.

**Unsigned preview:** Windows may show a reputation warning. Use official files
and matching checksums; do not disable security software globally. Tune changes
persist until changed or undone. Quest session PC settings have conditional
restoration; runtime reset uses your chosen idle profile. There is no blanket
"Leave No Trace" guarantee.

[Installation guide](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/blob/main/INSTALL.md) ·
[Trust and recovery](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/blob/main/TRUST-AND-SAFETY.md)

Community: https://discord.gg/8yVKdS2w9
Optional support: https://paypal.me/neil9bailey

Free to use, closed source, optional contributions. GitHub counts asset downloads,
including repeats and verification downloads, not unique users or installations.
