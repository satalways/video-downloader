# Video Downloader for Windows

Download videos from YouTube, Facebook, and other supported sites. Version **0.2.3** for **64-bit Windows 10/11**.

This repository contains only the Windows executable and usage instructions. Source code is not included.

## Download and open

1. [Download VideoDownloader.exe](https://github.com/satalways/video-downloader/raw/refs/heads/main/VideoDownloader.exe).
2. Save it somewhere convenient and double-click it. The app opens maximized.
3. On first use, click **Install tools** inside the app and wait for installation to finish. Internet access is required to download yt-dlp, FFmpeg, FFprobe, and Deno. Tools are installed under your Windows user account without administrator access.

The executable includes the .NET runtime. No separate .NET installation, companion DLLs, or source files are needed. The first launch may take a few seconds while bundled runtime files are extracted. Download tools are installed separately by the app.

## Download videos

1. Paste one or more video links, separated by spaces or new lines.
2. Click **Analyze links**, or press **Ctrl+Enter**.
3. Choose the videos to download, a resolution, and an output format:
   - **Original quality** preserves the selected source codecs; separate audio/video streams may be merged into MKV.
   - **Windows-compatible MP4** converts incompatible media when needed.
   - **MP3** saves audio only.
4. Use **Change folder** to choose where to save your files.
5. Click **Download**. The queue starts automatically and downloads videos one at a time. If another download is running, the new videos wait their turn.

For playlists, paste a playlist link, click **Load playlist**, select its videos, then click **Analyze selected videos** before downloading.

Use **Pause queue** to prevent the next video from starting; the current download continues. Use **Cancel** to stop an individual download and **Retry** to try again. History provides **Play**, **Show file**, search, and status filters. **Remove from history** keeps the downloaded file.

## Keep downloading in the background

- Clicking the window's **X** hides the app in the Windows notification tray. Downloads continue in the background.
- Double-click the tray icon, or right-click it and choose **Open Video Downloader**, to restore the window. The icon may be inside the tray's hidden-icons menu.
- To quit completely, right-click the tray icon and choose **Exit**. This stops active work and saves interrupted/waiting downloads for the next launch.
- After restarting, the saved queue is paused. Use **Resume queue** for waiting jobs or **Resume all** to include interrupted jobs. Partial downloads resume when the source supports it.

## Tools, settings, and help

- Click **Update tools** to update download dependencies. Finish the active download and pause the queue first.
- Settings, history, and managed tools are stored in `%LOCALAPPDATA%\VideoDownloader`. Downloaded media stays in your selected folder.
- If a download fails, follow the app's recovery message. **Copy diagnostics** provides details you can include in a [GitHub issue](https://github.com/satalways/video-downloader/issues).
- Supported sites can change. Sign-in/cookies, DRM-protected media, and live recording are not supported. Download only content you have permission to save.

## Verify your download

SHA-256 for `VideoDownloader.exe`:

```text
65C01388F81A908885FA9B65853794BC5CDDB1C999C76296F943E3E8CB2F354A
```

To check it in PowerShell, run `Get-FileHash .\VideoDownloader.exe -Algorithm SHA256` and compare the result above.
