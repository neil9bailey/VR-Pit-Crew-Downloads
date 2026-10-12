**Current application build: 0.4.5 — published 12 October 2026.**

## Download

- [Windows installer — VR Pit Crew 0.4.5](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/download/v0.4.5/VR-Pit-Crew-0.4.5-Setup-x64.exe)
- [Portable ZIP — VR Pit Crew 0.4.5](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/download/v0.4.5/VR-Pit-Crew-0.4.5-Windows-x64.zip)
- [SHA256 checksums](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/download/v0.4.5/SHA256SUMS-0.4.5.txt)
- [Per-archive checksum file](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/download/v0.4.5/VR-Pit-Crew-0.4.5-Windows-x64.sha256)
- [Release page](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/tag/v0.4.5)

These are the current versioned assets. GitHub's automatic Source code archives contain public documentation, not application source.

## Recommended update

0.4.5 is a stability fix. **Everyone on 0.4.4 or earlier should update**, especially
if you leave Pit Crew running in the tray with Quest automation on.

## Fixed

- **Pit Crew slowly used more memory and could stop responding after a long time
  running.** The routine that checks which programs are running (used once a second
  by Quest automation, and by Monitor while a benchmark is armed or the window is
  open) created a small piece of data every time it ran that was never released.
  Over many hours the app grew by tens of megabytes an hour and each internal
  clean-up took longer, until the window could stop responding — on the maintainer's
  rig after about a day with a benchmark armed. The USB and controller scans had the
  same pattern. All three now set this data up once, so memory and responsiveness
  stay flat however long the app runs.
- No settings, profiles or recordings were ever at risk; the problem was memory and
  responsiveness only.

Everything else is unchanged from [0.4.4](RELEASE-NOTES-0.4.4.md).

## Validation and limits

201 automated tests passed in four consecutive runs, including new ones that fail
on 0.4.4 and pass on 0.4.5: no Windows data structure may be declared inside a
repeatedly called function, and repeated process, service, memory, USB and
controller probes must not leave anything behind. Measured on the process check:
4,000 calls on the old code grew memory from 9 to 40 MB and kept climbing; on the
fixed code it stays at about 10 MB. An isolated installer test verified a fresh
install, an upgrade over an existing install (stale runtime files removed,
`PitCrewData` kept) and uninstall, and the packaged app ran with a benchmark armed
with flat memory and steady handles.

No universal compatibility or FPS improvement is guaranteed. PresentMon measures
application presentations, which can be the desktop mirror; it is not headset FPS.

**Updating:** Close Pit Crew from the tray and install into the same folder. Existing
users keep their own PitCrewData: profiles, preferences, backups and recordings.
Preferences → Updates shows when a newer release exists; there is no automatic
updater.

**Requirements:** Windows 10/11 x64, .NET Framework 4.8+ and Microsoft Edge WebView2
Runtime. Python is bundled. Game/mod/vendor installations remain separate.

**Unsigned preview:** Windows may show a reputation warning. Use official files
and matching checksums; do not disable security software globally.

[Installation guide](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/blob/main/INSTALL.md) ·
[Trust and recovery](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/blob/main/TRUST-AND-SAFETY.md)

Community: https://discord.gg/8yVKdS2w9
Optional support: https://paypal.me/neil9bailey

Free to use, closed source, optional contributions. GitHub counts asset downloads,
including repeats and verification downloads, not unique users or installations.
