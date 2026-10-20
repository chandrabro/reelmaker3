# Text Video Studio (all in your browser)

Make 9:16 animated text-explainer videos. Everything happens on the website: edit, add your voice, preview, export MP4.
No terminal, no GitHub rendering.

## One-time setup
1. Upload this project to a GitHub repo (repo page → *Add file → Upload files*, or `git push`).
2. vercel.com → *Add New → Project* → import the repo → **Deploy**. Open your Vercel link.

## Making a video
1. **Scenes** (right side): edit the headline (wrap words in `[[ ]]` to colour them), chip text, theme, duration, visual type.
2. **Items / bullets**: each item has an **Appears at** box (seconds from scene start; blank = automatic).
   - Tip: play the preview, pause where your voice says the item, press **⏱** – the time is filled in for you.
3. **Voice-over**: click **🎙 Choose audio file** and pick your recording (mp3/wav/m4a). It plays in the preview.
   Adjust scene durations / item times until text matches your voice.
4. **Export**: click **🎬 Export MP4**, wait for 100% (keep the tab open), then **Save video**.
5. **Save your work**: **Download project.json** keeps all text/timings. **Import** loads it again.
   (The audio file is not inside project.json – pick it again.)

## Tips
- Use desktop **Chrome or Edge**. Other browsers may produce .webm instead of .mp4 (you'll see a note).
- A 60 s video takes roughly 1–3 minutes to export, depending on your PC.
- The editor autosaves in this browser, but only project.json is a real backup.

## Customising (code)
| What | Where |
|---|---|
| Colours / backgrounds | `src/themes.ts` |
| Font | `src/fonts.ts` |
| Layout, animation | `src/Video.tsx`, `src/Headline.tsx`, `src/Visual.tsx` |
| New visual type | component in `src/Visual.tsx` + case in `VisualView` + option in `src/Studio.tsx` |

Browser export supports a limited set of CSS (no radial gradients, no CSS-triangle tricks, no z-index) – keep new designs to simple shapes, linear gradients, rounded boxes and shadows.

## Optional: render on a computer instead
`npm install` then `npm run render -- projects/example.json` → `out/example.mp4`.

## Licence note
Remotion is free for individuals and companies up to 3 people; bigger companies need a licence (remotion.pro).
