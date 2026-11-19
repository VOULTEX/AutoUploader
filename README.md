# AutoUploader 🚀: schedule your YouTube Shorts 24/7

**Connect your channel → drop a ZIP of clips → AutoUploader schedules them.**
Every Short gets its own title, description and hashtags, and YouTube publishes them around the clock (e.g. one every 45 minutes), even after you close the page.

- 📦 **ZIP or video files**: MP4 / MOV / WebM. If a `.txt` / `.srt` with the same name sits next to a clip (Clip Vortex exports these), its words are used to write the title.
- ✍️ **A different title, description and hashtag mix for every Short**: built-in writer (English, Hinglish or Hindi styles), or ✨ **AI writing** with a free Gemini API key. Edit anything, or press 🔀 for a new version.
- 📅 **Scheduling**: first post time, one every 15 min to 6 h, a daily posting window, and a max per day.
- ⚙️ **Settings on every upload**: category, "made for kids" declaration, AI-content disclosure, language, playlist, and subscriber notifications (off by default).
- 🔁 **Remembers everything**: close the tab and it continues where it stopped next time you open it. It handles YouTube's daily quota (waits for the reset) and expired logins.
- 🔒 **No server**: it runs entirely in your browser and talks only to Google/YouTube. Free to host on GitHub Pages.

---

## How the "24/7" part works

AutoUploader uploads each clip to YouTube **as a scheduled video** (private, with a publish time). YouTube's own scheduler then makes each one public at its time. So:

1. Keep the page open **only while it uploads** (the "waiting to upload" counter shows how many are left).
2. Once everything is uploaded, close it. YouTube posts the Shorts on schedule by itself.

Example: a ZIP of 40 clips at one every 45 minutes uploads in a few minutes, and YouTube posts them over the next 30 hours.

---

## Put it on GitHub (3 minutes)

1. Create a **public** repository named `autouploader`.
2. Upload these files (`index.html`, `README.md`, `.nojekyll`, `LICENSE`).
3. Go to **Settings → Pages**, choose **Deploy from a branch → `main` / root**, and save.
   Your site will be at `https://YOUR-NAME.github.io/autouploader/`.

## Connect your YouTube channel (one time, ~10 minutes)

1. Open **console.cloud.google.com** and create a project (e.g. "AutoUploader").
2. **APIs & Services → Library**: enable **YouTube Data API v3**.
3. **OAuth consent screen**: choose **External**, enter an app name and your email, and add the Google account that owns your channel as a **Test user**.
4. **Clients → Create client**: type **Web application**. Under **Authorized JavaScript origins**, add `https://YOUR-NAME.github.io` (the page shows the exact value).
5. Copy the **Client ID** into AutoUploader and click **Connect**. Google says the app isn't verified; it's your own app, so continue.

> Google access lasts about an hour. If a long upload batch runs past that, AutoUploader shows **"Continue uploading"**. One click and it carries on.

## ⚠ Read before posting for real

- **Google's audit, required for public videos:** YouTube forces every video uploaded through an *unaudited* Google Cloud project to **private**, and those videos stay locked (no appeal). Submit the free **"YouTube API Services – Audit and Quota Extension"** form for your project and wait for approval. **Test with 1–2 clips until then.**
- **Daily limits:** each Google project gets **100 API uploads per day** (AutoUploader stops at 90). YouTube also has an unpublished **per-channel daily upload limit** that grows with channel history and verification. When a limit is hit, AutoUploader waits and continues.
- **Every 45 minutes = 32 Shorts per day.**
- **Stay within YouTube's policies:** upload only clips you own or have permission to use (re-uploads of other people's content can get copyright strikes or "reused content" demonetization), and keep titles honest. Misleading clickbait and mass-posting near-identical videos break YouTube's spam policies and can hurt your channel.

## Optional: AI-written titles
Get a free API key at **aistudio.google.com**, switch on **✨ Write with AI**, and paste the key. It stays in your browser. If the AI fails, the built-in writer is used automatically.

MIT licensed.
