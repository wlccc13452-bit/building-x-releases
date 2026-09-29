# building-x-releases

Public Windows install packages — download from
[Releases](https://github.com/wlccc13452-bit/building-x-releases/releases).

## 1. EPAD Series

| Package | Files | Purpose |
|---------|--------|---------|
| **EPAD** | `Epad-*-win64.zip`, `Epad-*-win64-Setup.exe` | Structural engineering desktop (Building-X). Prefer **Setup.exe**. |
| **Report Orchestrator** | `ReportOrchestrator-*-win64.zip`, `ReportOrchestrator-*-win64-Setup.exe` | Standalone report UI . Prefer **Setup.exe**. |
| **ReportViewer** | `ReportViewer-*-win64.zip` | Companion report viewer (when shipped). |
| **epad-report-preview** | `epad-report-preview-*.vsix` | VS Code / Cursor preview extension. |

### Install

1. Download the latest assets from [Releases](https://github.com/wlccc13452-bit/building-x-releases/releases).
2. Prefer `*-Setup.exe` (Inno installer). For ZIP: extract and run the `.exe` from the folder.
3. Optional: install `epad-report-preview-*.vsix` via VS Code / Cursor → Extensions → Install from VSIX.

### Verify

- Optional: check digests against `SHA256SUMS*` in the same release.
- If the model viewer stays on “Loading model…”, confirm WebView2 Runtime is installed and the package includes `WebView2Loader.dll` beside the app.

## 2. Vinchi Hub

| Package | Files | Purpose |
|---------|--------|---------|
| **Vinchi Morph** | `VinchiMorph-*-win64.zip`, `VinchiMorph-*-win64-Setup.exe`, `latest-morph.yml` | Independent Morph desktop . Collaborates with Flow via hub-bridge.v1. |
| **Vinchi Flow** | `VinchiFlow-*-win64.zip`, `VinchiFlow-*-win64-Setup.exe`, `latest-flow.yml` | Independent Flow desktop . |
| **Sync Hub** | `SyncHub-*-win64.zip`, `SyncHub-*-win64-Setup.exe` | Device sync center + dashboard. |
| **Vinchi Hub (legacy)** | `Vinchi Hub-*.exe` | Electron all-in-one — **retiring**; prefer Morph + Flow Setup.exe. |

### Install

1. Download Morph and Flow `*-Setup.exe` from [Releases](https://github.com/wlccc13452-bit/building-x-releases/releases) (or ZIP if you prefer a portable layout).
2. Run both Setup installers. Default Flow path: `%LOCALAPPDATA%\Programs\VinchiFlow\VinchiFlow.exe`.
3. Optional: install Sync Hub the same way. Skip legacy `Vinchi Hub-*.exe` unless you need the old Electron shell.

### Use Morph ↔ Flow

1. Start **Vinchi Morph** and **Vinchi Flow** (both must be installed for collaboration).
2. In Morph, use **To Flow** to launch/activate Flow, sync theme, and hand off via `hub-bridge.v1` (loopback only).
3. If Flow is missing, Morph opens the releases page so you can install it.
4. `latest-morph.yml` / `latest-flow.yml` are updater metadata — keep them with the Setup artifacts when using auto-update feeds.

## Checksums

| Package | Files | Purpose |
|---------|--------|---------|
| **Checksums** | `SHA256SUMS*` | SHA-256 digests. |

Private source stays in product repos. This repo `main` is README-only.
