**Current application build: 0.4.4 — published 10 October 2026.**

## Download

- [Windows installer — VR Pit Crew 0.4.4](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/download/v0.4.4/VR-Pit-Crew-0.4.4-Setup-x64.exe)
- [Portable ZIP — VR Pit Crew 0.4.4](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/download/v0.4.4/VR-Pit-Crew-0.4.4-Windows-x64.zip)
- [SHA256 checksums](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/download/v0.4.4/SHA256SUMS-0.4.4.txt)
- [Per-archive checksum file](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/download/v0.4.4/VR-Pit-Crew-0.4.4-Windows-x64.sha256)
- [Release page](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/tag/v0.4.4)

These are the current versioned assets. GitHub's automatic Source code archives contain public documentation, not application source.

## Your rig, your profiles

Fresh installations contain **no developer profiles, personal settings, recorded
sessions, telemetry exports, backups, logs or selected devices**. Setup opens on
first launch and scans your PC. Profiles, History and recordings start empty.
Quest automation, Windows startup, voice and hotkeys start off. Opening the app
does not apply tuning. Save your own baseline in Tune and create your own Quest
game/idle profiles. Optional built-in presets are suggestions for review.

## New since 0.4.3

Three fixes from the first full session on the maintainer's rig with 0.4.3:

- **Headset confirmation hands over cleanly.** When two runtime sends land a few
  seconds apart (a detected game followed by a delayed ASW change, for example)
  the newer HUD flash now takes over instead of the earlier one switching the HUD
  off part-way through. A HUD shortcut, or a profile that sets the HUD itself,
  also cancels any confirmation still counting down, so the HUD you asked for
  stays as you set it.
- **Recordings end when the sim does.** If you leave the session before a
  benchmark or manual recording reaches its planned length, the capture now stops
  by itself, keeps the frames collected so far and says how far it got (for
  example "Assetto Corsa exited after 155 of the planned 180 seconds").
- **Frame-capture permission is flagged up front.** PresentMon can only record
  frames for an elevated process or an account in Windows' *Performance Log
  Users* group. Rig health now warns before you record if Windows will refuse the
  trace, the Monitor page says the same, and the "access denied" message explains
  the group fix as well as Administrator mode. AC telemetry and PC sensors never
  needed this permission.

See the [Quest feature matrix](TRAY-TOOL-PARITY.md) for what remains to be
validated on-headset. Full historical Tray Tool parity is still incomplete.

## Validation and limits

197 automated tests passed, including new ones for the HUD hand-over, the early
stop and the permission check. An isolated installer test verified a fresh
install, an upgrade over an existing install (stale runtime files removed,
`PitCrewData` kept) and uninstall. The build was then installed over 0.4.3 on the
maintainer's own rig: profiles, automation bindings and the earlier benchmark
capture survived, the permission check reported the rig correctly and the live
update check saw the published release.

Native Windows/NVIDIA writes, the tray, hotkeys, voice and a live PresentMon
capture are exercised by the app itself, not by an independent test harness.
No universal compatibility or FPS improvement is guaranteed. PresentMon measures
application presentations, which can be the desktop mirror; it is not headset FPS.

**Updating:** Close Pit Crew and install into the same folder. Existing users keep
their own PitCrewData: profiles, preferences, backups and recordings. A clean
release does not wipe existing data. The app can tell you that a newer version
exists, but there is no automatic updater.

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
