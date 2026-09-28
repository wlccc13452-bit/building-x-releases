# building-x-releases

Public **installer bucket only**. This repository exists so private `building-x`
can publish Windows install packages via GitHub Releases.

| | |
|--|--|
| Releases (installers) | https://github.com/wlccc13452-bit/building-x-releases/releases |

## What belongs here

**Only** GitHub Release **assets** (uploaded by CI `gh release`):

- `Epad-*-win64.zip` / `Epad-*-win64-Setup.exe`
- `ReportOrchestrator-*-win64.zip` / `ReportOrchestrator-*-win64-Setup.exe`
- `ReportViewer-*-win64.zip` (when built)
- `epad-report-preview-*.vsix`
- `SHA256SUMS*`

`main` on this repo should stay a thin README (this file). Do **not** push
installer binaries into git history — put them on **Releases** only.

## How packages arrive

```text
private building-x CI
  → build installers under epad/releases/
  → gh release create|upload --repo wlccc13452-bit/building-x-releases
```

Publisher setup and allow-list: private repo `building-x/.github/RELEASES.md`.

## Local submodule (optional)

```bat
cd building-x
git submodule update --init building-x-releases
cd building-x-releases
git pull
```
