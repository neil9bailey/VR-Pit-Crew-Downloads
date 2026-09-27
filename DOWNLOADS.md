# Download statistics

GitHub records a `download_count` for each release asset. VR Pit Crew does not install download tracking or analytics on users' PCs.

## Current downloads and existing links

On 27 September 2026 the existing shared installer and ZIP URLs were updated to **application build 0.3.2**. Their `v0.3.1` route and filenames are retained for link compatibility. The installer and application show version 0.3.2.

The README badge counts the **current installer asset** at that shared URL. The original 0.3.1 assets were renamed with `ORIGINAL`, preserving their asset IDs and recorded counts rather than deleting them. New build assets have their own counters.

| Asset | GitHub asset ID | Count recorded before replacement |
|---|---:|---:|
| Original 0.3.1 installer, now `VR-Pit-Crew-0.3.1-ORIGINAL-Setup-x64.exe` | 588123882 | 1 |
| Original 0.3.1 ZIP, now `VR-Pit-Crew-0.3.1-ORIGINAL-Windows-x64.zip` | 588124012 | 0 |
| Original checksum file | 588124200 | 0 |

These are historical snapshots, not live totals. Original assets may still receive later downloads. The original checksum file is retained unchanged and lists its original filenames; the current `SHA256SUMS.txt` also lists the archived binaries under their new ORIGINAL names.

For total installer downloads across builds, sum installer EXE counts, including archived installers. Count portable ZIP downloads separately and exclude checksum files. Repeat and verification downloads count, so these are not unique users, successful installations, usage or payments. Badges can be cached.

[Live release metadata and asset counts](https://api.github.com/repos/neil9bailey/VR-Pit-Crew-Downloads/releases/tags/v0.3.1)

```powershell
$releases = Invoke-RestMethod 'https://api.github.com/repos/neil9bailey/VR-Pit-Crew-Downloads/releases?per_page=100'
$releases | ForEach-Object { $_.assets } | Select-Object name, download_count, browser_download_url
```

Deleting an asset deletes its associated counter. For future updates, archive the old asset by renaming it, then map the tested replacement to the established download filename and update checksums and release notes. Keep the compatibility purpose explicit; do not change the executable's actual version to match an old filename.

Reference: [GitHub release-asset API](https://docs.github.com/en/rest/releases/assets).
