# Overlyrics (Taskbar Edition)

A fork of **Overlyrics**, redesigned to live seamlessly **inside the Windows taskbar** instead of floating above the desktop.

This edition places synchronized Spotify lyrics directly in the taskbar area — centered, minimal, distraction‑free, and always on top.

---

## 🔥 Key Features

- **Taskbar Docking** — Lyrics sit *inside* the taskbar height (no wasted desktop space).
- **True Centering** — Horizontally centered; fixes layout drift on long lines.
- **Always On Top** — Window reasserts topmost state after every lyric update.
- **Smooth Transitions** — Fade-in/out animations for lyric changes.
- **Spotify Sync** — Uses Spotipy + Spotify Playback API to track current song.
- **Threaded Workers** — Background threads for API and lyric-sync keep UI responsive.
- **Transparent UI** — Minimal, modern overlay look.

---

## ⚙️ Requirements

- Python 3.9+
- PySide6
- spotipy
- syncedlyrics (or your lyrics provider)
- Optional: `Public Sans` font (falls back to Arial if missing)

Install with:

```bash
pip install -r requirements.txt
```

If you don't have a `requirements.txt`, install basics:

```bash
pip install PySide6 spotipy syncedlyrics
```

---

## 🔧 Setup

1. Add your Spotify API Client ID to the script by setting the `CLIENT_ID` constant.
2. Ensure `REDIRECT_URI` in the script is registered in your Spotify Developer Dashboard.
3. Run the app:

```bash
python working.py
```

On first run the app may open a browser tab for authentication. Paste the auth code into the small Tkinter prompt when requested.

---

## 🖥 Positioning Behavior

This fork positions the lyric window *inside the taskbar height* and centers it horizontally.  
Positioning code uses `QScreen.geometry()` (full screen) and `availableGeometry()` to calculate `taskbar_height`, then places the window so it overlaps into the taskbar area (no extra vertical space above desktop).

If your taskbar is on another monitor or docked differently, adjust the placement logic in the `if __name__ == "__main__"` block.

---

## 🛠 Notable Implementation Notes

- The hidden animation label is set to avoid expanding layout width to prevent right-shift drift.
- `window.adjustSize()` and `window.repaint()` are called before positioning to get correct dimensions.
- `self.setWindowFlag(Qt.WindowStaysOnTopHint, True)` and `self.show()` are called on lyric updates to keep the window on top.
- If Public Sans font isn't installed, the app falls back to Arial (see console warning).

---

## ❗ Known Issues & Tips

- If the window appears off-center, try resizing or toggling the taskbar auto-hide setting; the app attempts to calculate taskbar height but complex multi-monitor setups may need manual tweaks.
- Running the app as administrator may affect topmost behavior; generally no admin rights are required.
- On Linux or macOS, taskbar handling differs — this fork is primarily targeted at Windows.

---

## ♻️ Contributing

This project is a fork of [CezarGab/Overlyrics](https://github.com/CezarGab/Overlyrics). Contributions, bug reports, and PRs are welcome.

---

## 📜 License

This project is licensed under the MIT License — see `LICENSE` for details.

---

## Contact

For issues or suggestions, open an issue on the repository or contact the maintainer.

