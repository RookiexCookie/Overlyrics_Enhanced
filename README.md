<p align="center">
 <img width="400px" src="https://github.com/CezarGab/Overlyrics/raw/main/Logos/main-logo.png" align="center" alt="GitHub Readme Stats" />
 <h2 align="center">Overlyrics Enhanced</h2>
 <p align="center">Bringing the lyrics to life!</p>
</p>
  <p align="center">
    <a href="https://www.python.org">
      <img alt="Python 3.9" src="https://img.shields.io/badge/Python-3.9-3776AB.svg?style=flat&logo=python&logoColor=white" />
    </a>
    <a>
      <img alt="License - MIT" src="https://img.shields.io/badge/License-MIT-yellow.svg" />
    </a>
    <br />
    <br />
    <a>
      <img src="https://img.shields.io/badge/Spotify-1ED760?&style=for-the-badge&logo=spotify&logoColor=white"/>
    </a>
    <a>
      <img src="https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=blue"/>
    </a>
    <a>
      <img src="https://img.shields.io/badge/GitHub%20Pages-222222?style=for-the-badge&logo=GitHub%20Pages&logoColor=white"/>
    </a>
 <p align="center">
   <a>
      <video src="demo.mp4"/>
    </a>
  </p>



Overlyrics is a desktop lyrics overlay that displays **real-time, synchronized Spotify lyrics** on top of any window.  
This fork improves performance, adds a modern UI using **PySide6 (Qt)** instead of Tkinter for the overlay window, and includes several bug fixes for long-term stability.

---

## 🔥 Key Improvements in This Fork

✅ Migrated overlay UI from **Tkinter** to **PySide6 (Qt)** for smoother animations  
✅ Fade-in / fade-out lyric transitions  
✅ Higher polling precision for lyric timing  
✅ Independent background worker threads for API + sync  
✅ Clean shutdown management (no more orphan threads)  
✅ Font fallback handling if Public Sans is unavailable  
✅ Executable build ships with all dependencies bundled  
✅ Smaller latency between Spotify playback → lyric display  
✅ Better no-music / no-lyrics feedback handling

---

## 🧩 What You Need To Run the Python Script (`Overlyrics.py`)

First install:

```
pip install spotipy
pip install syncedlyrics
pip install PySide6
```

> Optional: Install **Public Sans** font for best visuals  
(Overlyrics will fall back to Arial if missing).

---

## 🔑 Spotify Authentication (First Run Only)

1. Create an app at https://developer.spotify.com/dashboard/
2. Copy the **Client ID** into the script (`CLIENT_ID`)
3. Add this Redirect URI in the app settings:

```
https://cezargab.github.io/Overlyrics
```

4. On the first run, a small authentication window opens.
5. After authentication, tokens are cached locally — no repeat login.

---

## 🧪 Running from Source

```
python Overlyrics.py
```

The floating lyrics overlay will appear and stay on top of other windows.  
Drag with **left-click**, right-click to open menu (resize text / quit).

---

## 🛠️ Build Your Own Executable

```
pip install pyinstaller
pyinstaller --noconfirm --clean --windowed --name "Overlyrics" Overlyrics.py
```

A `.spec` file will be generated. You can delete it **if you don’t plan to rebuild**,  
but keep it if you want reproducible builds.

---

## 📜 License

This project uses the MIT license, same as the original upstream repository.

---

Enjoy the music 🎧
