# No-Spoiler Movie Experience (GitHub Pages)

A minimal, theater-style webpage for long-form video playback where viewers cannot see:

- total duration
- progress bar
- playback controls
- scrubbing UI

The page shows a black background and plays the film full-screen after one click.

## Setup

1. Add your film file as `movie.mp4` in the repository root.
2. Push this repository to GitHub.
3. Enable **GitHub Pages** from the default branch root.
4. Share the Pages link.

## Notes

- Browsers require a user gesture before media playback, so there is a single **Start Film** button.
- The player intentionally hides controls and blocks common keyboard seek shortcuts.
- This is deterrence-focused UX, not DRM. A technically advanced user can still inspect source/network tools.
