# Clair Obscur - No-Spoiler Video Experience

A minimal, cinematic video player with no duration, no progress bar, and no scrubbing.
Experience a 7-hour journey with the uncertainty of not knowing when it ends.

## Controls

**Keyboard:**
- `Spacebar` → Play/Pause

**Mouse:**
- `Single Click` → Play/Pause
- `Double Click` → Fullscreen

## Setup

### 1. Split Your Video

Use FFmpeg to split the video at natural chapter breaks:

```bash
# Act 1 (0:00 to 2:47:00)
ffmpeg -i Clair-Obscur-Movie.webm -t 02:47:00 -c copy Act1.webm

# Act 2.1 (2:47:00 to 4:55:51)
ffmpeg -i Clair-Obscur-Movie.webm -ss 02:47:00 -t 02:08:51 -c copy Act2-1.webm

# Act 2.2 (4:55:51 to 6:01:10)
ffmpeg -i Clair-Obscur-Movie.webm -ss 04:55:51 -t 01:05:19 -c copy Act2-2.webm

# Act 3 (6:01:10 to end)
ffmpeg -i Clair-Obscur-Movie.webm -ss 06:01:10 -c copy Act3.webm
```

### 2. Create a GitHub Release

1. Go to your repository on GitHub
2. Click **Releases** → **Create a new release**
3. Tag: `v1.0`
4. Title: `Clair Obscur Video Files`
5. Upload all 4 video files:
   - `Act1.webm`
   - `Act2-1.webm`
   - `Act2-2.webm`
   - `Act3.webm`
6. Click **Publish release**

### 3. Update index.html with Release URLs

After publishing, get the direct download links for each file (right-click → copy link):
- `https://github.com/YOUR-USERNAME/YOUR-REPO/releases/download/v1.0/Act1.webm`
- And so on for the other acts

Update the video URLs in `index.html` accordingly.

### 4. Enable GitHub Pages

1. Make sure your repository is **Public** (Settings → Change visibility)
2. Go to **Settings → Pages**
3. Set source to your deploy branch and folder `/ (root)`
4. Click **Save**
5. Wait 2-3 minutes for deployment
6. Visit your Pages URL: `https://YOUR-USERNAME.github.io/YOUR-REPO/`

## Features

✅ **Seamless Multi-Part Playback** - Auto-transitions between acts with no interruption  
✅ **Auto-Save System** - Progress saved every 5 seconds and on pause  
✅ **Auto-Resume** - Picks up exactly where viewer left off (remembers both part and position)  
✅ **No Spoilers** - No duration, progress bar, or timeline visible  
✅ **Sleek Animations** - Visual feedback for play/pause actions  
✅ **Cinema Mode** - Cursor auto-hides during playback  

The viewer will never know there are multiple parts — it plays as one continuous video!

## Troubleshooting

**If the video doesn't load:**
- Repository must be **Public** for GitHub Releases to be accessible
- Hard refresh the page: `Cmd+Shift+R` (Mac) or `Ctrl+Shift+R` (Windows)
- Check browser console (F12) for errors
- Verify release files are accessible by visiting the direct URLs

**Why GitHub Releases instead of Git LFS?**
- GitHub Pages doesn't serve Git LFS files properly (only serves pointer files)
- GitHub Releases can host files up to 2GB each and stream them directly
- More reliable for video playback
