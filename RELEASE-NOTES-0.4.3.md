**Current application build: 0.4.3 — published 10 October 2026.**

## Download

- [Windows installer — VR Pit Crew 0.4.3](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/download/v0.4.3/VR-Pit-Crew-0.4.3-Setup-x64.exe)
- [Portable ZIP — VR Pit Crew 0.4.3](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/download/v0.4.3/VR-Pit-Crew-0.4.3-Windows-x64.zip)
- [SHA256 checksums](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/download/v0.4.3/SHA256SUMS-0.4.3.txt)
- [Per-archive checksum file](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/download/v0.4.3/VR-Pit-Crew-0.4.3-Windows-x64.sha256)
- [Release page](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/tag/v0.4.3)

These are the current versioned assets. GitHub's automatic Source code archives contain public documentation, not application source.

## Your rig, your profiles

Fresh installations contain **no developer profiles, personal settings, recorded
sessions, telemetry exports, backups, logs or selected devices**. Setup opens on
first launch and scans your PC. Profiles, History and recordings start empty.
Quest automation, Windows startup, voice and hotkeys start off. Opening the app
does not apply tuning. Save your own baseline in Tune and create your own Quest
game/idle profiles. Optional built-in presets are suggestions for review.

## New since 0.4.2

- **See what the headset actually received.** Meta's command-line tool never
  reports whether a runtime setting took effect, so after every send (a profile
  apply, a detected game, a delayed ASW change or a before-launch profile) Pit
  Crew now shows the headset performance HUD for six seconds, then puts your
  profile's HUD choice back. Messages and the journal say plainly what was sent
  and what still needs a look, and a timed-out command now tells you to check
  that the headset and Link are connected. Switch the confirmation off under
  Quest → Desktop options if you prefer.
- **Rig health card on the Tune page.** Sixteen checks for settings that commonly
  cause stutter, dropouts or a soft picture: USB selective suspend, Windows game
  capture, desktop V-Sync, a frame limit below any headset refresh rate,
  single-pass stereo together with CSP FSR, pixel density above 1.1 with 8× MSAA,
  a Pure filter without Pure, the Balanced power plan, optional vendor services,
  HEVC above 200 Mbps on USB Link and more. Each hint has a Show setting button
  that jumps to the control; nothing is changed for you.
- **Benchmark presets in Monitor.** Five repeatable runs (Silverstone 20 cars,
  Monza 10 cars, Spa 30 cars, Nordschleife solo and ACC Spa 20 cars) plus a
  180-second duration. Arm one, then start the sim: the recording begins on its
  own as soon as Assetto Corsa's telemetry goes live (other sims after a 45-second
  settle). Every capture now records which tuning profile was last applied and a
  fingerprint of the tracked game settings, so two runs can be compared fairly.
- **Update notice.** Preferences → Updates asks GitHub once a day, or when you
  choose Check now, whether a newer release exists and shows a link in the
  sidebar. Nothing is downloaded or installed automatically, only the app version
  is sent, and the check can be switched off.
- Opening the app a second time now brings the existing window to the front,
  even when it was hidden in the tray.
- Rift S and other headsets on the Meta runtime are now named where the Link
  controls apply, and Windows services that are not installed read "Not
  installed" instead of a blank.

See the [Quest feature matrix](TRAY-TOOL-PARITY.md) for what remains to be
validated on-headset. Full historical Tray Tool parity is still incomplete.

## Validation and limits

193 automated tests passed, covering the HUD confirmation, Rig health rules,
benchmark presets and update check alongside the existing transaction, review,
apply, verify, rollback and undo logic. An isolated installer test verified a
fresh install, an upgrade over an existing install (stale runtime files removed,
`PitCrewData` kept) and uninstall. The build was then installed over 0.4.2 on the
maintainer's own rig: profiles and automation bindings survived, the Rig health
card, benchmark presets, update check and second-launch hand-off were checked
working, and the live update check correctly reported the published release.

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
