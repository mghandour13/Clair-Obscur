# No-Spoiler Movie Experience (GitHub Pages)

This repository is a full-screen “private cinema” page for a single video.

What the viewer can do:
- ✅ Pause
- ✅ Play

What the viewer cannot do:
- ❌ See duration
- ❌ See progress bar
- ❌ Scrub forward/backward
- ❌ Skip with keyboard shortcuts

It also resumes from the last watched point if the tab/browser is closed.

---

## What **you** need to do (only once)

### 1) Put your video in the repo
Place your file at the repository root and name it exactly:

`M4V00943.MP4`

> You said you only want to add the file yourself. That is the only required content step.

### 2) Push to GitHub
If this repo is local only, connect it to GitHub and push:

```bash
git remote add origin https://github.com/<your-username>/<your-repo>.git
git push -u origin <your-branch>
```

### 3) Enable GitHub Pages
In GitHub:
1. Open the repository.
2. Go to **Settings** → **Pages**.
3. Under **Build and deployment**:
   - **Source**: `Deploy from a branch`
   - **Branch**: your default branch (usually `main`) and folder `/ (root)`
4. Save.

After ~1–2 minutes, your page URL is live (for example):

`https://<your-username>.github.io/<your-repo>/`

### 4) Send the link
Share only that link. The page starts with a single **Start Film** button.

---

## Playback behavior implemented

- Full-screen black theater style.
- No native controls shown.
- Only pause/play action is allowed (button, click on video, or space/k key).
- Seeks are blocked (both forward and backward).
- Playback position is saved to `localStorage` and resumes on reopen.
- Playback speed is forced to 1x.

---

## Important limitation (honest note)

This is strong UX deterrence, not DRM.
A technically advanced person can still inspect developer tools/network traffic.
For stronger privacy, host `M4V00943.MP4` behind expiring signed URLs instead of fully public static hosting.
