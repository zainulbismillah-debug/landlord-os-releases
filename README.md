# Landlord OS — releases

This repository holds two things and nothing else:

- **`latest.json`** — the update manifest. Landlord OS reads this file to find
  out whether a newer version exists.
- **Releases** — the Windows installer for each published version, attached to
  a tag of the form `v1.0.1`.

There is no source code here.

## Installing Landlord OS

Download the newest installer from the
[Releases](../../releases/latest) page and run it.

Windows will warn that the publisher is unknown, because the installer is not
signed with a paid certificate. Choose **More info**, then **Run anyway**.

## Updating

Open Landlord OS and go to **Settings → Version and updates → Check now**. It
will tell you whether a newer version exists, show what changed, and download
it for you. The download is checked against the checksum published in
`latest.json` before it is offered.

Nothing is ever installed automatically.

## Your records

Landlord OS keeps everything on your own computer, at
`%APPDATA%\Landlord OS\data`. Installing an update replaces the application
only — your properties, tenants, rent history, documents, settings and backups
are untouched.

Before installing an update, Landlord OS saves a complete copy of your records
and documents. If anything goes wrong, that copy is in your backups folder.

## Verifying a download by hand

Each release includes a `.sha256` file. To check a download yourself:

```powershell
certutil -hashfile LandlordOS-Setup-1.0.1.exe SHA256
```

The result should match the checksum in `latest.json`.
