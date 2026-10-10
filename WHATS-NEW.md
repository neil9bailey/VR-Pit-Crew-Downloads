# What's new in VR Pit Crew — 0.3.1 to 0.4.4

*Last updated 10 October 2026 for build 0.4.4.* The download links shared with the
first preview still deliver the current version. To update, close the app and run
the new installer over the old folder; profiles, backups and recordings stay.

**Download:** https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/tag/v0.4.4
(installer or portable ZIP, SHA-256 checksums included).

## What the first preview (0.3.1) could do

- Scan your PC for the things AC VR needs (CSP, Pure, Content Manager, Meta Link,
  NVIDIA, wheel) and walk you through setup.
- Read and change about 100 settings across AC graphics, CSP, Quest Link, the NVIDIA
  driver profile, Windows power/USB/services and wheel feedback, with a preview
  before applying, byte-exact backups and Undo.
- Save and load tuning profiles.
- Basic Quest runtime profiles (ASW and supersampling through Meta's command-line tool).
- Live AC telemetry and application frame-time recording with charts and CSV export.
- A Windows installer with .NET / WebView2 checks and an uninstaller that leaves
  your data alone.

## What's new since then

### Quest control centre — Tray Tool's job, done independently (0.4.1 → 0.4.4)

- Per-game Quest profiles covering ASW mode, supersampling, FOV multipliers, mipmap
  generation and bias, adaptive GPU scaling, the performance HUD, CPU priorities for
  the game and the Meta runtime, timed delays, audio routing and a session power plan.
- **Automation:** pick a profile per sim and an idle/reset profile. When the sim
  starts, the profile goes out; when it exits, the idle profile goes back and any
  PC-side change (power plan, audio, priorities) is restored from a recovery record
  that survives crashes.
- **Headset confirmation (0.4.3):** Meta's tool never reports whether a setting took,
  so after every send the app shows the headset performance HUD for six seconds and
  then puts your profile's HUD choice back. 0.4.4 makes two quick sends hand over
  cleanly instead of cutting each other short.
- Native tray icon, opt-in start with Windows, global hotkeys, offline voice
  commands, HUD/ASW shortcuts.
- One-click read-only import of Oculus Tray Tool profiles. OTT is no longer needed
  alongside Pit Crew, and automation pauses if OTT is running rather than fighting it.
- More Link controls: sharpening, distortion curvature and dynamic bitrate maximum,
  alongside bitrate, encode width and codec.
- Automation no longer re-sends commands while a sim is still loading (0.4.2).
  Rift S and other headsets on the Meta runtime are covered by the Link controls (0.4.3).

### Tune — safer, and it now tells you what's wrong

- **Rig health card (0.4.3/0.4.4):** 17 checks for settings that commonly cause
  stutter, dropouts or a soft image: USB selective suspend, Windows game capture,
  desktop V-Sync, a frame cap below any headset refresh rate, single-pass stereo with
  CSP FSR, pixel density above 1.1 with 8× MSAA, a Pure filter without Pure, the
  Balanced power plan, optional vendor services, HEVC above 200 Mbps on USB Link,
  low RAM/VRAM combinations, no headset on USB, and whether Windows will let the
  frame recorder run. Each hint has a *Show setting* button. Nothing is changed for you.
- Undo can recover a change interrupted mid-apply (crash, power cut) and retry a
  partial Undo (0.4.2).
- Importing a profile from another PC keeps whatever fits and reports what it
  skipped, instead of rejecting the whole file (0.4.2).
- Profiles can be archived rather than deleted (0.4.2).

### Monitor — benchmarks you can compare

- **Benchmark presets (0.4.3):** five repeatable runs: Silverstone GP 20 AI, Monza
  10 AI, Spa 30 AI (heavy grid), Nordschleife Tourist solo and ACC Spa 20 AI. Arm
  one, start the session, and the recording begins by itself the moment AC's
  telemetry goes live. A 180-second option was added.
- Every capture records which tuning profile was applied and a fingerprint of your
  game settings, so two runs are compared like for like.
- If you leave the session early the recording stops by itself and keeps what it
  got (0.4.4).
- Statistics: average FPS, 1% low, p99 frame time, the share of frames over your
  headset's budget and GPU time, with the same caveat as day one: this is what the
  application presented, which on Link can be the desktop mirror, not headset frames.

### Setup and status

- Tells apart the last-launched AC version, Steam build, CSP version and build,
  active Pure package, weather controller and filter revision; checks Pure's
  declared minimum CSP build and warns about missing loader, controller or pureVR
  filter files (0.3.2).
- Content Manager is found even when it is not running (0.4.2). The PSVR2 page is
  hidden in the Quest edition (0.4.2).

### Updates, install and housekeeping

- **Update notice (0.4.3):** Preferences can check GitHub once a day and show a
  sidebar link when a newer release exists. Nothing downloads or installs itself,
  only the app version is sent, and the check can be switched off.
- Opening the app a second time brings the existing window to the front (0.4.3).
- Installer upgrades clean out the previous version's runtime files; `PitCrewData`
  is never touched (0.4.2).
- The package is verified clean on every release: no developer profiles,
  recordings, device IDs or logs inside (0.4.1 onward).
- Frame capture needs a Windows permission (an elevated app, or your account in the
  *Performance Log Users* group). 0.4.4 says so up front and explains the fix
  instead of failing when you press record.

## Numbers, for what they are worth

- Automated tests: 50 at 0.3.2, 197 at 0.4.4, plus an isolated installer test
  (fresh install, upgrade, uninstall, data preserved) and a real session on the
  maintainer's rig before each release.
- Still an **unsigned preview** (SmartScreen may warn; checksums are published),
  still focused on original AC, Quest USB Link and NVIDIA, still no "more FPS"
  promise: it changes settings and shows you what happened, nothing more.
- The app's only network call is the optional update check. Nothing about your rig
  is uploaded.

## Links

- [Release notes for 0.4.4](RELEASE-NOTES-0.4.4.md) · earlier notes:
  [0.4.3](RELEASE-NOTES-0.4.3.md), [0.4.2](RELEASE-NOTES-0.4.2.md),
  [0.4.1](RELEASE-NOTES-0.4.1.md), [0.3.2](RELEASE-NOTES-0.3.2.md),
  [0.3.1](RELEASE-NOTES-0.3.1.md)
- [Installation guide](INSTALL.md)
- [What it changes and how recovery works](TRUST-AND-SAFETY.md)
- [Quest feature matrix against Tray Tool](TRAY-TOOL-PARITY.md)
- Discord: https://discord.gg/8yVKdS2w9 · Optional support: https://paypal.me/neil9bailey

Feedback from different rigs (AMD GPUs, Rift S, Virtual Desktop, 72/80/120 Hz)
shapes the next build; the Rig health checks, benchmark presets and update notice
all came from comments on the first post.
