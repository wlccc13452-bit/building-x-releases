# building-x-releases

Public **GitHub Releases** bucket for install packages (no source trees).

Private product repos keep source private; their GitHub Actions workflows upload
binaries / installers here via `gh release` and secret `RELEASES_REPO_TOKEN`.

| | |
|--|--|
| GitHub | https://github.com/wlccc13452-bit/building-x-releases |
| Releases | https://github.com/wlccc13452-bit/building-x-releases/releases |
| Checkout | `building-x/building-x-releases/` (git submodule of private `building-x`) |

Do **not** commit large binaries to `main` unless intentional — prefer
[Releases](https://github.com/wlccc13452-bit/building-x-releases/releases).

---

## Publisher projects

Local clones (examples):

| Project | Path |
|---------|------|
| building-x | `ifc_projects/building-x` (or vinchi-hub submodule) |
| vizion_ai | `ifc_projects/vizion_ai` |
| vinchi-hub | `D:\playgrounds\vinchi-hub` |

Each publisher repo needs Actions secret **`RELEASES_REPO_TOKEN`** — a PAT with
`contents:write` on this public repo.

---

## What is / is not published

**Published here:** install-only artifacts (ZIPs, VSIX, wheels, NSIS installers).

**Not published here:**

- Product source trees / sdists (`*.tar.gz`)
- `building-x` **Register2026** installer (stays on private `building-x` Releases)
- Pure `vizion-sdk` / `vizion-runtime` source wheels (replaced by Nuitka binaries)

---

## How publish works

```text
private repo CI (Windows / Linux as needed)
  → build install packages
  → gh release create|upload --repo wlccc13452-bit/building-x-releases
```

Details live in each source repo (not duplicated here):

- building-x: `.github/RELEASES.md`
- vizion_ai: `README.md` → “Build installation packages” / Package workflow
- vinchi-hub: `.github/workflows/vinchi-hub-protected-release.yml`

---

## Local (submodule)

```bat
cd building-x-releases
git pull
```

Parent (`building-x`):

```bat
git submodule update --init building-x-releases
```
