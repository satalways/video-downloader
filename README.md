# Video Downloader for Windows

Download videos from YouTube, Facebook, and other supported sites. Version **0.2.8** for **64-bit Windows 10/11**.

This repository contains only the Windows setup installer and usage instructions. Source code is not included.

## Download and install

1. [Download VideoDownloaderSetup.exe](https://github.com/satalways/video-downloader/releases/latest/download/VideoDownloaderSetup.exe).
2. Double-click the setup file and follow the installation wizard. Installation is for your current Windows user and does not require administrator access. The default location is `%LOCALAPPDATA%\Programs\Video Downloader`.
3. Setup creates a **Video Downloader** shortcut in the Start menu. You can also select the optional desktop shortcut. Open the app from either shortcut; it opens maximized.
4. On first use, click **Install tools** inside the app and wait for installation to finish. Internet access is required to download yt-dlp, FFmpeg, FFprobe, and Deno. Tools are installed under your Windows user account without administrator access.

Setup includes the application and .NET runtime. No separate .NET installation or source files are needed. The first launch may take a few seconds while bundled runtime files are extracted. Download tools are installed separately by the app.

A [single-file portable app](https://github.com/satalways/video-downloader/releases/latest/download/VideoDownloader.exe) is also available. It supports automatic updates and keeps a backup of the previous executable.

## Update or uninstall

Before running setup again or uninstalling, right-click the app's tray icon and choose **Exit**. Clicking the window's **X** keeps the app running in the background. Setup and uninstall will ask you to close a running copy of this version.

Open **About** in the footer, press **F1**, or choose **About and updates** from the tray menu. **Automatically install app updates** is enabled by default. The app checks stable GitHub Releases at startup and every six hours, including when automatic installation is disabled. When a newer version is available, the About button highlights **Update available** and the app sends a Windows tray notification. About shows the available version, full update status, and **Check for updates**. Automatic installation verifies the download, waits until active downloads, analysis, and tool updates finish, then installs and restarts. Your settings, history, and paused queue are preserved. You can also use **View latest release** to download an update manually, or run a newer setup file. To remove it, open **Windows Settings → Apps**, find **Video Downloader**, and choose **Uninstall**. Uninstall removes the application and shortcuts while keeping your downloaded videos, settings, history, and installed download tools.

## About and GitHub

**About** includes a short application description, your installed version, the last successful update check, and links to the GitHub repository, release notes, and issue tracker. It shares live update status with the main window. Clicking a new-release tray notification opens About. Small About windows scroll to keep all controls accessible.

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

SHA-256 for `VideoDownloaderSetup.exe`:

```text
8FC217D35A28AF674618D5D7170D97A3011CA974F16505285B2621155E2DD62C
```

To check it in PowerShell, run `Get-FileHash .\VideoDownloaderSetup.exe -Algorithm SHA256` and compare the result above.
