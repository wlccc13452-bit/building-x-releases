# building-x-releases

Public Windows installers for **EPAD** / **ReportViewer** (ZIP + SHA256).

| | |
|--|--|
| GitHub | https://github.com/wlccc13452-bit/building-x-releases |
| Source (private) | https://github.com/wlccc13452-bit/building-x |
| Parent checkout | `building-x/building-x-releases/` (git submodule) |

Installers are published as **GitHub Releases** by the private repo workflow
`.github/workflows/release-windows.yml` (Nuitka + PyInstaller via `epbuild`).

Do **not** commit large ZIP binaries to `main` unless intentional — prefer
[Releases](https://github.com/wlccc13452-bit/building-x-releases/releases).

## Local

```bat
cd building-x-releases
git pull
```

Parent: `git submodule update --init building-x-releases`
