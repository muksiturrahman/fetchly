# Install Fetchly on Linux

**Other systems:** [Mac](mac.md) · [Windows](windows.md) · [Android](android.md) · [Download page](https://muksiturrahman.github.io/fetchly/)

Setup takes about 3 minutes. You need a **64-bit Linux desktop with GTK 3** (Ubuntu 22.04+, Debian 12+, Fedora, Mint, and most others) and **Google Chrome** or **Chromium**.

- [1 · Install the app](#1--install-the-app)
- [2 · Add the Chrome extension](#2--add-the-chrome-extension)
- [3 · Add video support](#3--add-video-support)
- [4 · Check it works](#4--check-it-works)
- [Updating](#updating) · [Uninstalling](#uninstalling) · [Troubleshooting](#troubleshooting)

---

## 1 · Install the app

```bash
mkdir -p ~/Applications/Fetchly
tar -xzf ~/Downloads/Fetchly-Linux.tar.gz -C ~/Applications/Fetchly
~/Applications/Fetchly/fetchly
```

(Download **[Fetchly-Linux.tar.gz](https://github.com/muksiturrahman/fetchly/releases/latest/download/Fetchly-Linux.tar.gz)** first.)

On first launch Fetchly adds itself to your **applications menu** and registers the `fetchly://` link, so the extension's **Open Fetchly** button can start it. It then opens its **setup guide**.

## 2 · Add the Chrome extension

1. In the setup guide, click **Copy Folder Path & Open Chrome** (or open `chrome://extensions` yourself).
2. Turn on **Developer mode** (top right), then click **Load unpacked**.
3. In the folder window press **Ctrl+L**, paste the path, press **Enter**, then click **Select**.

   The path is `~/.local/share/Fetchly/ChromeExtension`.

4. Pin Fetchly from the puzzle-piece menu.

## 3 · Add video support

YouTube and about 1,800 other sites need **yt-dlp**: in the setup guide (or **Settings → Video**), click **Download yt-dlp** (about 35 MB).

For **1080p and above (including 4K)**, install **ffmpeg**, and for YouTube a JavaScript runtime:

```bash
sudo apt install ffmpeg nodejs        # Debian, Ubuntu, Mint
sudo dnf install ffmpeg nodejs        # Fedora (ffmpeg from RPM Fusion)
```

Restart Fetchly afterwards.

## 4 · Check it works

- The Fetchly popup in Chrome says **Connected** and shows the same version as the app.
- Play any video: a **Download video** bar appears on it. Click it and pick a quality.

---

## Updating

Quit Fetchly, extract the new archive over the old folder, start it again. Then click **↻** on Fetchly in `chrome://extensions` and refresh your tabs.

## Uninstalling

```bash
rm -rf ~/Applications/Fetchly ~/.local/share/applications/fetchly.desktop
rm -rf ~/.local/share/Fetchly        # optional: list, settings, yt-dlp, extension copy
```

Remove the extension in `chrome://extensions`. Your downloaded files are not touched.

## Troubleshooting

| Problem | Fix |
| --- | --- |
| `error while loading shared libraries: libgtk-3.so.0` | Install GTK 3: `sudo apt install libgtk-3-0`. |
| The popup says **Not running** | Start Fetchly from the applications menu. Closing the window quits it. |
| **Open Fetchly** does nothing | Start Fetchly once: it re-registers the link (needed after moving the folder). |
| No notifications | Install `libnotify-bin` (`notify-send`). |
| Move to Trash doesn't work | Fetchly uses `gio trash`, part of GLib; files stay in place if it's missing. |
| 1080p and 4K are missing | Install ffmpeg (step 3) and restart Fetchly. |
