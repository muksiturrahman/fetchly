# Changelog

## 2.1.0

- **Android downloads keep going in the background:** switch apps, lock the screen or swipe Fetchly away, and the download continues, with its progress in a notification. Finished and failed downloads get a notification too.
- **Pause and resume for streams and YouTube on Android:** they now continue where they stopped (also after Android closes the app) instead of starting again from 0%. Expired YouTube links are refreshed by themselves.
- **Update notice:** once a day Fetchly asks GitHub whether a newer version is out and shows a small banner with a link to the download page. Turn it off in Settings → General.
- **Safer browser bridge:** the extension and the app now share a secret, so other programs on your computer can't send downloads to Fetchly. **After updating, open `chrome://extensions` and click ↻ on Fetchly.**

## 2.0.9

- **YouTube on Android,** up to 1080p with sound: paste or share a YouTube link (Shorts, youtu.be, watch …) and pick a quality. 720p and 1080p come as separate video and sound, which the phone joins after downloading — no re-encoding, full quality.
- **Other video sites on Android:** each video found on the page is listed with its quality and real size, biggest first; small preview clips are left out; videos written in the page's player settings are found too. Files are named after the page's title.
- **Android Add URL:** the save folder is shown in full (Download/Fetchly); no "save the page as HTML" for video sites; Download stays off after an error until the link changes; a clear message instead of an endless wait when there's no internet.
- Video names no longer end in "[NAp]" when a site doesn't say the height.

## 2.0.7

- **Fixed:** a stream link (`.m3u8`) pasted into Add URL or shared to Fetchly saved the playlist's text instead of the video. Now its qualities are listed and the video is saved.
- **Fixed:** videos from sites that don't say their height were named `… [NAp].mp4`. The quality tag is now left out when it isn't known.
- Tested on real Windows and Linux machines with every release: start, browser bridge, downloads, the `fetchly://` link, and videos through yt-dlp.

## 2.0.6

Fetchly 2 is a new app, rebuilt from the ground up so it runs everywhere.

- **Now on Windows, Linux and Android,** as well as Mac. Same features on every computer: multi-connection downloads, resume, the Chrome extension, and YouTube up to 4K.
- **Android:** add a link, or **Share → Fetchly** from any app. Files go to Download/Fetchly. (YouTube needs a computer; files and streams work on the phone.)
- **Smoother at high speed:** each download runs on its own thread, so the window never stutters, even above 400 MB/s.
- **Streams without ffmpeg:** HLS (`.m3u8`) streams that aren't encrypted are saved even when ffmpeg isn't installed.
- **Mac:** works on macOS 12 and later (was 14). Your download list from Fetchly 1 is kept.
- **Extension:** no more "Extension context invalidated" errors after the extension updates; an old tab asks you to reload the page instead.

## 1.0.7

- **Fixed:** in **Add URL**, the list of qualities was invisible (squeezed to zero height), so it looked like nothing happened. It now always shows.
- **Download** in Add URL uses the qualities already found and takes the best one, instead of searching again.
- The dialog says "Finding video qualities…" while it searches, and a pasted video-site link is searched as soon as the dialog opens.

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
