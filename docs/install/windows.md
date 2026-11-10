# Install Fetchly on Windows

**Other systems:** [Mac](mac.md) · [Linux](linux.md) · [Android](android.md) · [Download page](https://muksiturrahman.github.io/fetchly/)

Setup takes about 3 minutes. You need **Windows 10 or 11 (64-bit)** and **Google Chrome** (or Edge, Brave or Opera).

- [1 · Install the app](#1--install-the-app)
- [2 · Open it the first time](#2--open-it-the-first-time)
- [3 · Add the Chrome extension](#3--add-the-chrome-extension)
- [4 · Add video support](#4--add-video-support)
- [5 · Check it works](#5--check-it-works)
- [Updating](#updating) · [Uninstalling](#uninstalling) · [Troubleshooting](#troubleshooting)

---

## 1 · Install the app

1. Download **[Fetchly-Windows.zip](https://github.com/muksiturrahman/fetchly/releases/latest/download/Fetchly-Windows.zip)**.
2. Right-click it → **Extract All…** and choose a folder you'll keep, for example `C:\Users\<you>\Fetchly`.
3. Optional: right-click **fetchly.exe** → **Show more options → Send to → Desktop (create shortcut)**, or pin it to Start.

Keep all the files together: `fetchly.exe` needs the `data` folder and the `.dll` files next to it.

## 2 · Open it the first time

Double-click **fetchly.exe**. Fetchly isn't signed with a paid Microsoft certificate yet, so Windows may show **Windows protected your PC**. Click **More info → Run anyway**. You only do this once.

If Windows asks whether Fetchly may use the network, allow **private networks**: the extension talks to the app on this PC only (`127.0.0.1`).

Fetchly opens its **setup guide**, with buttons for the next two steps. It also registers the `fetchly://` link for your Windows user, so the extension's **Open Fetchly** button can start the app.

## 3 · Add the Chrome extension

Google doesn't allow YouTube downloaders in the Chrome Web Store, so the extension is added in developer mode:

1. In the setup guide, click **Copy Folder Path & Open Chrome**. If Chrome doesn't open by itself, open it and go to `chrome://extensions`.
2. Turn on **Developer mode** (top right), then click **Load unpacked**.
3. In the folder window, click the address bar, paste the path with **Ctrl+V**, press **Enter**, then click **Select Folder**.

   The path is `%APPDATA%\Fetchly\ChromeExtension` (usually `C:\Users\<you>\AppData\Roaming\Fetchly\ChromeExtension`).

4. Click the puzzle-piece icon in Chrome's toolbar and **pin** Fetchly.

## 4 · Add video support

YouTube and about 1,800 other sites need **yt-dlp**. In the setup guide (or **Settings → Video**), click **Download yt-dlp** (about 35 MB, downloaded only when you click).

For **1080p and above (including 4K)**, install **ffmpeg**, which joins video and sound. In **Terminal** or **PowerShell**:

```powershell
winget install ffmpeg
```

YouTube also needs **Node.js** (or Deno or Bun):

```powershell
winget install OpenJS.NodeJS
```

Restart Fetchly afterwards so it finds them.

## 5 · Check it works

- The Fetchly popup in Chrome says **Connected** and shows the same version as the app (bottom right of its window).
- Play any video: a **Download video** bar appears on it. Click it and pick a quality.
- Click any download link in Chrome: Fetchly takes it over.

---

## Updating

Download the new zip, quit Fetchly, and extract the new files over the old folder. Then click **↻** on Fetchly in `chrome://extensions` and refresh your tabs. Your download list is kept.

## Uninstalling

1. Remove the extension in `chrome://extensions`.
2. Close Fetchly and delete its folder.
3. Optional: delete `%APPDATA%\Fetchly` (the download list, the extension copy and yt-dlp). Your downloaded files are not touched.

## Troubleshooting

| Problem | Fix |
| --- | --- |
| The popup says **Not running** | Start `fetchly.exe`, or click **Open Fetchly** in the popup. On Windows, closing the window quits Fetchly. |
| **Open Fetchly** does nothing | Start Fetchly once from its folder: it re-registers the link (needed after moving the folder). |
| A missing `.dll` error | The zip wasn't fully extracted. Extract all files again into one folder. |
| No **Download video** bar | Refresh the page after installing; check **Show "Download video" on videos** in the popup. |
| "Video support isn't installed" | Settings → Video → **Download yt-dlp**. |
| 1080p and 4K are missing | Install ffmpeg (step 4) and restart Fetchly. |
| Port 6801 in use | Another copy of Fetchly is running. Close it. |
