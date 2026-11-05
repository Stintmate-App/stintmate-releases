# Stintmate releases

Stintmate is a free app for sim racing on Windows: it records your sessions and laps, analyses them,
and gives you a race engineer you talk to over the radio while you drive. More at
[www.stintmate.app](https://www.stintmate.app).

This repository holds Stintmate's releases only: no code.

## Download

The latest version, always at the same link:
[Stintmate-setup.exe](https://github.com/Stintmate-App/stintmate-releases/releases/latest/download/Stintmate-setup.exe)

Every release is titled `Stintmate vX.Y.Z` and carries:

| File | What |
|---|---|
| `Stintmate-X.Y.Z-setup.exe` | the installer of that version |
| `Stintmate-setup.exe` | the same installer under a name that never changes, for the link above |
| `*.sha256` | the SHA-256 of each installer |
| `release.json`, `release.json.sig` | the release manifest and its signature, which Stintmate checks before it installs an update |
| `connectors.json` | the catalog of the official connectors (see below) |
| `THIRD-PARTY-NOTICES.txt` | the licences of every component inside the installer |
| `stintmate-speech-X.Y.Z-source.zip` | the complete source of Stintmate Speech, the speech engine inside the installer (GPL-3.0-or-later) |

The installer runs per user: it needs no administrator rights. Once installed, Stintmate looks for a
new version once a day and offers it; you can turn that off in Settings.

## Check the download

In PowerShell, in the folder you downloaded to:

```powershell
Get-FileHash .\Stintmate-setup.exe -Algorithm SHA256
```

The hash must equal the one in `Stintmate-setup.exe.sha256` of the same release.

## Windows warnings

The installer is not code-signed yet.

- **SmartScreen** may show "Windows protected your PC" with "Unknown publisher". Choose **More info**
  if Windows asks, then **Run anyway**. The warning fades as more people download the same version.
- **Smart App Control:** when it is on, Windows blocks programs that are not signed, and the
  installer cannot run. Its state is in Windows Security › App & browser control › Smart App Control.

## Connectors

Stintmate reads each game through a connector. The official connectors are installed from Stintmate
itself (Settings › Apps), using the `connectors.json` of the latest release. Each connector's setup
is published by that connector's own repository, for example the
[AMS2 connector](https://github.com/Stintmate-App/ams2-connector/releases).

## Licence

Stintmate is free to use and to share as the unmodified installer; it may not be sold. The full
terms, the same ones the installer shows, are in [LICENSE.txt](LICENSE.txt). The parts under their
own licences are listed in `THIRD-PARTY-NOTICES.txt` in the install folder.
