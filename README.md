# Morning Habits

When you stop your morning alarm, a Shortcut opens your checklist site on GitHub Pages. **Walk** and **Read** only get checked off after you add a photo that passes the checks.

```
Alarm stops ──► Shortcut opens https://adamsalv.github.io/morning-habits/
                     │
                     ├─ 🚶 Walk: photo from today, taken away from home (GPS check)
                     ├─ 📖 Read: photo from today
                     │
                     └─► saved on your phone + backed up to data/log.json in the repo
```

## How fakes are caught

| Button | What's checked |
|---|---|
| **📷 Take photo now** | Opens the camera. The photo has to be less than 3 minutes old. For **Walk**, the page also gets your live GPS position. It has to be accurate to within 100 m and at least 200 m from home (you can change that distance). |
| **🖼️ Pick today's photo** | Reads the photo's own data. Its date has to be today. For **Walk**, its GPS location also has to be at least 200 m from home. Old photos, screenshots, and photos with no data are rejected. |

Your home location stays on your phone and is never uploaded. The repo only records the date, the time, and how far from home the walk photo was. No photos or coordinates are stored there.

**Heads-up:** When you pick a photo from your library on a website, iPhone often removes its location data. If a walk photo from your library gets rejected for "no GPS data", use **Take photo now** instead.

## Setup

1. **Turn on Pages:** repo **Settings → Pages → Deploy from a branch → `main` / `(root)` → Save**. The site goes live at `https://adamsalv.github.io/morning-habits/`.
2. **Open on alarm:** Shortcuts → **Automation → + → Alarm → Is Stopped** (your morning alarm) → **Run Immediately**, turn off **Notify When Run** → action **Open URLs** with the site link.
3. **First time on the phone (at home):** open the site in Safari → **⚙️ Settings → Set home to where I am now**. To stop the daily location prompt: **aA → Website Settings → Location: Allow**.
4. *(Optional backup)* GitHub **Settings → Developer settings → Fine-grained tokens**: access to only `morning-habits`, **Contents: Read and write**. Paste it into the site's Settings and tap **Save**.

## Files

- `index.html`: the checklist, photo checks, streak, 20-week calendar, and GitHub backup
- `data/log.json`: your history, updated by the site each morning

## Limits

This keeps an honest person honest. It isn't tamper-proof: someone who knows the code could edit the page or fake GPS.
