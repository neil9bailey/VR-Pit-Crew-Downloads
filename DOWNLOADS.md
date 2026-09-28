# Download statistics

GitHub records a download_count for each release asset. VR Pit Crew does not install download tracking or analytics on users' PCs.

## Current v0.4.1 release

The current public preview is [VR Pit Crew v0.4.1](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/tag/v0.4.1).

| Asset | GitHub asset ID | SHA-256 | Downloads |
|---|---:|---|---:|
| VR-Pit-Crew-0.4.1-Setup-x64.exe | 595637429 | 28d320e75d49e285aad2c7b8736ade935ffec14ddb997096649ccef500aa4ea4 | 0 |
| VR-Pit-Crew-0.4.1-Windows-x64.zip | 595637020 | dd0e0955b55e5409bcf64ac6091f5bf6dacefb9a92cac1cb01c67acd9a3e9add | 0 |
| SHA256SUMS-0.4.1.txt | 595637417 | 790f6efbc71fd0be42d75ce845c9f460391739887ece24d7b5d7119eea4bb830 | 0 |
| VR-Pit-Crew-0.4.1-Windows-x64.sha256 | 595636991 | b02d33cca1046083bfc1cb21b5eff03805b3eefc21008d36e216b2f0b363d2d1 | 0 |

The installer and ZIP hashes above match the built 0.4.1 package. GitHub's automatic Source code archives are not application downloads.

## Historical counters

Earlier releases and archived assets retain their own counters. These are
historical snapshots, not live totals; archived assets may still receive later
downloads. Repeat and verification downloads count, so these are not unique users,
successful installations, usage or payments.

For total installer downloads across builds, sum installer EXE counts, including
archived installers. Count portable ZIP downloads separately and exclude checksum
files. Badges can be cached.

[Live v0.4.1 release metadata and asset counts](https://api.github.com/repos/neil9bailey/VR-Pit-Crew-Downloads/releases/tags/v0.4.1)

    $releases = Invoke-RestMethod 'https://api.github.com/repos/neil9bailey/VR-Pit-Crew-Downloads/releases?per_page=100'
    $releases | ForEach-Object { $_.assets } | Select-Object name, download_count, browser_download_url

Reference: [GitHub release-asset API](https://docs.github.com/en/rest/releases/assets).
