# 🚀 Quick Start: Publish auf GitHub

## Schnellanleitung in 5 Schritten

### 1️⃣ Repository auf GitHub erstellen
1. Gehe zu https://github.com/new
2. **Repository name:** `ha-knx-light-control` (oder dein Name)
3. **Description:** `Professionelle KNX-Lichtsteuerung Blueprint für Home Assistant`
4. **Public** anwählen
5. **NICHT** ankreuzen: README, .gitignore, license
6. Klicke **Create repository**

### 2️⃣ Git installieren (falls noch nicht installiert)

**Windows:** https://git-scm.com/download/win  
**Mac:** `brew install git` oder `xcode-select --install`  
**Linux:** `sudo apt-get install git`

### 3️⃣ Lokales Repository initialisieren

Öffne Terminal/Command Prompt im Ordner mit allen Dateien:

```bash
# Git konfigurieren (einmalig)
git config --global user.name "Dein Name"
git config --global user.email "deine@email.com"

# Repository initialisieren
git init
git add .
git commit -m "Initial commit: KNX Light Control Blueprint v1.1.0"
```

### 4️⃣ Mit GitHub verbinden und hochladen

```bash
# Ersetze DEIN-USERNAME mit deinem GitHub-Username
git remote add origin https://github.com/DEIN-USERNAME/ha-knx-light-control.git
git branch -M main
git push -u origin main
```

### 5️⃣ Repository konfigurieren

Auf GitHub:
1. Gehe zu deinem Repository
2. Klicke auf **Settings** (Zahnrad rechts bei "About")
3. Füge hinzu:
   - **Description:** `Professionelle KNX-Lichtsteuerung Blueprint für Home Assistant`
   - **Website:** `https://www.home-assistant.io/`
   - **Topics:** `home-assistant`, `knx`, `blueprint`, `automation`, `smart-home`

## ✅ Fertig!

Dein Blueprint ist jetzt öffentlich verfügbar!

### Import-URL für Home Assistant:
```
https://github.com/DEIN-USERNAME/ha-knx-light-control/blob/main/light_control_day_night.yaml
```

## 📝 Wichtig: Platzhalter ersetzen

Öffne diese Dateien und ersetze:
- `README.md` → Alle `DEIN-USERNAME` und `DEIN-REPO`
- `LICENSE` → `[DEIN NAME]`

## 📢 Community teilen

### Home Assistant Forum
https://community.home-assistant.io/ → Share Your Projects

### Reddit
- r/homeassistant
- r/homeautomation

## 🔄 Release erstellen

1. Gehe zu **Releases** → **Create a new release**
2. **Tag:** `v1.1.0`
3. **Title:** `v1.1.0 - Szenenbasiertes Ausschalten`
4. **Description:** Kopiere aus CHANGELOG.md
5. **Publish release**

## 🆘 Probleme?

Siehe `GITHUB_SETUP.md` für detaillierte Anleitung mit Troubleshooting.

---

**Viel Erfolg! 🎉**
