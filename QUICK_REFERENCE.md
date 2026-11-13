# Quick Reference: GitHub Pages Setup

## 🎯 Your Project Details
- **GitHub Username:** sdtonkin1
- **Repository Name:** AgenticWorkspace
- **GitHub Pages URL:** https://sdtonkin1.github.io/AgenticWorkspace/
- **Repository URL:** https://github.com/sdtonkin1/AgenticWorkspace
- **Visibility:** Private ✓
- **Published Files Location:** `/docs` folder

---

## ⚡ Quick Commands

### 1️⃣ Create Repository on GitHub
```
Go to: https://github.com/new
- Name: AgenticWorkspace
- Private: YES
- Create Repository
```

### 2️⃣ Link Local Repository to GitHub
```bash
cd /Users/STonkin/Downloads/AgenticWorkspace
git remote add origin https://github.com/sdtonkin1/AgenticWorkspace.git
git branch -m main
git push -u origin main
```

### 3️⃣ After Adding Your HTML
```bash
cd /Users/STonkin/Downloads/AgenticWorkspace
git add .
git commit -m "Add SharePoint prototype"
git push
```

### 4️⃣ Configure GitHub Pages
```
Go to: https://github.com/sdtonkin1/AgenticWorkspace/settings/pages
- Source: Deploy from a branch
- Branch: main
- Folder: / (root)
- Save
```

### 5️⃣ Verify It's Live
```
Wait 2 minutes, then visit:
https://sdtonkin1.github.io/AgenticWorkspace/
```

---

## 📁 File Organization

```
docs/index.html          ← Your main HTML (replace template)
docs/css/styles.css      ← Stylesheets
docs/js/script.js        ← JavaScript
docs/assets/             ← Images, fonts, etc.
```

---

## 🔑 Important Notes

✓ **Private Repository:** Only you can see the GitHub repo  
✓ **Public GitHub Pages:** Anyone can view the published site (by default)  
✓ **No Secrets:** Don't commit API keys, passwords, tokens  
✓ **Relative Paths:** Use `css/styles.css` not `/css/styles.css` in HTML  

---

## ❌ Common Mistakes to Avoid

1. ❌ Setting repository to Public (use Private)
2. ❌ Putting HTML in root instead of `/docs`
3. ❌ Using absolute paths `/css/` instead of relative `css/`
4. ❌ Forgetting to push to GitHub after making changes
5. ❌ Not checking GitHub Actions for deployment errors

---

## 🆘 Need Help?

**GitHub Pages not showing?**
- Check: https://github.com/sdtonkin1/AgenticWorkspace/actions
- Look for "pages build and deployment" workflow

**HTML not rendering correctly?**
- Fix relative paths in CSS/JS imports
- Check browser console for errors (F12)

**Can't push to GitHub?**
- Use Personal Access Token instead of password
- Create one at: https://github.com/settings/tokens

---

**Project Location:** `/Users/STonkin/Downloads/AgenticWorkspace`  
**Ready to Deploy:** ✓ Yes
