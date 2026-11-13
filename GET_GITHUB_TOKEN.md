# Getting Your GitHub Personal Access Token

## Why You Need This

GitHub no longer accepts your regular password for command-line operations. Instead, you need a **Personal Access Token** (PAT).

## Steps to Create Your Token

### 1. Go to GitHub Settings
- Visit: https://github.com/settings/tokens
- Or: Click your profile icon (top-right) → Settings → Developer settings → Personal access tokens → Tokens (classic)

### 2. Click "Generate new token (classic)"

### 3. Fill in the Token Details
```
Token name:     My Mac Git Token
               (or any name you prefer)

Expiration:     90 days
               (choose what works for you)

Scopes:         Check these boxes:
                ☑ repo (Full control of private repositories)
                ☑ workflow (Update GitHub Action workflows)
```

### 4. Click "Generate token"

### 5. **IMPORTANT: Copy Your Token Immediately!**
- You'll see a long string like: `ghp_1234567890abcdefghijklmnopqrstuv`
- **COPY THIS NOW** - you won't see it again!
- Don't share this token with anyone

### 6. Save It Somewhere Safe
- **Option A:** Paste it into a secure password manager
- **Option B:** Paste it into a text file and store securely
- **Do NOT commit it to GitHub**

## Using Your Token

When git asks for your password during `git push`, instead enter:
```
Username: sdtonkin1
Password: [paste your token here - NOT your GitHub password]
```

## After First Use

Git will ask to save it in your macOS Keychain. Click "Allow" so you don't have to enter it every time.

## If You Lose Your Token

1. Go back to: https://github.com/settings/tokens
2. Delete the old token
3. Generate a new one
4. Update your Keychain:
   - Keychain Access → search "github.com"
   - Delete the old entry
   - Next git command will prompt you to re-enter the new token

---

**Now you're ready to push!**

Go back and run:
```bash
cd /Users/STonkin/Downloads/AgenticWorkspace
git push -u origin main
```
