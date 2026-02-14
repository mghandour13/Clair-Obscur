# Clair Obscur - No-Spoiler Video Experience

A minimal, cinematic video player with no duration, no progress bar, and no scrubbing.
Features seamless multi-part playback and a video game-style save system.

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

### 2. Upload to GitHub

Place all 4 video files in your repository root:
- `Act1.webm`
- `Act2-1.webm`
- `Act2-2.webm`
- `Act3.webm`

Use **Git LFS** for large files:
```bash
git lfs install
git lfs track "*.webm"
git add .gitattributes
git add Act1.webm Act2-1.webm Act2-2.webm Act3.webm
git commit -m "Add video parts with LFS"
git push
```

### 3. Enable GitHub Pages

1. Go to **Settings → Pages**
2. Set source to your deploy branch and folder `/ (root)`
3. Open your Pages URL and hard-refresh once (`Ctrl+Shift+R`)

## Features

✅ **Seamless Multi-Part Playback** - Auto-transitions between acts with no interruption  
✅ **Auto-Save System** - Progress saved every 5 seconds and on pause  
✅ **Auto-Resume** - Picks up exactly where viewer left off (remembers both part and position)  
✅ **No Spoilers** - No duration, progress bar, or timeline visible  
✅ **Sleek Animations** - Visual feedback for play/pause actions  
✅ **Cinema Mode** - Cursor auto-hides during playback  

The viewer will never know there are multiple parts — it plays as one continuous video!

## If it still does not play

- Confirm all 4 files exist in the same branch selected in Pages settings
- Wait 1-2 minutes for Pages deployment after pushing
- Verify Git LFS is properly tracking the .webm files
- Check exact filename casing: `Act1.webm`, `Act2-1.webm`, `Act2-2.webm`, `Act3.webm`
- Try a hard refresh: `Ctrl+Shift+R` (Windows) or `Cmd+Shift+R` (Mac)
