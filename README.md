# Çarşı Kaçışı (Bazaar Escape)

A 3D rooftop runner over the domes of a covered bazaar in Istanbul. You are a young apprentice chasing the cat that stole a ring from the jeweller. Ten hand-built levels, a roof map, three stars per level, and a synthesised darbuka-and-clarinet loop.

Built by Claude Haiku 5.5 with Claude Code from one prompt: [prompts/carsi-kacisi.md](prompts/carsi-kacisi.md)

![Title](docs/01-title.png)

## Play

Run any static server in this folder, for example `python -m http.server 8000`, and open `http://localhost:8000/`. The game loads Three.js r170 from `cdn.jsdelivr.net`, so it needs an internet connection. If the engine cannot load, the title screen says so and Play stays disabled.

- Run along the roofs, jump, and jump again in the air once.
- Slide down the far side of a dome (it gets fast), grab a laundry line and ride it.
- Step up onto ledges up to 0.45 units high; higher ones need a jump.
- Falling into the street sends you back to the last checkpoint.
- Collect the lokum (Turkish delight) along the way. The cat runs about ten units ahead with the ring; catch it where it stops at the end of each level.
- Stars: finish within the target time, collect 80% of the lokum, and never fall.
- Levels 1 to 10 unlock in order. Finishing level 10 returns the ring to the jeweller.

![Gameplay](docs/02-gameplay.png)

## Controls

| Action | Keyboard | Touch |
|---|---|---|
| Move | `WASD` or arrow keys | Virtual stick (bottom left) |
| Jump (press again in the air for a second jump) | `Space` | Jump button |
| Slide | `Shift` | Slide button |
| Turn the camera | Mouse drag | Drag on the screen |
| Pause | `P` or `Esc` | Pause icon |
| Music on/off | `M` | Sound icon |
| Effects on/off | `X` | Sound icon |
| Language TR / EN | `L` | Language button |
| Fullscreen | `F` | Settings |

Every button can be reached with the keyboard, and touch targets are at least 44 px.

## Level map and results

![Roof map](docs/04-roof-map.png)

![Result](docs/03-result.png)

The levels are one table (`LEVELS` in `index.html`). Each level is a short layout string such as `R12 C G3 O12 M4 B8 L5 W10 Z`: roofs, gaps, domes, sliding planks, breaking tiles, laundry lines, gust zones, checkpoints, and the cat at the end. The comment above the table lists every token.

Target time is the level length in units divided by 5.

## Night levels

Levels 8 and 9 run at dusk. Pigeons sit on the roofs and flap away as you pass, and now and then a small flock crosses between the camera and the runner.

![Night](docs/06-night.png)

## Phone

![Phone](docs/05-phone.png)

## URL flags

| Flag | Effect |
|---|---|
| `?lang=en` / `?lang=tr` | Start in English or Turkish |
| `?low` | Low quality: no shadows, half the particles, pixel ratio 1 |
| `?debug` | Show fps, draw calls, the mode, and any JavaScript errors |
| `?auto` | The built-in bot plays through all ten levels (same rules as a player) |
| `?sim=N` | Start level 1 and fast-forward N game seconds before the first frame |
| `?noassets` | Accepted for consistency. The game ships no assets, so it changes nothing |

Test hooks: `window.carsi` exposes the live state (mode, level, time, lokum, falls, player position), and `window.carsiSim(seconds)` fast-forwards the simulation without rendering.

## Saved data

Settings are saved under `arena.carsi.settings`, progress under `arena.carsi.save`, and the best result per level under `arena.carsi.best` in `localStorage`. Storage errors are caught, so the game still runs without it.

## What was verified

- A bot pass with `?auto` clears all ten levels with zero falls, reaches the ending, and logs no JavaScript errors (headless Chromium). The bot takes 44 to 57 seconds of game time per level.
- Frame rate in headless Chromium on the development laptop: 60 fps with 50 draw calls during play on level 1. The Intel UHD 620 target was not measured on hardware.
- Night flock: up to three pigeons on screen at once, confirmed by counting in the running game.
- Screenshots above were taken from the running game. The touch layout was checked in a separate emulated-phone screenshot that is not in `docs/`.

## Known limits

- Human run times were not measured. The bot takes 44 to 57 seconds per level. The levels are linear, with no branching routes.
- The cat is small on screen at the default camera distance.
- The synthesised music and effects were not listened to. They are generated with Web Audio and should be checked by ear.
- Touch controls were checked with device emulation only, not on a real phone.
- The game pauses when the tab is hidden. Headless screenshots can trigger that pause too.
- Loading from `file://` was not tested.

## Credits and license

Code, level design, models, and sounds are original and built in code. The only external code is Three.js r170 (MIT), loaded from jsdelivr. No third-party assets are used.

Licensed under the MIT License. See [LICENSE](LICENSE).
