# Install VR Pit Crew

## Windows installer

1. Download `VR-Pit-Crew-0.3.1-Setup-x64.exe` from the [official release](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/tag/v0.3.1).
2. Close VR Pit Crew if it is running. Run Setup, review the licence and choose whether to add a desktop shortcut.
3. Keep the default installation folder unless you need a different writable location. Setup installs for your Windows account without requiring administrator access.
4. Launch **VR Pit Crew** from the Start menu and open **Setup** for the prerequisite scan.

Python is included. The app requires Windows 10/11 x64, Microsoft .NET Framework 4.8 or newer and Microsoft Edge WebView2 Runtime. If Setup reports a missing runtime, install it from Microsoft and rerun Setup:

- [.NET Framework 4.8](https://dotnet.microsoft.com/download/dotnet-framework/net48)
- [WebView2 Evergreen Runtime](https://developer.microsoft.com/microsoft-edge/webview2/)

The installer does not install games, paid mods, vendor drivers or Meta software. The Setup module links to relevant tools. Optional Windows/service changes and some capture features can require **Administrator mode** inside the app.

## Portable option

Extract the complete portable ZIP to a writable folder. Run `VR Pit Crew.exe` and keep `_internal` beside it. No separate Python installation is needed.

## Updates and your settings

Close the app and run the new installer into the same folder. Profiles, backups, preferences and recordings are kept in `PitCrewData` beside the EXE. Back up that folder before moving installations. If migrating from a portable copy, close both copies and copy your existing `PitCrewData` into the new installation folder before starting it.

The installer checks that the target EXE can be replaced. If it asks you to close the app, do so and rerun Setup. Do not install into a protected system folder; the app needs to write its data beside the EXE.

## Uninstall

Use Windows Installed apps / Apps & features, or **VR Pit Crew → Uninstall** in the Start menu. Uninstall removes the packaged program and shortcuts, while retaining `PitCrewData` and other files you added. It does not undo previously applied game, GPU or Windows settings; use the app's History/Undo before uninstalling if you want to revert a supported change.

## Preview status and integrity

This release is unsigned, so Windows can show an unknown publisher or reputation warning. No code-signing certificate is bundled. Download only from the official release and compare its SHA256 to `SHA256SUMS.txt` if you want to check file integrity. A matching checksum checks bytes; it is not publisher certification.

The package has local tests, but second-PC compatibility and real headset/runtime behaviour still need wider validation. Start with a saved baseline and small, reviewed changes.
