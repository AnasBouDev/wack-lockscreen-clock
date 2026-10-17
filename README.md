# WACK – Sonoma Lockscreen Clock

> A GNOME Shell extension that transforms your lock screen into a macOS Sonoma / Cupertino-style experience — beautiful ambient clock, blurred background, and a polished password prompt.

![GNOME Shell](https://img.shields.io/badge/GNOME%20Shell-46–51-blue?logo=gnome)
![License](https://img.shields.io/github/license/rinzler69-wastaken/wack-lockscreen-clock)

---

## ✨ Features

- **Sonoma-style clock** — large, elegant time & date display on the lock screen
- **Cupertino layout mode** — iOS/macOS-inspired password prompt with smooth blur
- **Adaptive scaling** — prompt box correctly sizes and positions on any resolution
- **GNOME 46 → 51 compatible** — fully updated for modern GNOME Shell APIs (ESM imports, Clutter orientation, async safety)
- **Wayland & X11** support

---

## 📦 Installation

### From source

```bash
# Clone the repo
git clone https://github.com/rinzler69-wastaken/wack-lockscreen-clock.git

# Install the extension
cp -r wack-lockscreen-clock \
  ~/.local/share/gnome-shell/extensions/wack-lockscreen-clock@rinzler69-wastaken.github.com

# Restart GNOME Shell (X11: Alt+F2 → r; Wayland: log out & back in)
# Then enable
gnome-extensions enable wack-lockscreen-clock@rinzler69-wastaken.github.com
```

### Requirements

| Dependency | Version |
|---|---|
| GNOME Shell | 46 – 51 |
| GJS | 1.74+ |

---

## ⚙️ Configuration

Open **GNOME Extensions** app → click the ⚙ gear next to *WACK – Sonoma Lockscreen* — or run:

```bash
gnome-extensions prefs wack-lockscreen-clock@rinzler69-wastaken.github.com
```

---

## 🛠 GNOME 51 Migration Notes

| Change | Details |
|---|---|
| `shell-version` | Added `46` through `51` |
| `St.BoxLayout` orientation | Replaced deprecated `vertical: true` → `orientation: Clutter.Orientation.VERTICAL` |
| Async safety | Added `.catch()` on all floating promises; `get_stage?.()` guards on Clutter actors |
| Cupertino prompt scaling | Fixed width (`22em`/`340px`), entry height (`38px`), bottom-margin clamping (`28px`) |

---

## 📁 Project Structure

```
extension.js              Main entry point
prefs.js                  Preferences UI
stylesheet.css            All custom styles (including Cupertino prompt)
src/
  main/
    wackClock.js          Clock widget
    layoutManager.js      Cupertino layout positioning
    cupertinoPromptManager.js  Prompt state management
    promptStyling.js      Entry / button styling helpers
    unblank.js            Background unblur logic
    alphaCache.js         Alpha/blur caching
schemas/                  GSettings schemas
```

---

## 🤝 Contributing

Pull requests are welcome! Please open an issue first to discuss major changes.

---

## 📄 License

MIT © rinzler69-wastaken
