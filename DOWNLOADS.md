# Download statistics

GitHub records a download_count for each release asset. VR Pit Crew does not install download tracking or analytics on users' PCs.

## Current v0.4.2 release

The current public preview is [VR Pit Crew v0.4.2](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/tag/v0.4.2).

| Asset | SHA-256 | Downloads |
|---|---|---:|
| VR-Pit-Crew-0.4.2-Setup-x64.exe | 458563759818ed13ed6beba8a87a640fde08aebf812c293fbefa1d6836fe1a67 | 0 |
| VR-Pit-Crew-0.4.2-Windows-x64.zip | 78bc79d0e18aeae527335805ed5b9d2ef562e288a4c06faedcdbc89a7d387553 | 0 |
| SHA256SUMS-0.4.2.txt | 565d2d4a88942412ce08e2a41504968fd3e166ce25c68b6188598577ea9863f9 | 0 |
| VR-Pit-Crew-0.4.2-Windows-x64.sha256 | 14e747fa40f716eb6d98f5d1c4039cabdd0e8898a44fe295b0839feef23c9f84 | 0 |

The installer and ZIP hashes above match the built 0.4.2 package. GitHub's automatic Source code archives are not application downloads.

[Live v0.4.2 release metadata and asset counts](https://api.github.com/repos/neil9bailey/VR-Pit-Crew-Downloads/releases/tags/v0.4.2)

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
