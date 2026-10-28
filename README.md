# FortiBoothDemo

A Chrome extension that plays Fortinet product-demo videos back to back, full screen, with a short intro slide before each one — the kind of unattended loop you want running on a booth laptop, a kiosk display, a lobby screen, or a shared conference-room monitor.

## What it does

- Opens one tab on video.fortinet.com and plays your chosen Fortinet demo videos in order.
- Shows a 5-second **intro slide** before each video (title, one-line description, "Why it matters in the public cloud").
- Plays full screen, with sound and captions on when the video has them.
- Keeps looping — after the last video it goes back to the first.
- Works with both Vimeo and YouTube videos (the Fortinet library uses both).
- Lets you build and save your playlist from a settings page — no code to edit.

## How it helps

Running demos at a booth, in a meeting room, or on a dashboard is normally a bunch of clicks: open the page, hit play, sit through the baked-in "Demo starts in..." intro, wait for the end, pick the next one. FortiBoothDemo turns that into one click:

- One **click** → playlist runs full screen, forever.
- One **place** to curate the playlist (add, remove, reorder, edit intro text).
- One **export file** so the same playlist can move to another laptop in seconds.
- You can **pause**, **resume**, **skip**, **mute** and **toggle captions** from on-screen controls or the keyboard.

## Install (one-time)

1. Unzip `forticnapp-demo-loop-extension-v3.zip` somewhere permanent on your laptop (not Downloads — Chrome needs the folder to stay where you point it).
2. Open `chrome://extensions`.
3. Turn on **Developer mode** (top-right toggle).
4. Click **Load unpacked** and pick the unzipped folder.
5. Pin the FortiBoothDemo icon from Chrome's extensions menu so it stays visible in the toolbar.

That's it. The icon is now one click away.

## Three-step workflow

### 1. Build your playlist

Click the **FortiBoothDemo** icon. Chrome opens the settings page.

In **Add a video**, paste a Fortinet video page URL — any page under `https://video.fortinet.com/...` with an embedded Vimeo or YouTube player — and click **Fetch & add**. The extension reads the page, finds the video, pulls the title, and generates an intro slide for it (title, one-sentence "what", one-sentence "why in the public cloud"). Edit any field inline if you'd like different wording.

Reorder with ▲/▼. Remove with **Delete**.

### 2. Save

Click **Save** at the bottom. This writes the playlist to Chrome storage. If you close the tab without saving, your changes are lost.

Want a copy you can move or back up? Click **Export .json** — the file downloads with the full playlist. On another laptop, install the extension, open the settings, click **Import .json**, pick the file.

### 3. Launch

Click **▶ Start demo loop** at the top. A new tab opens on video.fortinet.com, the loop takes over the tab, goes full screen, and starts playing your playlist. Press **Esc** to leave full screen. Close the tab to stop.

## Example — set up a 3-video FortiCNAPP demo in under a minute

1. Click the FortiBoothDemo icon → settings page opens.
2. Paste `https://video.fortinet.com/products/lacework-forticnapp/2026/forticnapp-unified-risk-management` → **Fetch & add**.
3. Paste `https://video.fortinet.com/products/lacework-forticnapp/2026/forticnapp-alert-summarization` → **Fetch & add**.
4. Paste `https://video.fortinet.com/products/lacework-forticnapp/2026/forticnapp-alert-remediation` → **Fetch & add**.
5. Click **Save**.
6. Click **▶ Start demo loop**. The booth is now playing a three-demo FortiCNAPP loop full screen, with a 5-second intro slide before each demo.

To add FortiClient to the mix later, paste its page URL (e.g. `https://video.fortinet.com/products/forticlient/7.4/forticlient-standalone`) — the extension picks up that it's a YouTube embed and plays it the same way. Save, launch.

## Controls while the loop is running

Move the mouse to the top of the screen for the control bar; it also appears on every intro slide.

- **◀ Previous** / **Next ▶** — skip to the previous or next demo
- **Pause** / **Resume** — holds the current video or intro slide
- **Fullscreen** — toggle full screen (Esc also leaves)
- **Sound** — mute / unmute
- **CC** — captions on / off (only works for videos that have published captions)

Keyboard shortcuts: `←`/`→` skip, `Space` pause/resume, `M` mute, `C` captions, `Esc` leave full screen.

## Tips

- Add a `Start seconds` value to a video entry to skip its baked-in intro. For the FortiCNAPP Base Container Demo, `74` jumps straight to 1:14 and the viewer never hears the "Demo starts in..." baked-in countdown.
- If a video has no captions (some demos don't), the CC button has nothing to turn on — that's not a bug, Fortinet just didn't publish captions for that one.
- The intro slide text and the "why" line are editable per demo on the settings page — use whatever wording fits your audience.

## Troubleshooting

- **"Could not find a Vimeo or YouTube video on that page."** The page doesn't appear to embed a supported player. Check that the URL you pasted is a video page on `video.fortinet.com`, not a product landing page.
- **A demo plays blank or stops starting.** Right-click the loop tab, pick **Inspect**, open the **Console** tab, run `__fl()`, and send me the output.
- **The Start button is disabled.** The playlist is empty. Add at least one video and click **Save**.
- **The extension version is in `chrome://extensions`**. Reload after each update: find the FortiBoothDemo card and click the circular refresh icon.
