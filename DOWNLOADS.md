# Download statistics

GitHub automatically records a `download_count` for every uploaded release asset. There is no tracking code or analytics agent installed on users' PCs.

The README badge shows downloads of `VR-Pit-Crew-0.3.1-Setup-x64.exe` only. GitHub also provides separate counts for the portable ZIP and checksum file. These counts include repeat and validation downloads; they are not unique users or successful installations. Badges can be cached and update after a delay.

View the [public release metadata](https://api.github.com/repos/neil9bailey/VR-Pit-Crew-Downloads/releases/tags/v0.3.1). Under `assets`, each file has a `name` and `download_count`.

For the publisher, this optional PowerShell command lists all published release assets:

```powershell
$releases = Invoke-RestMethod 'https://api.github.com/repos/neil9bailey/VR-Pit-Crew-Downloads/releases?per_page=100'
$releases | ForEach-Object { $_.assets } | Select-Object name, download_count, browser_download_url
```

Use versioned assets and retain old releases. Deleting an asset also deletes its associated count; uploading a replacement starts a new count. GitHub counts downloads of release assets, not downloads from a Discord attachment or another file host.

Reference: [GitHub release-asset API](https://docs.github.com/en/rest/releases/assets).
