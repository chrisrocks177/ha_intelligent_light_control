# 🚀 Quick Start: Publishing to GitHub

## Quick Guide in 5 Steps

### 1️⃣ Create Repository on GitHub
1. Go to https://github.com/new
2. **Repository name:** `ha-knx-light-control` (or your choice)
3. **Description:** `Professional KNX light control Blueprint for Home Assistant`
4. Select **Public**
5. **DO NOT** check:
   - [ ] Add a README file (we already have one)
   - [ ] Add .gitignore (we already have one)
   - [ ] Choose a license (we already have one)
6. Click **Create repository**

### 2️⃣ Install Git (if not already installed)

**Windows:** https://git-scm.com/download/win  
**Mac:** `brew install git` or `xcode-select --install`  
**Linux:** `sudo apt-get install git`

### 3️⃣ Initialize Local Repository

Open Terminal/Command Prompt in the folder with all files:

```bash
# Configure Git (one-time)
git config --global user.name "Your Name"
git config --global user.email "your@email.com"

# Initialize repository
git init
git add .
git commit -m "Initial commit: KNX Light Control Blueprint v1.1.0"
```

### 4️⃣ Connect to GitHub and Upload

```bash
# Replace YOUR-USERNAME with your GitHub username
git remote add origin https://github.com/YOUR-USERNAME/ha-knx-light-control.git
git branch -M main
git push -u origin main
```

### 5️⃣ Configure Repository

On GitHub:
1. Go to your repository
2. Click **Settings** (gear icon next to "About")
3. Add:
   - **Description:** `Professional KNX light control Blueprint for Home Assistant`
   - **Website:** `https://www.home-assistant.io/`
   - **Topics:** `home-assistant`, `knx`, `blueprint`, `automation`, `smart-home`

## ✅ Done!

Your Blueprint is now publicly available!

### Import URL for Home Assistant:
```
https://github.com/YOUR-USERNAME/ha-knx-light-control/blob/main/light_control_day_night_EN.yaml
```

## 📝 Important: Replace Placeholders

Open these files and replace:
- `README.md` → All `YOUR-USERNAME` and `YOUR-REPO`
- `LICENSE` → `[YOUR NAME]`

## 📢 Share with Community

### Home Assistant Forum
https://community.home-assistant.io/ → Share Your Projects

### Reddit
- r/homeassistant
- r/homeautomation

## 🔄 Create Release

1. Go to **Releases** → **Create a new release**
2. **Tag:** `v1.1.0`
3. **Title:** `v1.1.0 - Scene-Based Switching`
4. **Description:** Copy from CHANGELOG.md
5. **Publish release**

## 🆘 Problems?

See `GITHUB_SETUP.md` for detailed guide with troubleshooting.

---

**Good luck! 🎉**
