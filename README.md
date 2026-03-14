> Automatically tracks [GUI.for.SingBox](https://github.com/GUI-for-Cores/GUI.for.SingBox) upstream releases, builds daily and publishes as a ready-to-use pacman repository via GitHub Pages.

## Usage

Add to the end of `/etc/pacman.conf`:

```ini
[gui-for-singbox]
SigLevel = Optional TrustAll
Server = https://<your-username>.github.io/<repo-name>/x86_64
```

Then install:

```bash
sudo pacman -Sy
sudo pacman -S gui-for-singbox
```

## How to fork

1. Fork this repository
2. Go to Settings → Pages, set Source to **gh-pages** branch
3. Go to Settings → Actions → General, set Workflow permissions to **Read and write**
4. Manually trigger the workflow: Actions → Build & Publish Arch Repo → Run workflow
5. Once the build completes, verify at `https://<your-username>.github.io/<repo-name>/`

## How it works

```
Every day at UTC 06:00
    ↓
Fetch latest upstream version via GitHub API
    ↓
Compare with version.txt — skip if unchanged
    ↓
In an Arch Linux container: update PKGBUILD, run updpkgsums, makepkg
    ↓
Generate pacman database with repo-add
    ↓
Deploy to gh-pages, keeping only the latest package
```
