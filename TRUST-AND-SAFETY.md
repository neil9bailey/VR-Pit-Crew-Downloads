# Trust, safety and recovery

## SmartScreen and publisher identity

The first public builds are unsigned. Windows SmartScreen may show an unknown-publisher or unrecognized-app warning because there is no trusted code-signing certificate attached yet. Download only from the official GitHub release and compare the published SHA256 checksum if desired. Do not disable Defender or SmartScreen globally. If your organization blocks unsigned software, wait for a signed build or ask your administrator to approve this specific release.

The installer and EXE carry Neil9Bailey as package publisher metadata, but that metadata is not a cryptographic signature. A checksum confirms that downloaded bytes match the published release; it does not prove who created them. A future signed release will show a certificate-backed publisher identity.

## What changes and how recovery works

VR Pit Crew reads current state, shows proposed changes, asks for confirmation, and saves supported original snapshots and verification records before applying. History and Undo can restore supported changes when the backup is intact and no newer edit has replaced it. Undo checks for drift and refuses to overwrite a newer edit. Failed multi-setting writes roll back writes already made when the backend supports rollback.

There is no “Leave No Trace on exit” promise in this release. Closing the app does not automatically undo applied game, driver, power-plan, service, registry changes made in Tune. Those settings are intended to persist after a reboot. Use History → Undo before changing or uninstalling if you want to restore a supported snapshot. `PitCrewData` beside the EXE stores profiles and backups and survives updates; back it up before moving or deleting it.

Quest runtime automation is separate. PC-side session audio, power and priority changes have durable recovery records and are restored on game/app exit when they have not been replaced externally. After interruption, use Quest → Migration & recovery. Runtime reset-on-close is an explicit setting. It is off by default, sends a chosen profile only while the app is open, pauses after command failure or conflicts, and leaves the last runtime value when the app closes unless the configured idle-reset transition runs. Verify manual Quest changes with the Meta performance HUD. Command dispatch is logged as sent/unverified; the app does not claim headset readback.

The app does not upload telemetry, profiles, backups, payment data or system reports automatically. Application frame-time recordings remain local. PresentMon readings may measure the desktop mirror and are not headset FPS or Link latency.
