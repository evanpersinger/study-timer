# Study Timer

A Pomodoro-style study timer built with Python and tkinter, with an optional 40Hz binaural beat and local daily session tracking.

## Features

- Two presets: 25 min study / 5 min break, 50 min study / 10 min break
- Dual display: current countdown on the left, next session length on the right
- 40Hz binaural beat plays during study sessions and stops when they end. The "40hz Beat: On/Off" button (top right) toggles it, even mid-session
- Manual control: nothing auto-starts, you click Start Break and Start Study yourself
- Session tracking: partial sessions count as decimals (0.5 is half a session) alongside total study time
- Daily data saved locally to `data/data.json`, reset each day with history kept (format in [data/README.md](data/README.md))
- Test mode: 5-second timers, enabled by uncommenting the TEST button in `study_timer.py`

## Requirements

- Python 3.9+, [uv](https://docs.astral.sh/uv/), and tkinter (included with most Python installs)
- The beat plays on macOS (`afplay`) and Linux (`paplay`), not Windows yet. Notification sounds work on all three

## Run

```bash
cd study-timer
cp data/data_example.json data/data.json   # first time only
uv run study_timer.py
```

## How to use

1. Pick a preset and click Start
2. When the study timer ends, a sound plays until you click Stop or Start Break
3. When the break ends, a sound plays until you click Start Study
4. Pause holds the timer. Reset starts over, and the partial study time still counts

## Troubleshooting

- **Beat not playing?** `binaural_beat.mp3` must be in the project root and the toggle must say On
- **GUI not appearing?** Check tkinter with `python -m tkinter`
- **No audio on Linux?** `sudo apt-get install pulseaudio-utils`
