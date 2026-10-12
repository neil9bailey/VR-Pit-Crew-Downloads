# Download statistics

GitHub records a download_count for each release asset. VR Pit Crew does not install download tracking or analytics on users' PCs.

## Current v0.4.5 release

The current public preview is [VR Pit Crew v0.4.5](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/tag/v0.4.5).

| Asset | SHA-256 | Downloads |
|---|---|---:|
| VR-Pit-Crew-0.4.5-Setup-x64.exe | 8c657d426e3e7dc94a83a0f9db4b9649cef741e503650d1bc663bbf523f6deab | 0 |
| VR-Pit-Crew-0.4.5-Windows-x64.zip | edbeb2b2c5656a4a10442fb39667475f2b8d45d393f8208526baf9c8f71e23ed | 0 |
| SHA256SUMS-0.4.5.txt | 5ecbe7910ab3ef3b8b97a23327b2560b6258f75c1ce89bb404cd8ca5958f2b9e | 0 |
| VR-Pit-Crew-0.4.5-Windows-x64.sha256 | 3a4c67f4f9c8f2b4c65541c6614eb74a04d2f2e8c28b946dc91a1f83d38909a9 | 0 |

The installer and ZIP hashes above match the built 0.4.5 package. GitHub's automatic Source code archives are not application downloads.

[Live v0.4.5 release metadata and asset counts](https://api.github.com/repos/neil9bailey/VR-Pit-Crew-Downloads/releases/tags/v0.4.5)

## Historical counters

Earlier releases and archived assets retain their own counters. These are
historical snapshots, not live totals; archived assets may still receive later
downloads. Repeat and verification downloads count, so these are not unique users,
successful installations, usage or payments.

For total installer downloads across builds, sum installer EXE counts, including
archived installers. Count portable ZIP downloads separately and exclude checksum
files. Badges can be cached.

[Live v0.4.4 release metadata and asset counts](https://api.github.com/repos/neil9bailey/VR-Pit-Crew-Downloads/releases/tags/v0.4.4) ·
[Live v0.4.3 release metadata and asset counts](https://api.github.com/repos/neil9bailey/VR-Pit-Crew-Downloads/releases/tags/v0.4.3) ·
[Live v0.4.2 release metadata and asset counts](https://api.github.com/repos/neil9bailey/VR-Pit-Crew-Downloads/releases/tags/v0.4.2) ·
[Live v0.4.1 release metadata and asset counts](https://api.github.com/repos/neil9bailey/VR-Pit-Crew-Downloads/releases/tags/v0.4.1)

    $releases = Invoke-RestMethod 'https://api.github.com/repos/neil9bailey/VR-Pit-Crew-Downloads/releases?per_page=100'
    $releases | ForEach-Object { $_.assets } | Select-Object name, download_count, browser_download_url

Reference: [GitHub release-asset API](https://docs.github.com/en/rest/releases/assets).
