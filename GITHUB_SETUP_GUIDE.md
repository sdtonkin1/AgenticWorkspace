# GitHub & GitHub Pages Setup Guide

**Project:** AgenticWorkspace  
**Repository Name:** AgenticWorkspace  
**GitHub Username:** sdtonkin1  
**GitHub Pages Source:** `/docs` folder  

---

## 📋 Complete Setup Checklist

### Step 1: Create the Private GitHub Repository ✓
**Status:** Ready to push

1. Go to [github.com/new](https://github.com/new)
2. Fill in the details:
   - **Repository name:** `AgenticWorkspace`
   - **Description:** "HTML prototype for SharePoint Modern Mockup (SKiLNet v15)"
   - **Visibility:** `Private` ⭐ IMPORTANT
   - **Initialize repository:** Leave unchecked (we already have local git)
3. Click **"Create repository"**

You'll see instructions to push an existing repository. Copy the commands that look like:
```bash
git remote add origin https://github.com/sdtonkin1/AgenticWorkspace.git
git branch -m main
git push -u origin main
```

### Step 2: Add Your HTML Prototype ✓
**Status:** Ready for your HTML file

**Important:** You need to download your SharePoint HTML file and place it in the `docs/` folder.

#### To download from SharePoint:
1. Go to your SharePoint URL: `https://rpo365-my.sharepoint.com/personal/stonkin_rightpoint_com/Documents/Documents/Cowork/Tasks/sharepoint-modern-mockup-review-2026-10-27/output/SKiLNet_SharePoint_Modern_Mockup_v15.html`
2. Right-click the HTML file → **"Download"**
3. Save it to your local machine

#### To add it to the repository:
1. Rename the file to `index.html` (if not already named that)
2. Place it in the `docs/` folder
   ```
   AgenticWorkspace/
   └── docs/
       └── index.html  ← Your SharePoint mockup
   ```
3. If the HTML has external CSS/JS files, place them in:
   - `docs/css/` for stylesheets
   - `docs/js/` for JavaScript files
   - `docs/assets/` for images, fonts, etc.

4. Commit and push:
   ```bash
   cd /Users/STonkin/Downloads/AgenticWorkspace
   git add .
   git commit -m "Add SharePoint Modern Mockup HTML prototype"
   git push origin main
   ```

### Step 3: Configure GitHub Pages
**Status:** Manual setup required on GitHub.com

1. Go to: `https://github.com/sdtonkin1/AgenticWorkspace/settings/pages`
2. Under **"Build and deployment"**:
   - **Source:** Select `Deploy from a branch` (or `GitHub Actions` for CI/CD)
   - **Branch:** Select `main`
   - **Folder:** Select `/ (root)`
   
   *Note: Since we chose `/docs`, GitHub will automatically serve from `docs/`*

3. Leave **Enforce HTTPS** checked ✓
4. Click **"Save"**

GitHub will now deploy your site. You'll see a message:
> "Your site is live at `https://sdtonkin1.github.io/AgenticWorkspace/`"

### Step 4: Verify GitHub Pages is Working
**Status:** Do this after Step 3

1. Wait 1-2 minutes for GitHub Pages to build
2. Visit: `https://sdtonkin1.github.io/AgenticWorkspace/`
3. You should see your HTML prototype displayed

If it shows a 404:
- Check that `docs/index.html` exists in your repo
- Verify GitHub Pages settings are configured
- Clear your browser cache and refresh

### Step 5: Push Your Repository to GitHub
**Status:** Ready to execute

```bash
cd /Users/STonkin/Downloads/AgenticWorkspace

# Add the remote (use the URL from your GitHub repository)
git remote add origin https://github.com/sdtonkin1/AgenticWorkspace.git

# Set default branch to main (if not already)
git branch -m main

# Push to GitHub
git push -u origin main
```

**You may be prompted for authentication:**
- If using HTTPS: Enter your GitHub Personal Access Token (not your password)
- If using SSH: Make sure your SSH key is configured

### Step 6: Access Your Private Repository
**Status:** Done after Step 5

- **Private Repository URL:** `https://github.com/sdtonkin1/AgenticWorkspace`
- **GitHub Pages URL:** `https://sdtonkin1.github.io/AgenticWorkspace/`
- **Only you (and collaborators) can see** the repository
- **Anyone with the link can view** the GitHub Pages site (you can change this in settings)

---

## 🔐 Privacy & Security Notes

### Repository Privacy
- ✓ **Private:** Only you and invited collaborators can see the source code
- ✓ **GitHub Pages:** By default, the published site is public (but hard to discover)

### To make GitHub Pages private:
1. Go to `https://github.com/sdtonkin1/AgenticWorkspace/settings/pages`
2. Under **"Restrict access to GitHub Pages"** (if available)
3. Require authentication or use GitHub's built-in access restrictions

Alternatively, use GitHub's environment protection rules or require authentication.

---

## 🛠️ Troubleshooting

### Issue: "404 Not Found" on GitHub Pages
**Solution:**
1. Verify `docs/index.html` exists: `ls -la docs/index.html`
2. Check GitHub Pages settings are correctly configured
3. Wait 2-3 minutes for deployment to complete
4. Check the "Actions" tab on GitHub for deployment errors

### Issue: Git push fails with authentication error
**Solution:**
- For HTTPS: Create a Personal Access Token (PAT) at `github.com/settings/tokens`
  - Select scopes: `repo`, `workflow`
  - Use PAT instead of password when prompted
- For SSH: Set up SSH keys:
  ```bash
  ssh-keygen -t ed25519 -C "stonkin@rightpoint.com"
  pbcopy < ~/.ssh/id_ed25519.pub
  # Paste into GitHub Settings → SSH Keys
  ```

### Issue: HTML doesn't render correctly
**Common causes:**
1. **Relative paths broken:** Update CSS/JS/image paths to be relative to `docs/`
   - Change: `href="/css/style.css"` → `href="css/style.css"`
   - Change: `src="/js/script.js"` → `src="js/script.js"`
2. **External resources blocked:** HTTPS/CORS issues
3. **Missing dependencies:** Ensure all referenced files are committed

---

## 📚 File Structure Reference

```
AgenticWorkspace/
├── .git/                      # Git repository data
├── .gitignore                 # Files to ignore
├── README.md                  # Repository description
├── GITHUB_SETUP_GUIDE.md      # This file
│
└── docs/                      # ← GitHub Pages serves from here
    ├── index.html             # Main prototype (replace with your HTML)
    ├── css/
    │   ├── styles.css
    │   └── ... (other stylesheets)
    ├── js/
    │   ├── script.js
    │   └── ... (other scripts)
    └── assets/
        ├── images/
        ├── fonts/
        └── ... (other assets)
```

---

## 🚀 Next Steps

1. **Create the GitHub repository** (Step 1)
2. **Download your HTML from SharePoint** (Step 2)
3. **Place it in `docs/index.html`** (Step 2)
4. **Push to GitHub** (Step 5)
5. **Configure GitHub Pages** (Step 3)
6. **Verify it's live** (Step 4)

---

## 📖 Useful Links

- **GitHub Repository:** `https://github.com/sdtonkin1/AgenticWorkspace`
- **GitHub Pages:** `https://sdtonkin1.github.io/AgenticWorkspace/`
- **GitHub Pages Docs:** `https://docs.github.com/en/pages`
- **GitHub CLI Reference:** `https://cli.github.com/manual/`
- **Git Commands Cheat Sheet:** `https://git-scm.com/docs`

---

## ✅ Completion Checklist

- [ ] Created private GitHub repository named "AgenticWorkspace"
- [ ] Downloaded HTML prototype from SharePoint
- [ ] Placed HTML in `docs/index.html`
- [ ] Committed all files to Git: `git add . && git commit -m "..."`
- [ ] Pushed to GitHub: `git push -u origin main`
- [ ] Configured GitHub Pages in repository settings
- [ ] Verified GitHub Pages is live at: `https://sdtonkin1.github.io/AgenticWorkspace/`
- [ ] Updated file paths if needed (relative paths in HTML/CSS)
- [ ] (Optional) Added collaborators to private repository

---

**Last Updated:** November 13, 2024  
**For help:** Refer to GitHub documentation or contact GitHub Support
