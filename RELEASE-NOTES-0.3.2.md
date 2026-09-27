**Current application build: 0.3.2 — updated 27 September 2026.**

This release page keeps the original shared download URLs working. The `v0.3.1` URL and the filenames containing `0.3.1` are compatibility names: the two current downloads below now install/run **VR Pit Crew 0.3.2**. The installer and application display 0.3.2.

## Download the current build
- [Windows installer — build 0.3.2](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/download/v0.3.1/VR-Pit-Crew-0.3.1-Setup-x64.exe)
- [Portable ZIP — build 0.3.2](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/download/v0.3.1/VR-Pit-Crew-0.3.1-Windows-x64.zip)
- [SHA256 checksums](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/download/v0.3.1/SHA256SUMS.txt)

Files marked **ORIGINAL** are archived 0.3.1 packages, retained with their previous download counts. Choose the links above for the current build. GitHub's automatic Source code archives contain the public documentation, not the application.

## Fixed in 0.3.2
- Distinguishes the last-launched Assetto Corsa version, Steam build, CSP version/build, active Pure package, weather controller and filter revision.
- Checks Pure's declared minimum CSP build and warns about missing loader, weather/controller or required pureVR filter files.
- Corrects Pure detection in Setup and the app version displayed in the sidebar.
- Includes trust and recovery guidance in the portable package.

**Validation:** 50 automated tests passed. The Windows EXE and its status/Setup readback were checked locally. An isolated installer test verified all 254 payload files and confirmed user data survives upgrade and uninstall. This is not a guarantee of compatibility or an FPS improvement on every rig. The developer rig's individual car/track repairs are not bundled.

**Updating:** Close VR Pit Crew and install into the same folder. Preserve `PitCrewData`, which contains your profiles, preferences, backups and recordings. The app has no automatic updater; existing users need to download and install this build.

**Requirements:** Windows 10/11 x64, .NET Framework 4.8+ and Microsoft Edge WebView2 Runtime. Python is bundled.

**Unsigned preview:** Windows may show an unknown-publisher or reputation warning. Download from this repository and verify the matching SHA256; do not disable Defender or SmartScreen globally. Supported changes are backed up and can be reverted through History → Undo, subject to drift checks. Settings are not automatically restored when the app closes.

**Remaining validation:** Wider second-PC testing, real Quest runtime effects and in-headset/on-track performance. PresentMon application FPS is not headset FPS.

[Installation guide](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/blob/main/INSTALL.md) · [Trust and recovery](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/blob/main/TRUST-AND-SAFETY.md)

Community: https://discord.gg/8yVKdS2w9  
Optional support: https://paypal.me/neil9bailey

Free to use, closed source, optional contributions. GitHub counts release-asset downloads, including repeat and verification downloads; they are not unique users or successful installations.
