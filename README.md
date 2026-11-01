# aoe2-squire-data

Test data for [aoe2-squire](https://github.com/chris-h-sg/aoe2-squire): screen recordings
and full frame sets of recorded Age of Empires II: DE games. They are too large for the
main repository. The main repository keeps each game's replay, telemetry CSV, a few
fixture frames and the expected results under `test_bench/` (see its `README.md`).

The data lives in **release assets**, not in git: one release per recording batch.

```bash
gh release download <tag> -R chris-h-sg/aoe2-squire-data
```

## Releases

| Release | Game | Assets |
|---|---|---|
| [`sample-games-2026-11`](https://github.com/chris-h-sg/aoe2-squire-data/releases/tag/sample-games-2026-11) | Game 1 (2026-11-01): live vs AI, Britons, QS Arabia, Normal speed, 1920x1080; `test_bench/game1-castle-vs-ai.*` in aoe2-squire | `telemetry_20261101_110257.mkv` (screen recording, 30 fps H.264, ~18 min), `telemetry_20261101_110257.video.json` (ffmpeg and match start times, to align the video with the CSV), `telemetry_20261101_110257_frames.zip` (all masked resource-panel frames saved by `--record-frames`, with `frames.csv`) |
| [`sample-games-2026-11`](https://github.com/chris-h-sg/aoe2-squire-data/releases/tag/sample-games-2026-11) | Game 2 (2026-11-01): live vs AI, Vikings, QS Arabia, Fast speed with three pauses and a late capture start, 1920x1080; `test_bench/game2-fast-pauses.*` in aoe2-squire | `telemetry_20261101_131446.mkv` (~12.5 min, cut 2.4 s before the end of the recording, which showed the desktop after an alt-tab), `telemetry_20261101_131446.video.json`, `telemetry_20261101_131446_frames.zip` (without the frame saved at match end, for the same reason; `frames.csv` still lists it) |
| [`sample-games-2026-11`](https://github.com/chris-h-sg/aoe2-squire-data/releases/tag/sample-games-2026-11) | Game 3 (2026-11-01): game 2's replay played back at regular, 4x and 8x speed with a pause, 75% UI scale; `test_bench/game3-playback-75ui.csv` in aoe2-squire | `telemetry_20261101_170101.mkv` (~4 min; a black box covers a desktop window and the alt-tab switcher from 6.9 s to 21.7 s, timeline unchanged), `telemetry_20261101_170101.video.json`, `telemetry_20261101_170101_frames.zip` |

To find a CSV row or sanity report finding in the video, use `tools/align_video.py` in
aoe2-squire. Frame file names are the `timestamp_ms` of their CSV row.
