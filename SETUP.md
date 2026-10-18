# Publish this GitHub profile README

GitHub shows a profile README only when it lives in a **public repository named exactly `Guntera-ui`** (your username), with `README.md` at the repository root.

## Option A — GitHub CLI (`gh`) on NixOS

1. Download and extract the ZIP from ChatGPT. Enter the extracted `Guntera-ui-profile` folder, the one containing `README.md` and `assets/`.
2. Ensure `gh auth status` works. If not: `gh auth login`.
3. Publish as your public profile repository:

```bash
cd ~/Downloads/Guntera-ui-profile
git init -b main
git add README.md assets/
git commit -m "Create profile README"
gh repo create Guntera-ui --public --source=. --remote=origin --push
```

If the repository already exists, clone it first and copy `README.md` and `assets/` into the clone instead of using `gh repo create`.

## Option B — Browser

1. Create a **public** repository named `Guntera-ui` at https://github.com/new.
2. Upload `README.md` to its root and all SVG files under `assets/`.
3. Visit https://github.com/Guntera-ui — the profile README should appear above the pinned repositories.

## Customize

- Edit descriptions in `README.md` with `vim README.md`.
- The color palette is embedded in the local SVG assets. Its main hues are lavender `#C3A0FF`, pink `#F79BC8`, and cyan `#7AE8F2` against ink `#0A0B16`.
- All project links refer to public repositories checked before packaging.
- GitHub does not let README authors insert arbitrary CSS/JavaScript; layout depends on its Markdown renderer. The local SVGs remain repository assets, not externally hosted widgets.
- The small technology badges come from shields.io. If offline or blocked, the rest of the README still displays.
- The profile repository is independent of your `Nixos` repository, `main`/`hybrid` branches, and `/etc/nixos`. It does not modify sudo rights.

## Editing later

```bash
git clone https://github.com/Guntera-ui/Guntera-ui.git
cd Guntera-ui
vim README.md
git add README.md assets/
git commit -m "Refresh profile"
git push
```
