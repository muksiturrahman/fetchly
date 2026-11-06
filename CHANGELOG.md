# Changelog

## 1.0.6

- **Fixed:** file names that the server sends percent-encoded (`My%20Movie.mp4`) are now saved readably (`My Movie.mp4`), as browsers do.
- New docs: an illustrated [install guide](docs/INSTALL.md), [how it works](docs/HOW-IT-WORKS.md), and a demo GIF in the README.

## 1.0.5

The first public release.

- **Setup guide** on first launch (also under **Help → Setup Guide**): install the Chrome extension, add video support, and try it. Each step is ticked off when it's done.
- **Universal app:** one download runs on both Apple Silicon and Intel Macs (macOS 14 or later).
- **Without ffmpeg**, the quality list only offers formats that already include sound, so a download never fails at the joining step.
- **Fixed:** the extension popup always showed "Fetchly isn't running", even when the app was connected.
- The app and the extension show their version (popup, `chrome://extensions`, status bar). The popup warns you when the extension needs a reload.

## 1.0.2 – 1.0.4

- **Download video** bar: appears by itself when a video plays, follows the main video, ignores background and preview clips, waits for ad/player swaps instead of blinking, and returns after you scroll back.
- Pasted page links (YouTube etc.) find the video instead of saving the page's HTML. A web page is never saved by mistake.
- **Clear History** (File menu and Settings → Privacy). Finished downloads no longer keep the site's cookies.

## 1.0.0

- First version: multi-connection downloads with dynamic splitting, resume after pause/quit/crash, queue, categories, menu bar, notifications.
- Video downloads through yt-dlp with a quality picker (4K … audio only, MP3), and HLS streams through ffmpeg.
- Chrome extension: download capture, video detection, right-click menu, popup.
