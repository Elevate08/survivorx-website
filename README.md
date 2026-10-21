# Survivor-X: Astral Forge — Official Landing Page

Official landing page for **Survivor-X: Astral Forge**, an Android native 2D tactical arena survival roguelite developed and published by **Stasis State LLC**.

## 🌐 Custom Subdomain & GitHub Pages Setup

This repository is configured with a `CNAME` file pointing to:
```
survivorx.stasisstate.com
```

### DNS Setup (at your DNS provider, e.g., Cloudflare, Namecheap):
- **Type:** `CNAME`
- **Host / Name:** `survivorx`
- **Target / Value:** `<your-github-username>.github.io`

### GitHub Pages Settings:
1. In this repository, go to **Settings > Pages**.
2. **Build and deployment:** Source: Deploy from branch (`main` / `/root`).
3. **Custom domain:** Ensure `survivorx.stasisstate.com` is entered and check **Enforce HTTPS**.

## 📁 Project Structure

```
.
├── index.html            # Main game showcase landing page
├── styles.css            # Sci-fi / Roguelite dark aesthetic stylesheet
├── CNAME                 # survivorx.stasisstate.com
├── .nojekyll             # Prevents Jekyll processing
├── robots.txt            # Search engine directives
├── sitemap.xml           # XML sitemap
├── assets/               # Production screenshots & 512x512 app icon
└── README.md
```
