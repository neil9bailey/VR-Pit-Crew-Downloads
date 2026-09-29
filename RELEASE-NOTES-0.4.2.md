**Current application build: 0.4.2 — published 29 September 2026.**

## Download

- [Windows installer — VR Pit Crew 0.4.2](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/download/v0.4.2/VR-Pit-Crew-0.4.2-Setup-x64.exe)
- [Portable ZIP — VR Pit Crew 0.4.2](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/download/v0.4.2/VR-Pit-Crew-0.4.2-Windows-x64.zip)
- [SHA256 checksums](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/download/v0.4.2/SHA256SUMS-0.4.2.txt)
- [Per-archive checksum file](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/download/v0.4.2/VR-Pit-Crew-0.4.2-Windows-x64.sha256)
- [Release page](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/tag/v0.4.2)

These are the current versioned assets. GitHub's automatic Source code archives contain public documentation, not application source.

## Your rig, your profiles

Fresh installations contain **no developer profiles, personal settings, recorded
sessions, telemetry exports, backups, logs or selected devices**. Setup opens on
first launch and scans your PC. Profiles, History and recordings start empty.
Quest automation, Windows startup, voice and hotkeys start off. Opening the app
does not apply tuning. Save your own baseline in Tune and create your own Quest
game/idle profiles. Optional built-in presets are suggestions for review.

## New since 0.4.1

- The PSVR2 sidebar page is no longer shown in the Quest edition; the app now
  determines its own edition at run time instead of only naming the package.
  Setup's prerequisite scan and guided steps count only Quest items.
- Tuning Undo can recover a change interrupted mid-apply (a crash or power loss)
  and can be retried if it only partly completes, instead of only working on a
  clean "applied" record.
- Importing a saved tuning profile now uses whatever fits this PC and reports
  what it had to skip, instead of rejecting the whole file over one mismatched
  value such as a Windows power plan.
- Saved tuning profiles can be archived (kept, not deleted) from the Profiles page.
- Quest automation no longer re-sends commands and PC settings repeatedly while
  a sim is still starting up.
- The NVIDIA "Trilinear optimisation" control's On/Off labelling is corrected.
- Content Manager is now detected even when it is not running.
- An installer upgrade now removes the previous version's runtime files cleanly
  instead of leaving old ones behind; user data in `PitCrewData` is untouched.
- `RELEASE-GUIDE.md` (publisher-only notes) is no longer bundled in the package.

See the [Quest feature matrix](TRAY-TOOL-PARITY.md) for what remains to be
validated on-headset. Full historical Tray Tool parity is still incomplete.

## Validation and limits

153 automated tests passed, covering the fixes above alongside the existing
transaction, review, apply, verify, rollback and undo logic. An isolated
installer test verified a fresh install, an upgrade over an existing install,
and uninstall, confirming `PitCrewData` survives each step. The build was also
installed and used on the maintainer's own rig: a settings review, apply and
undo, the Setup scan, and the Quest page were all checked working.

Native Windows/NVIDIA writes, the tray, hotkeys, voice and a live PresentMon
capture are exercised by the app itself, not by an independent test harness.
No universal compatibility or FPS improvement is guaranteed. PresentMon measures
application presentations, which can be the desktop mirror; it is not headset FPS.

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
