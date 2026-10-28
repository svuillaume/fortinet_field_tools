<div align="center">

# FortiBoothDemo

**Chrome extension — Fortinet demo videos on loop, full screen, one click.**

For booth laptops · kiosks · lobby displays · conference-room monitors

</div>

---

## What it is

FortiBoothDemo plays a playlist of Fortinet product-demo videos **back-to-back and full screen**, with a short, branded **intro slide** before each one.

You build the playlist from a settings page — paste a Fortinet video URL, the extension finds the embedded Vimeo or YouTube player on its own and generates an intro slide you can edit. Save, click **▶ Start**, walk away.

## Why it helps

| Without FortiBoothDemo | With FortiBoothDemo |
|---|---|
| Open each video page by hand | Playlist runs itself in one click |
| Sit through baked-in "Demo starts in…" intros | Clean 5-second branded intro before each video |
| Pick the next video every few minutes | Loops forever, in your chosen order |
| Different laptop = set everything up again | Export `.json` → Import `.json` → done |
| No way to add new videos without editing code | Paste URL → **Fetch & add** |

## Install (one-time)

1. **Unzip** `fortidemobooth.zip` somewhere permanent (not `Downloads`).
2. Open `chrome://extensions`.
3. Toggle **Developer mode** on (top-right).
4. Click **Load unpacked** → pick the unzipped folder.
5. Pin the icon from Chrome's puzzle-piece menu.

The icon is now in your toolbar. That's it.

---

## The 3-step flow

```
 Settings Save ▶ Launch
┌───────────────┐ ┌───────────────┐ ┌────────────────────┐
│ Paste URL → │ → │ Playlist saved│ → │ Full-screen loop │
│ Fetch & add │ │ in Chrome │ │ on video.fortinet │
│ Edit slide │ │ storage │ │ │
└───────────────┘ └───────────────┘ └────────────────────┘
```

### 1 · Build your playlist

Click the **FortiBoothDemo** icon → the settings page opens.

- Paste a Fortinet video URL into **Add a video** → click **Fetch & add**.
- The extension reads the page, finds the Vimeo or YouTube ID, generates an **intro slide** (title · one-sentence "what" · one-sentence "why in the public cloud").
- Edit any field inline. Reorder with ▲▼. Delete to remove.

### 2 · Save

Click **Save** to write the playlist to Chrome storage. Changes aren't persisted until you click Save.

Want a portable copy? **Export .json** downloads the playlist as a file. On another laptop, install the extension, open settings, **Import .json**, pick the file, done.

### 3 · ▶ Launch

Click **▶ Start demo loop** at the top. A new tab opens on `video.fortinet.com`, goes full screen, and starts the loop. Close the tab to stop.

---

## Example — build a 3-demo FortiCNAPP loop in under a minute

```
Icon → Settings
 ↓
Paste https://video.fortinet.com/products/lacework-forticnapp/2026/forticnapp-unified-risk-management
 ↳ Fetch & add
Paste …/forticnapp-alert-summarization
 ↳ Fetch & add
Paste …/forticnapp-alert-remediation
 ↳ Fetch & add
 ↓
Save
 ↓
▶ Start demo loop
```

Done — three FortiCNAPP demos playing full screen, each introduced by a 5-second slide, looping back to the first.

Want to add FortiClient (which the Fortinet library embeds via YouTube)? Paste its page URL, Save, launch — same workflow.

---

## ️ Controls while the loop runs

Move the mouse to the **top of the screen** for the control bar. It's also visible on every intro slide.

| Control / Key | What it does |
|---|---|
| **◀ Previous** / **Next ▶** · `←` `→` | Skip between demos |
| **Pause** / **Resume** · `Space` | Hold the current video or intro slide |
| **Fullscreen** · `Esc` | Toggle / leave full screen |
| **Sound** · `M` | Mute / unmute |
| **CC** · `C` | Captions on / off (only when the video has them) |

---

## Tips

- **Skip baked-in intros.** Set `Start seconds` on an entry to jump into the real content. For the Base Container Demo use `74` — the viewer never sees Fortinet's own "Demo starts in…" countdown.
- **Edit the intro text** for your audience — the "why in the public cloud" line is yours to rewrite per demo.
- **No captions on some videos?** Fortinet doesn't publish captions on every demo. CC can only enable what's actually there.
- **Keep two laptops in sync** by exporting from one and importing on the other. The `.json` is small and plain.

## Troubleshooting

| What you see | What to do |
|---|---|
| *Could not find a Vimeo or YouTube video on that page* | The URL isn't a video page. Open it in a browser first and confirm there's an embedded player. |
| A demo plays blank, or stops starting | Right-click the loop tab → **Inspect** → **Console** → run `__fl()` → send the output. |
| **Start demo loop** button disabled | Playlist is empty. Add at least one video, click **Save**. |
| Extension doesn't pick up a change | In `chrome://extensions`, click the circular **Reload** icon on the FortiBoothDemo card. |

---

<div align="center">

**Built for Fortinet sales booths. Works for any demo loop of Fortinet library videos.**

</div>
