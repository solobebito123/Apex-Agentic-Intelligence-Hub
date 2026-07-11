# AAIH Portfolio Website — Hosting Guide

## Overview

This is the official one-page portfolio website for **Apex Agentic & Intelligence Hub (AAIH)**, built with HTML5 and Tailwind CSS (via CDN). No build step is required — just upload the single `index.html` file to any static host.

---

## 🚀 Hosting on GitHub Pages (Recommended — Free)

### Step 1 — Create a GitHub Repository

1. Go to [https://github.com/new](https://github.com/new)
2. Name your repository: `aaih-website` (or any name you prefer)
3. Set visibility to **Public** (required for the free GitHub Pages tier)
4. Click **Create repository**

### Step 2 — Upload Your Files

**Option A — Via the GitHub Web UI (No Terminal Needed)**

1. Inside your new repository, click **Add file → Upload files**
2. Drag and drop `index.html` into the upload area
3. Scroll down, add a commit message like `Initial site launch`
4. Click **Commit changes**

**Option B — Via Git CLI**

```bash
# Clone your new empty repo
git clone https://github.com/YOUR_USERNAME/aaih-website.git
cd aaih-website

# Copy the site file in
cp /path/to/index.html .

# Commit and push
git add index.html
git commit -m "Initial AAIH site launch"
git push origin main
```

### Step 3 — Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** (top navigation)
3. Scroll down to the **Pages** section in the left sidebar
4. Under **Build and deployment → Source**, select **Deploy from a branch**
5. Under **Branch**, choose `main` and folder `/ (root)`
6. Click **Save**

### Step 4 — Access Your Live Site

- GitHub Pages will build in ~1–2 minutes
- Your site will be live at:
  ```
  https://YOUR_USERNAME.github.io/aaih-website/
  ```
- GitHub will show the live URL in **Settings → Pages** once active

---

## 🌐 Custom Domain (Optional)

To use a custom domain like `aaih.ai`:

1. In **Settings → Pages → Custom domain**, enter your domain (e.g., `aaih.ai`)
2. Click Save — GitHub will add a `CNAME` file to your repo
3. In your DNS provider (Namecheap, Cloudflare, GoDaddy, etc.), add these records:

   | Type  | Name | Value                      |
   |-------|------|----------------------------|
   | A     | @    | 185.199.108.153             |
   | A     | @    | 185.199.109.153             |
   | A     | @    | 185.199.110.153             |
   | A     | @    | 185.199.111.153             |
   | CNAME | www  | YOUR_USERNAME.github.io.    |

4. Enable **Enforce HTTPS** in the Pages settings after DNS propagates (~24–48 hrs)

---

## ✏️ Customising Before Launch

Before publishing, update these items in `index.html`:

| What to change | Where to find it |
|---|---|
| Calendly booking link | `href="https://calendly.com/YOUR_CALENDLY_LINK"` |
| Contact email | `href="mailto:hello@aaih.ai"` |
| Website URL | `href="https://aaih.ai"` |
| Social media links | `href="#"` on LinkedIn, Twitter/X, GitHub icons |
| Contact form submission | `handleSubmit()` function — replace the `setTimeout` with your real endpoint (Formspree, EmailJS, etc.) |

### Setting Up a Free Contact Form (Formspree)

1. Sign up at [https://formspree.io](https://formspree.io) — free tier supports 50 submissions/month
2. Create a new form and copy your endpoint URL
3. In `index.html`, update the `<form>` tag:
   ```html
   <form id="contact-form" action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
   ```
4. Remove the `onsubmit="handleSubmit(event)"` attribute if using native Formspree redirect

---

## 🛠 Other Static Hosting Options

| Platform | Free Tier | Notes |
|---|---|---|
| **Netlify** | Yes | Drag-and-drop deploy at app.netlify.com → Sites → Add new site |
| **Vercel** | Yes | `npx vercel --prod` or GitHub integration |
| **Cloudflare Pages** | Yes | Best performance globally via CDN |
| **AWS S3 + CloudFront** | ~$0.50/mo | Enterprise option |
| **Firebase Hosting** | Yes | `firebase deploy` after setup |

---

## 📁 File Structure

```
AAIH-Website/
├── index.html          ← The entire website (all-in-one)
└── README_WEBSITE.md   ← This file
```

The site uses **Tailwind CSS via CDN** — no `node_modules`, no build tools, no dependencies to install. Just `index.html`.

---

## 📞 Support

Built by the AAIH team. For questions, reach out at [hello@aaih.ai](mailto:hello@aaih.ai).
