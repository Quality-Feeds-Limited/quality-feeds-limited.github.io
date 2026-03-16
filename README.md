# QAL ERP Documentation Site

Built with [Jekyll](https://jekyllrb.com/) and the [Just the Docs](https://github.com/just-the-docs/just-the-docs) theme, deployed via GitHub Pages.

---

## 🚀 How to Publish to GitHub Pages

### Step 1 — Create a GitHub Repository

1. Go to [https://github.com/new](https://github.com/new)
2. Name the repository: `qal-erp-docs`
3. Set it to **Public**
4. Do **NOT** initialise with a README (you already have one)
5. Click **Create repository**

---

### Step 2 — Push This Project to GitHub

Open a terminal in this folder and run:

```bash
git init
git add .
git commit -m "Initial commit — QAL ERP documentation"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/qal-erp-docs.git
git push -u origin main
```

Replace `YOUR-USERNAME` with your actual GitHub username.

---

### Step 3 — Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** → **Pages** (left sidebar)
3. Under **Source**, select **GitHub Actions**
4. Click **Save**

GitHub will automatically trigger the deploy workflow on your next push.

---

### Step 4 — Update the Base URL

Open `_config.yml` and update the `baseurl` and `url` fields:

```yaml
baseurl: "/qal-erp-docs"       # your repo name
url: "https://YOUR-USERNAME.github.io"
```

Commit and push the change:

```bash
git add _config.yml
git commit -m "Update base URL for GitHub Pages"
git push
```

---

### Step 5 — View Your Site

After the GitHub Actions workflow completes (usually 1–2 minutes), your site will be live at:

```
https://YOUR-USERNAME.github.io/qal-erp-docs
```

You can monitor the deployment under the **Actions** tab of your repository.

---

## 📁 Project Structure

```
qal-erp-docs/
├── _config.yml                          # Jekyll + Just the Docs configuration
├── Gemfile                              # Ruby dependencies
├── index.md                             # Homepage
├── .gitignore
├── .github/
│   └── workflows/
│       └── deploy.yml                   # GitHub Actions auto-deploy
├── docs/
│   └── accounting/
│       ├── index.md                     # Accounting module overview
│       ├── general-ledger.md
│       ├── chart-of-accounts.md
│       ├── chart-of-accounts-type.md    # ✅ Full documentation
│       ├── voucher-type.md              # ✅ Full documentation
│       └── financial-year.md
└── assets/
    └── images/
        └── accounting/
            ├── coa-list.png
            ├── coa-menu.png
            ├── coa-button.png
            ├── coa-create.png
            ├── coa-edit.png
            ├── vt-list.png
            ├── vt-menu.png
            ├── vt-button.png
            ├── vt-create.png
            └── vt-edit.png
```

---

## ✏️ Adding New Documentation Pages

To add a new module page (e.g., "Financial Year"):

1. Create a new `.md` file in `docs/accounting/`
2. Add the following front matter at the top:

```yaml
---
layout: default
title: Financial Year
parent: Accounting
nav_order: 5
---
```

3. Write your content in Markdown below.
4. Commit and push — the site rebuilds automatically.

---

## 🖼️ Adding Screenshots

1. Place your `.png` images in `assets/images/accounting/`
2. Reference them in Markdown:

```markdown
![Alt text]({{ site.baseurl }}/assets/images/accounting/your-image.png)
*Figure caption here*
```

---

## 🏠 Running Locally (Optional)

To preview the site on your machine before pushing:

```bash
gem install bundler
bundle install
bundle exec jekyll serve
```

Then open `http://localhost:4000/qal-erp-docs` in your browser.
