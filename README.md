# SmartSure Website

Responsive static landing/download website for SmartSure.

## Publish with GitHub Pages (Android / Termux)

1. Create a new **public** GitHub repository named `smartsure-website`.
2. In Termux, place this folder somewhere accessible or extract the ZIP in `~/storage/shared/Download`.
3. Copy `index.html` into the repository root.
4. Upload `index.html` using GitHub in Chrome, or use Git from Termux:

```bash
pkg update
pkg install git
termux-setup-storage
mkdir -p ~/smartsure-website
cd ~/smartsure-website
# Copy index.html into this folder, then:
git init
git branch -M main
git add index.html
git commit -m "Add SmartSure download website"
git remote add origin https://github.com/YOUR_USERNAME/smartsure-website.git
git push -u origin main
```

If Git asks for a password, use a GitHub Personal Access Token instead of your account password. Never share the token.

5. On GitHub repository: Settings → Pages → Source `Deploy from a branch` → Branch `main` → Folder `/(root)` → Save.
6. Wait for the Pages URL, typically `https://YOUR_USERNAME.github.io/smartsure-website/`.

## Configure real downloads later

In `index.html`, find the `data-placeholder` buttons in the Download section and replace them with real URLs:
- `apk`: link to your successfully built APK (prefer a GitHub Release or trusted hosting)
- `play`: official Google Play listing URL after publication
- `ios`: official App Store listing after approval
- `web`: deployed SmartSure web app URL

The current buttons intentionally show "coming soon" and do not pretend that the app is already available on each platform.

## Security
- Do not upload `.env`, Firebase private credentials, signing keystores, passwords, tokens or API secrets.
- GitHub Pages is static hosting. It does not create an APK or convert an Expo app into a web app.
