# Rowing Interval Timer

A single-page interval timer for a 20-minute rowing boot camp workout, with an animated rower that moves at the target stroke rate so you can match it in real life.

**Live demo:** `https://YOUR-USERNAME.github.io/rowing-timer/`

## Features

- **Full 20-minute structure:** warm-up, power intervals, intensity intervals, and sprint intervals, each with its target strokes per minute (SPM).
- **Rowing animation synced to SPM:** a rower animation plays at the pace of the current interval (20, 22, 24, 26, 28 or 30 SPM), so you can row in time with it.
- **Fixed timer section:** the countdown, SPM, progress bar and controls stay at the top while the interval list scrolls and follows the current interval.
- **Controls:** Start / Pause / Resume, Skip, Back and Reset.
- **Audio cues:** short beeps for the last 3 seconds of each interval and a longer beep at each change (can be turned off).
- **Optional cooldown:** adds a 3-minute easy row at 18–20 SPM.
- **Screen wake lock:** asks the browser to keep the screen on while the timer is running (where supported).
- **Light and dark mode:** follows your device setting.

## Workout structure

| Phase | Time | Intervals |
|---|---|---|
| Warm-up | 2 min | 1 min @ 20 SPM, 1 min @ 22 SPM |
| Power intervals | 6 min | 2 min @ 24 SPM, 1 min @ 22 SPM, 2 min @ 26 SPM, 1 min @ 22 SPM |
| Intensity intervals | 8 min | 4 × (1 min @ 28 SPM, 1 min @ 22 SPM) |
| Sprint intervals | 4 min | 3 × (30 sec @ 30 SPM, 30 sec @ 22 SPM), then a final 30 sec @ 30 SPM |
| Cooldown (optional) | 3 min | Row gently at 18–20 SPM |

## Usage

Open the page and press **Start**. No installation, build step or dependencies are needed.

To run it locally, download `index.html` and open it in any modern browser.

## Hosting on GitHub Pages

1. Put `index.html` at the root of the repository.
2. Go to **Settings → Pages**.
3. Set the source to **Deploy from a branch**, choose `main` and `/ (root)`, and save.
4. After a minute or two the timer is live at `https://YOUR-USERNAME.github.io/REPO-NAME/`.

## Project structure

```
.
├── index.html   # the whole app: HTML, CSS, JavaScript and embedded GIFs
└── README.md
```

Everything lives in one self-contained file. The six rowing GIFs are embedded as base64 data, so the file is about 5.5 MB.

## How the animation sync works

Each GIF is one full rowing stroke, timed so that one loop equals 60 ÷ SPM seconds (for example, 3 seconds at 20 SPM and 2 seconds at 30 SPM). When an interval starts, the page swaps in the GIF for that interval's SPM, so the animation restarts at the beginning of the stroke. When the timer is paused or reset, a still image of the first frame is shown.

The cooldown uses the 20 SPM animation.

## Credits

The workout structure is based on the 20-minute "Boot Camp Sweat" session by Laine on Hydrow. This is an unofficial personal project and is not affiliated with or endorsed by Hydrow.
