# HACKER ANKIT — Video Studio

A local-first, full-window video editing workstation with laptop-style app chrome, an animated HACKER अंकित launch screen, and browser-native editing tools. There is no account, server upload, API key, subscription, credit system, or watermark. Imported media stays in the browser. The editor uses IndexedDB for local media and localStorage for project metadata.

## Run locally

Open `index.html` directly in a recent browser. Most editing features work from a local file. Browser security may limit microphone access and PWA installation when opened this way. For full PWA support, publish it with GitHub Pages (or use any static file host). No build step or package manager is needed.

## Publish from a computer

1. Create a new public GitHub repository.
2. Upload the contents of this folder (keep `index.html` at the repository root) and commit them to the `main` branch.
3. In the repository, open **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, then save.
5. Open the Pages URL GitHub displays. The first deployment can take a few minutes.

## Publish from a phone

1. Create a repository on GitHub in the mobile browser.
2. Open the repository, choose **Add file → Upload files**, and upload all project files and the `icons` folder. Keep the files at the root; do not upload an enclosing project folder.
3. Commit the upload to `main`.
4. In **Settings → Pages**, select **Deploy from a branch**, `main`, and `/ (root)`, then save.
5. Open the URL GitHub Pages provides. If uploading the complete folder from a phone is inconvenient, use GitHub's browser editor to add each file and create `icons/icon.svg` in the `icons` directory.

## What works locally

- Video, image, GIF (when supported), and audio import; multiple files; local media library.
- Video and image clips on the video lane, audio clips on the audio lane, text overlays on the text lane, drag to reorder/move, edge handles to trim, snapping, split at the playhead, duplicate, delete, clip speed from 0.1× to 10×, volume with fade in/out, mirror/rotate, crop edges, contain/fill, background color, and an explicitly experimental green/blue chroma-key cutout (not AI).
- The timeline toolbar exposes Filter, Trim, FX, Split, Duplicate, Delete, Speed, Volume, Crop, Rotate and Fit. Split, Duplicate and Delete use the selected clip or the clip beneath the playhead; successful actions confirm completion.
- Browser video/image preview with Play/Pause below the monitor, frame-step buttons, click-and-drag timeline scrubbing, text/title/subtitle overlays, color filter adjustments, and 110 distinct local filter/effect presets across 22 categories: basic, beats, glitch, RGB, blur, spin, drop shadow, zoom, retro, cinematic, color, neon, cyberpunk, warm, cool, motion, noir, light, festival, nature, pastel, and contrast.
- Save project metadata and media to this browser, local profile name and preferences, plus project JSON export/import. Source media remains separate from the project JSON; re-import the original files if they are not in this browser's local store.
- Local WebM rendering through Canvas capture and MediaRecorder where supported. The render includes the video/image sequence, filter looks, transforms, text overlays with 26 system font choices, 20 style presets, outline/shadow controls, and entrance animations, and local audio tracks where browser recording supports mixed audio.
- Local audio track playback/mix, device speech synthesis with installed voice selection and rate/pitch controls, and microphone recording where available and permitted.
- Installable app shell and offline caching of the static editor files after its first successful load.

## Browser limits

MediaRecorder's codecs vary by browser. WebM is the practical fallback; MP4 appears only when the browser advertises MP4 recording support. Export renders in real time and is limited by device memory, performance, supported codecs, and clip duration. Advanced transitions between clips, keyframe interpolation, reverse playback, semantic AI background removal, speech-to-text, and neural TTS are not implemented. The experimental cutout is a simple green/blue chroma-key tool and works best with an evenly colored background; it is not semantic subject removal. Visual filter looks, crop, mirror/rotate, scale, basic fades, contain/fill modes, and local text effects apply in the local export. The audio panel uses local files and never downloads commercial/world music; bring audio you have rights to use. The device voice feature is browser speech synthesis, not cloud AI. Large media may exceed local browser storage. The interface reports unsupported media/export cases instead of claiming those operations succeeded.

## Quick check list

- Open the page and press **EDIT VIDEO**.
- Import a supported local video and confirm preview/playback.
- Add an image or audio file; select clips and try split, duplicate, delete, reorder, and zoom.
- Add a title, adjust its text/color/size, and move the playhead through its duration.
- Change a color preset and inspect the preview.
- Save, refresh, and confirm the browser-local project is restored; export and re-import its JSON.
- Render a short WebM and play the downloaded file.
- Publish with GitHub Pages, load once online, then try re-opening the editor offline.

## Files

```text
index.html
styles.css
app.js
manifest.json
sw.js
icons/icon.svg
README.md
```
