# Quest runtime parity with Oculus Tray Tool: 0.4.1 public preview

Pit Crew's independent Quest module covers the Oculus Tray Tool functions sim racers
relied on, with no installed or running OTT dependency. This matrix tracks which
functions are implemented and which still need headset validation. Build 0.3.2 still
depended on OTT; build 0.4.0 moved the active workflow to independent Pit Crew
profiles and native Windows controls. It is a validation candidate, not a claim that
every historical OTT feature is complete.

## Functional coverage

| Tray Tool function | Pit Crew implementation | Verification / remaining work |
| --- | --- | --- |
| ASW and supersampling | Quest profiles and Meta's installed CLI | Validation/command tests; headset behaviour still needs testing |
| Global/default profile | Explicit idle profile; optional application on startup | Transition tests; live Meta startup test pending |
| Per-game profiles | Create, edit, archive, enable/disable, JSON import/export; executable matching including custom games | Source tests and browser save/review test |
| FOV horizontal/vertical | Independent paired multipliers | Command tests; reconnect Link and verify the visible crop |
| Adaptive GPU scaling | Independent runtime setting | Command validation; headset test pending |
| Mipmap generation and bias | Independent runtime settings | Command validation; installed runtime acceptance pending |
| Game and OVR/Dash priorities | Windows process API with identity checks and saved original priority | Own-process change/restore verified; game/runtime processes pending |
| ASW and priority delays | Separate bounded timers; cancellation on game exit | Simulated process/time transition tests |
| Performance HUD | Performance, timing, compositor, ASW, version and off commands | Command tests; visual headset check pending |
| Mirror controls | Minimise game window or launch installed OculusMirror; stop only the mirror Pit Crew launched | Desktop session validation pending |
| Quest Link bitrate, encode width, codec | Existing registry backend with before/after snapshots and Undo | Existing transaction tests; encoder effects require Link test |
| Link sharpening, distortion curvature, dynamic bitrate maximum | Added to normal tuning; defaults remove the corresponding override where appropriate | Registry transaction tests; inspect ODT and headset after apply |
| Playback/microphone switching | Windows endpoints; all console, multimedia and communications roles | Actual endpoint enumeration and same-value writes verified; session switching test pending |
| Audio/power/priority restoration | Durable original values; restore on managed game exit and app exit; explicit recovery after interruption | Partial-write rollback, disconnected-device and newer-value conflict tests |
| Session power plans | Choose installed plan per profile; restore original | Fixture tests; real plan switch/restore pending |
| USB selective suspend | Existing Windows tuning control | Existing read/apply/Undo implementation |
| Windows startup | Opt-in per-user Run entry, normal Windows permissions | EXE/reboot verification pending; no UAC bypass or elevated task installed |
| Minimise and close to tray | Native tray with Open, HUD controls and Exit | Code added; restricted execution session could not register a shell icon; normal desktop validation required |
| Keyboard hotkeys | Configurable Ctrl/Alt/Shift plus letter/digit/F-key | Parsing/collision tests; desktop registration pending |
| Voice controls | Opt-in offline Windows recognition, five wake-phrase commands | Requires installed System.Speech recognizer; microphone test pending |
| Meta service start/stop/restart | Bounded actions; blocks running sims and enabled automation | No service restart performed on the live rig |
| Launch with profile | Optional executable path; initial render commands before launch; assigned automation owns the session | Manual acceptance test pending |
| Logs | Profile attempts, result status, PC recovery history and import report | Local persistence tests |
| OTT migration | Read-only SQLite import including FOV, mipmaps, priority, delays, mirror and notes | Full synthetic import, disabled-state and repeat-import tests; source DB never written |

The old `ott.*` controls are removed from active tuning. The old database backend
is retained only to allow recovery of transactions made by earlier Pit Crew builds.
OTT is optional as a migration source; its executable, DLLs, database or bundled
Meta CLI are not shipped with Pit Crew. Meta Link and its runtime remain required.

## Open parity items

These are explicitly incomplete, not silently substituted:

- Vendor-library cover-art editing and bulk profile editing. Steam/Meta local manifest discovery is implemented; choose the actual executable before creating a profile.
- Custom voice phrases, push-to-talk bindings and spoken profile confirmations.
- Oculus-client hide/restore behaviour and automatic service lifecycle preferences.
- USB hub / legacy Rift sensor device power controls beyond the existing power-plan setting.
- Automatic app update checking. Existing users still download and reinstall.
- Individual HUD panels and ASW modes beyond the options exposed in the candidate.

Historical OTT features also require a separate compatibility decision: replacing
the old Rift Home binary, CPU-name spoofing and patching old Air Link timeouts.
The candidate does not modify Meta application binaries, pretend to implement these
features, or require OTT to provide them. The target current-Quest workflow and
literal parity with every legacy Rift feature are different acceptance scopes;
the latter is not complete.

## Acceptance before removing Tray Tool from the rig

1. Launch the candidate EXE normally in the Windows desktop. Verify its tray icon,
   restore/show action, and explicit Exit action. Test a hotkey that is unused by
   other software. If using voice, test recognition and disabling it.
2. Import OTT profiles, read the report, and configure global audio/power/startup
   choices explicitly. Import does not activate automation or change system settings.
3. Close OTT. With Link connected, apply one runtime setting at a time and verify it
   in Meta Debug Tool / the headset HUD. Check FOV and supersampling after reconnect.
4. Assign a game profile and an explicit reset profile covering every runtime
   override. Test game start, delayed commands, game exit, and restoration of audio,
   power and priorities. Verify actual audible headset sound.
5. Test interruption recovery, application exit and a reboot. Then disable OTT's
   startup, keeping its installation available for rollback until validation passes.
6. Repeat a familiar driving session and compare measured frame times. No FPS
   gain or full compatibility is claimed from unit tests alone.

The public preview includes these independent controls. They do not depend on
Oculus Tray Tool being installed. Full historical OTT parity is still incomplete.

Local acceptance has since confirmed a visible performance HUD, audible and smooth
AC driving, automatic game detection, delayed ASW dispatch, idle reset and a real
session power-plan change/restore. Startup registration and native tray readiness
were checked. Numerical headset setting readback, reboot acceptance, changing from
a different audio endpoint, microphone recording, voice and hotkey interaction,
and broader second-PC compatibility remain unverified.

## Reference evidence

- Installed ApollyonVR Oculus Tray Tool 0.87.7 User Guide and 0.87.8 profile schema,
  read locally on 27 September 2026. No OTT implementation code was copied.
- Meta Debug Tool: https://developers.meta.com/horizon/documentation/native/pc/dg-debug-tool/
- Windows MMDevice API: https://learn.microsoft.com/en-us/windows/win32/coreaudio/mmdevice-api
- Supplemental Link registry observations, checked against names in the installed
  Meta binary: https://github.com/Eliminater74/MetaQuestTrayTool/blob/main/docs/ODT-REGISTRY.md
  Those observations establish persisted settings, not active encoder behaviour.
