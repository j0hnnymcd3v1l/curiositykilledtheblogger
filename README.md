# Curiosity Killed the Blogger

Dark editorial writing site — fiction, flash fiction, and essays by Miguel Coias.

Built with [Hugo](https://gohugo.io/) and deployed via GitHub Pages.

---

## Setup (one-time)

### 1. Install Hugo

```bash
# macOS
brew install hugo

# Verify
hugo version
```

### 2. Create the GitHub repo

1. Go to github.com → New repository
2. Name it `curiositykilledtheblogger` (or whatever you like)
3. Set it to **Public**
4. Don't add a README (we already have one)

### 3. Push this project

```bash
cd cktb
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/curiositykilledtheblogger.git
git push -u origin main
```

### 4. Enable GitHub Pages

1. Go to your repo → **Settings** → **Pages**
2. Under "Source", select **GitHub Actions**
3. The workflow will auto-run on push

### 5. Connect your domain

1. In the same Pages settings, add `curiositykilledtheblogger.com` as custom domain
2. At your domain registrar, add these DNS records:
   - `A` record: `185.199.108.153`
   - `A` record: `185.199.109.153`
   - `A` record: `185.199.110.153`
   - `A` record: `185.199.111.153`
   - `CNAME` for `www`: `YOUR_USERNAME.github.io`
3. Check "Enforce HTTPS" once DNS propagates

---

## Writing workflow (iA Writer)

### Adding a new post

1. Open the `content/posts/` folder in iA Writer as a Library location
2. Create a new file, e.g. `my-new-story.md`
3. Add front matter at the top:

```yaml
---
title: "My New Story"
date: 2026-04-24
categories: ["Fiction"]
excerpt: "The opening line or two that appears on the homepage..."
words: 850
---
```

4. Write your piece below the `---`
5. Save

### Publishing

```bash
cd cktb
git add .
git commit -m "New post: My New Story"
git push
```

The site rebuilds automatically in ~30 seconds.

### Categories

Use any of these in the front matter (or create new ones):
- `Fiction`
- `Flash Fiction`
- `Non-Fiction`

### Tips

- **Drafts**: Add `draft: true` to front matter — Hugo won't publish it
- **Images**: Put them in `static/images/` and reference as `![alt](/images/photo.jpg)`
- **Preview locally**: Run `hugo server` and visit `http://localhost:1313`
- **Word count**: Hugo can auto-calculate, but the manual `words` field gives you control over what shows on the homepage

---

## Project structure

```
cktb/
├── content/
│   └── posts/          ← Your writing lives here
│       ├── why-i-write.md
│       ├── premonition.md
│       └── ...
├── themes/cktb/
│   ├── layouts/        ← Page templates
│   └── static/css/     ← Stylesheet
├── hugo.toml           ← Site config
└── .github/workflows/  ← Auto-deploy on push
```
