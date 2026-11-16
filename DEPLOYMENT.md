# Vercel Deployment Guide — Envora Flexi

This project is pre-configured and ready for 1-click deployment on **Vercel**.

---

## Method 1: Instant Deployment via Vercel CLI (Recommended)

Since the `vercel` CLI is already installed on your Mac, you can deploy directly from your terminal:

1. Open your terminal in this project directory:
   ```bash
   cd /Users/sanyamgolechha/Documents/Sanyam/envora-flexi
   ```

2. Run the deployment command:
   ```bash
   vercel
   ```
   *(If prompted, log in with your email or GitHub/GitLab account).*

3. Follow the quick interactive prompts:
   - **Set up and deploy?** `Y`
   - **Which scope do you want to deploy to?** *(Select your Vercel account/team)*
   - **Link to existing project?** `N`
   - **What's your project's name?** `envora-flexi` (or press Enter)
   - **In which directory is your code located?** `./` (press Enter)
   - **Want to modify these settings?** `N` (Vercel will automatically detect `vercel.json` and static files)

4. Once the preview URL looks good, deploy to production:
   ```bash
   vercel --prod
   ```

---

## Method 2: Continuous Deployment via GitHub

If you prefer automatic deployments whenever you make changes:

1. Initialize Git and commit:
   ```bash
   git init
   git add .
   git commit -m "feat: Envora Flexi website ready for production"
   ```

2. Create a new repository on GitHub (e.g. `envora-flexi`) and push:
   ```bash
   git remote add origin https://github.com/<your-username>/envora-flexi.git
   git branch -M main
   git push -u origin main
   ```

3. Go to [vercel.com/new](https://vercel.com/new):
   - Click **Import** next to your `envora-flexi` repository.
   - Framework Preset: **Other** (Zero Configuration).
   - Click **Deploy**.

Every time you commit and push to `main`, Vercel will automatically redeploy the site.

---

## Pre-Configured Files

- **`vercel.json`**:
  - `cleanUrls: true` (strips `.html` extensions automatically).
  - Security headers (`X-Content-Type-Options`, `X-Frame-Options`, `X-XSS-Protection`, `Referrer-Policy`).
- **`.gitignore`**:
  - Excludes local operating system artifacts (`.DS_Store`) and Vercel build state (`.vercel`).
- **`package.json`**:
  - Project metadata, scripts (`npm run dev`), and production build signals.
- **`index.html`**:
  - Fully self-contained static site with inline vector textures, Open Graph (OG) cards for WhatsApp/social sharing, and interactive simulators.

---

## Custom Domain Setup

Once deployed on Vercel:
1. Open your project on the [Vercel Dashboard](https://vercel.com/dashboard).
2. Go to **Settings > Domains**.
3. Enter your custom domain (e.g., `envoraflexi.com` or `www.envoraflexi.com`).
4. Follow the DNS instructions (add the `A` record `76.76.21.21` or `CNAME` `cname.vercel-dns.com` at your domain registrar like GoDaddy, Namecheap, or Cloudflare).
5. Vercel automatically issues and renews a free SSL certificate.
