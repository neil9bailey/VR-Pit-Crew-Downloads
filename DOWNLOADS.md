# Download statistics

GitHub records a download_count for each release asset. VR Pit Crew does not install download tracking or analytics on users' PCs.

## Current v0.4.4 release

The current public preview is [VR Pit Crew v0.4.4](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/tag/v0.4.4).

| Asset | SHA-256 | Downloads |
|---|---|---:|
| VR-Pit-Crew-0.4.4-Setup-x64.exe | b2af2cc7808fe038349fc430d27f3ea944d19e8aded5087db4f5cbe9aa0294f0 | 0 |
| VR-Pit-Crew-0.4.4-Windows-x64.zip | 5f543d48557930f48288440d60d0b5a22a4a565abbbda96dfb814ecc2d9a4547 | 0 |
| SHA256SUMS-0.4.4.txt | 09d7f2a518c6f4fbd71308a6f2fa5a23f033ab51188264240e716665805480ba | 0 |
| VR-Pit-Crew-0.4.4-Windows-x64.sha256 | 28c7240980ecd83733d1af04f7f281f75f3c22078fd5d25da1039bac539992fa | 0 |

The installer and ZIP hashes above match the built 0.4.4 package. GitHub's automatic Source code archives are not application downloads.

[Live v0.4.4 release metadata and asset counts](https://api.github.com/repos/neil9bailey/VR-Pit-Crew-Downloads/releases/tags/v0.4.4)

## Historical counters

Earlier releases and archived assets retain their own counters. These are
historical snapshots, not live totals; archived assets may still receive later
downloads. Repeat and verification downloads count, so these are not unique users,
successful installations, usage or payments.

For total installer downloads across builds, sum installer EXE counts, including
archived installers. Count portable ZIP downloads separately and exclude checksum
files. Badges can be cached.

[Live v0.4.3 release metadata and asset counts](https://api.github.com/repos/neil9bailey/VR-Pit-Crew-Downloads/releases/tags/v0.4.3) ·
[Live v0.4.2 release metadata and asset counts](https://api.github.com/repos/neil9bailey/VR-Pit-Crew-Downloads/releases/tags/v0.4.2) ·
[Live v0.4.1 release metadata and asset counts](https://api.github.com/repos/neil9bailey/VR-Pit-Crew-Downloads/releases/tags/v0.4.1)

    $releases = Invoke-RestMethod 'https://api.github.com/repos/neil9bailey/VR-Pit-Crew-Downloads/releases?per_page=100'
    $releases | ForEach-Object { $_.assets } | Select-Object name, download_count, browser_download_url

Reference: [GitHub release-asset API](https://docs.github.com/en/rest/releases/assets).
