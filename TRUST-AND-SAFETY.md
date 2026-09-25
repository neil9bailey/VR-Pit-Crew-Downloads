# Trust, safety and recovery

## SmartScreen and publisher identity

The first public builds are unsigned. Windows SmartScreen may show an unknown-publisher or unrecognized-app warning because there is no trusted code-signing certificate attached yet. This is expected for an early release, but treat it as a real trust decision: download only from the official GitHub release, verify the published SHA256 checksum, and review the release notes before running it. Do not disable Defender or SmartScreen globally. If your organization blocks unsigned software, wait for a signed build or ask your administrator to approve this specific release.

The installer and EXE carry Neil9Bailey as the package publisher metadata, but that metadata is not a cryptographic signature. A checksum confirms that the downloaded bytes match the published release; it does not prove who created them. A future signed release will show a certificate-backed publisher identity.

## What changes and how recovery works

VR Pit Crew does not silently tune the machine at startup. The normal flow is:

1. Read the current state.
2. Review the proposed changes.
3. Apply only after confirmation.
4. Save an original snapshot and verification record for supported targets.

History and Undo can restore supported changes when the backup is intact and no newer edit has replaced it. Undo checks for drift and refuses to overwrite a newer edit. Failed multi-setting writes roll back the writes already made when the backend supports rollback.

There is no “Leave No Trace on exit” promise in this release. Closing the app does not automatically undo applied game, driver, power-plan, service, registry or Tray Tool changes. Those settings are intended to persist after a reboot. Use the app's History → Undo before changing or uninstalling if you want to restore a supported snapshot. The app keeps `PitCrewData` beside the installation so profiles and backups survive updates; back it up before moving or deleting it.

Quest runtime automation is separate. It is off by default, sends a chosen profile only while the app is open, pauses after command failure or conflicts, and leaves the last runtime value when the app closes unless the configured idle-reset transition runs. Verify manual Quest changes with the Meta performance HUD. Command dispatch is logged as sent/unverified; the app does not claim headset readback.

## Scope and telemetry

The app shows the scope of each pending change before apply. It does not upload telemetry, profiles, backups, payment data or system reports automatically. Application frame-time recordings remain local. PresentMon readings may measure the desktop mirror and are not headset FPS or Link latency.

If an outcome is unclear, stop the sim, read the current state, and use the app's History and verification report. For help, use the Discord channel and redact personal paths, usernames and identifiers from screenshots or logs.
