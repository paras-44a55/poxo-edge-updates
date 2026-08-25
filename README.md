# poxo-edge-updates

Update manifest and release packages for Poxo PV Track EdgeNode. **No source code lives here.**

`version.json` (on `main`, fetched anonymously via raw.githubusercontent.com) is the manifest every
EdgeNode install polls. Its URL must never change; only its contents change on each release.

Published by `installer/publish_update.ps1` in the main EdgeNode repo — do not edit `version.json`
by hand except to disable an update (set `"available": false`).

## Schema

```json
{
  "available": true,
  "version": "1.0.7",
  "downloadUrl": "https://github.com/<owner>/poxo-edge-updates/releases/download/v1.0.7/update-1.0.7.zip",
  "sha256": "<sha256 of the exact zip attached to the release>",
  "releaseNotes": "What changed."
}
```

`available: false` (or the field missing) means no update is offered; every EdgeNode reports
itself up to date.
