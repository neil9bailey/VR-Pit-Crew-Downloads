# Download statistics

GitHub records a download_count for each release asset. VR Pit Crew does not install download tracking or analytics on users' PCs.

## Current v0.4.3 release

The current public preview is [VR Pit Crew v0.4.3](https://github.com/neil9bailey/VR-Pit-Crew-Downloads/releases/tag/v0.4.3).

| Asset | SHA-256 | Downloads |
|---|---|---:|
| VR-Pit-Crew-0.4.3-Setup-x64.exe | f50b5ada7c4d4276dbed6d09de7a03430d02407f87729f091b093a801ae0c41d | 0 |
| VR-Pit-Crew-0.4.3-Windows-x64.zip | e4fa12f3c3735c8a6409f508d704acd3152519c078207ef4af14d3f4ff967492 | 0 |
| SHA256SUMS-0.4.3.txt | c72607d6f79dc64177390d107f3c15ae421482fdc92ebc237e2c4cd456fad8b8 | 0 |
| VR-Pit-Crew-0.4.3-Windows-x64.sha256 | 6c1d3f310e1b5de4f33ef50652594e197f60dfc14e84bec56843ea7ca315664d | 0 |

The installer and ZIP hashes above match the built 0.4.3 package. GitHub's automatic Source code archives are not application downloads.

[Live v0.4.3 release metadata and asset counts](https://api.github.com/repos/neil9bailey/VR-Pit-Crew-Downloads/releases/tags/v0.4.3)

## Historical counters

Earlier releases and archived assets retain their own counters. These are
historical snapshots, not live totals; archived assets may still receive later
downloads. Repeat and verification downloads count, so these are not unique users,
successful installations, usage or payments.

For total installer downloads across builds, sum installer EXE counts, including
archived installers. Count portable ZIP downloads separately and exclude checksum
files. Badges can be cached.

[Live v0.4.2 release metadata and asset counts](https://api.github.com/repos/neil9bailey/VR-Pit-Crew-Downloads/releases/tags/v0.4.2) ·
[Live v0.4.1 release metadata and asset counts](https://api.github.com/repos/neil9bailey/VR-Pit-Crew-Downloads/releases/tags/v0.4.1)

    $releases = Invoke-RestMethod 'https://api.github.com/repos/neil9bailey/VR-Pit-Crew-Downloads/releases?per_page=100'
    $releases | ForEach-Object { $_.assets } | Select-Object name, download_count, browser_download_url

Reference: [GitHub release-asset API](https://docs.github.com/en/rest/releases/assets).
