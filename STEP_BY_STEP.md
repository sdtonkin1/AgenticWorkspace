# Step-by-Step: From SharePoint to GitHub Pages

## Overview
This guide takes you through creating a private GitHub repo and hosting your HTML prototype on GitHub Pages in 6 manageable steps.

---

## STEP 1: Create the Private Repository on GitHub

**Time Required:** 2 minutes  
**What you'll do:** Create a new private repository on GitHub.com

### Instructions:

1. **Open GitHub in your browser:**
   - Go to [github.com](https://github.com)
   - Sign in with your account (sdtonkin1)

2. **Click the "+" menu:**
   - Look in the top-right corner
   - Click the **"+"** icon
   - Select **"New repository"**

3. **Fill in the form:**
   ```
   Repository name:     AgenticWorkspace
   Description:         HTML prototype for SharePoint Modern Mockup (SKiLNet v15)
   Visibility:          PRIVATE ← Important!
   .gitignore template: Node (optional)
   License:             (skip, or choose MIT)
   ```

4. **Click "Create repository"**

5. **You'll see a page with setup instructions.** Copy the commands under:
   - "…or push an existing repository from the command line"
   - They'll look like:
     ```bash
     git remote add origin https://github.com/sdtonkin1/AgenticWorkspace.git
     git branch -m main
     git push -u origin main
     ```

✅ **Step 1 Complete!** Your private repository now exists on GitHub.

---

## STEP 2: Download Your HTML from SharePoint

**Time Required:** 5 minutes  
**What you'll do:** Download the HTML file from SharePoint to your computer.

### Instructions:

1. **Open the SharePoint link:**
   - Go to: `https://rpo365-my.sharepoint.com/personal/stonkin_rightpoint_com/Documents/Documents/Cowork/Tasks/sharepoint-modern-mockup-review-2026-10-27/output/SKiLNet_SharePoint_Modern_Mockup_v15.html`

2. **Download the file:**
   - Right-click the file name
   - Select **"Download"** (or similar option depending on your browser)
   - Save it to your Downloads folder

3. **Remember the file location:**
   - The file will be named something like: `SKiLNet_SharePoint_Modern_Mockup_v15.html`
   - It's now in your Downloads folder

✅ **Step 2 Complete!** You have the HTML file on your computer.

---

## STEP 3: Organize Files in Your Project

**Time Required:** 3 minutes  
**What you'll do:** Copy your HTML to the correct project folder.

### Instructions:

1. **Rename the HTML file (optional but recommended):**
   - Right-click the downloaded file
   - Rename it to: `index.html`
   - This makes it the default landing page for GitHub Pages

2. **Copy it to your project folder:**
   - Open Finder
   - Navigate to: `/Users/STonkin/Downloads/AgenticWorkspace/docs/`
   - Drag your `index.html` file there
   - It should replace the template `index.html` we created

3. **If your HTML has external files:**
   - CSS files → `docs/css/`
   - JavaScript files → `docs/js/`
   - Images → `docs/assets/`

4. **Verify the structure:**
   ```bash
   cd /Users/STonkin/Downloads/AgenticWorkspace
   ls -la docs/
   # Should show: index.html, css/, js/, assets/
   ```

✅ **Step 3 Complete!** Your HTML is in the right place.

---

## STEP 4: Prepare Files for GitHub

**Time Required:** 2 minutes  
**What you'll do:** Make sure file paths work with GitHub Pages.

### Instructions:

1. **Check your HTML file for absolute paths:**
   - Open `docs/index.html` in a text editor
   - Look for these patterns:
     ```html
     href="/css/styles.css"    ← BAD (absolute)
     src="/js/script.js"       ← BAD (absolute)
     src="/images/logo.png"    ← BAD (absolute)
     ```

2. **Fix any absolute paths to relative paths:**
   - Change from: `/css/styles.css` → to: `css/styles.css`
   - Change from: `/images/logo.png` → to: `assets/images/logo.png`
   - Save the file

3. **Why this matters:**
   - GitHub Pages serves from `docs/` folder
   - Absolute paths (`/css/`) won't work correctly
   - Relative paths (`css/`) will find the file correctly

✅ **Step 4 Complete!** File paths are ready for GitHub Pages.

---

## STEP 5: Push Your Files to GitHub

**Time Required:** 3 minutes  
**What you'll do:** Upload everything to GitHub.

### Instructions:

1. **Open Terminal/Command Prompt**

2. **Navigate to your project:**
   ```bash
   cd /Users/STonkin/Downloads/AgenticWorkspace
   ```

3. **Check git status:**
   ```bash
   git status
   ```
   You should see `index.html` listed as a new/modified file.

4. **Add all files:**
   ```bash
   git add .
   ```

5. **Commit your changes:**
   ```bash
   git commit -m "Add SharePoint Modern Mockup HTML prototype"
   ```

6. **Add the remote (copy from Step 1):**
   ```bash
   git remote add origin https://github.com/sdtonkin1/AgenticWorkspace.git
   ```

7. **Push to GitHub:**
   ```bash
   git push -u origin main
   ```

8. **If prompted for credentials:**
   - **Option A (Recommended):** Use a Personal Access Token
     - Go to: `https://github.com/settings/tokens`
     - Create a new token with `repo` scope
     - Paste the token when prompted
   - **Option B:** Use SSH keys (if already configured)
   - **Option C:** Use GitHub CLI (`gh auth login`)

✅ **Step 5 Complete!** Your files are now on GitHub!

---

## STEP 6: Enable GitHub Pages

**Time Required:** 2 minutes  
**What you'll do:** Configure GitHub to serve your HTML as a website.

### Instructions:

1. **Go to your repository settings:**
   - URL: `https://github.com/sdtonkin1/AgenticWorkspace/settings/pages`
   - Or: Click Settings → Pages (in left sidebar)

2. **Configure GitHub Pages:**
   ```
   Build and deployment
   Source:           Deploy from a branch
   Branch:           main
   Folder:           / (root)
   ```

3. **Save settings**

4. **GitHub will show a message:**
   ```
   ✓ Your site is live at:
     https://sdtonkin1.github.io/AgenticWorkspace/
   ```

5. **Wait 2-3 minutes for deployment**
   - GitHub needs time to build your site
   - You can watch progress in the "Actions" tab

✅ **Step 6 Complete!** GitHub Pages is now configured!

---

## STEP 7: Verify Everything Works

**Time Required:** 1 minute  
**What you'll do:** Visit your live site to confirm everything works.

### Instructions:

1. **Wait 2-3 minutes** after Step 6 completes

2. **Visit your GitHub Pages URL:**
   ```
   https://sdtonkin1.github.io/AgenticWorkspace/
   ```

3. **You should see your HTML prototype displayed!**

4. **If something's wrong:**
   - Check the "Actions" tab on GitHub for error messages
   - Make sure `docs/index.html` exists
   - Verify file paths are relative (not absolute)
   - Clear your browser cache and refresh

✅ **Step 7 Complete!** Your site is live!

---

## Final Checklist ✅

- [x] Created private GitHub repository
- [x] Downloaded HTML from SharePoint
- [x] Organized files in correct folders
- [x] Fixed file paths for GitHub Pages
- [x] Pushed files to GitHub
- [x] Enabled GitHub Pages
- [x] Verified site is live

---

## 🎉 Success!

Your private HTML prototype is now:
- **Stored securely** in a private GitHub repository
- **Published online** via GitHub Pages
- **Accessible at:** `https://sdtonkin1.github.io/AgenticWorkspace/`
- **Version controlled** with Git (track all changes)

---

## Next Steps (Optional Improvements)

### Share with Team Members
1. Go to repository Settings → Collaborators
2. Add team members (they can view private repo)
3. They can still view GitHub Pages site

### Make GitHub Pages Private
1. Settings → Pages
2. Look for access restrictions (if available on your plan)
3. Require authentication to view the site

### Add Custom Domain
1. If you have a custom domain, you can use it
2. Settings → Pages → Custom domain
3. Point DNS to GitHub Pages servers

### Add SSL/HTTPS
- GitHub Pages automatically provides HTTPS ✓

### Enable Branch Protection
1. Settings → Branches → Add rule
2. Require pull request reviews before merging
3. This ensures quality control before deployment

---

**Questions?** Refer to the `GITHUB_SETUP_GUIDE.md` or `QUICK_REFERENCE.md` files in your project folder.

**GitHub Pages Documentation:** https://docs.github.com/en/pages
