# Super Pixel Bros

[![Play it live](https://img.shields.io/badge/PLAY-LIVE-%23ffd23e?style=for-the-badge)](https://nwfella.github.io/super-pixel-bros/)

A faithful, Mario-inspired side-scrolling platformer in a **single self-contained HTML file** — procedural pixel art, synthesized chiptune sound, zero dependencies, zero network requests. Open it, press Start, jump.

## Features

- **Tight platformer physics** — acceleration + friction, variable jump height (tap vs. hold, classic release-cut), coyote time, jump buffering
- **Classic level design** — two full worlds (Green Hills → Cavern Deep), gaps, pipes, stairs, brick rows, mystery blocks, coin arcs
- **Enemy AI** — Goombas patrol and turn at platform edges; stomp to squash (+100), touch from the side and you lose a life. Spinies can't be stomped — jump *around* them
- **Power-ups** — Mushroom grows you big (break bricks, survive one hit); Star grants invincibility + **2× score multiplier** with a draining timer
- **Faithful details** — big Mario bonks shrink instead of dying, 1-UPs at 10,000 points and 100 coins, flag-pole finish with time bonus, blink-warning timer under 60s
- **Complete game loop** — HUD (score / coins / lives / time), level clear → next world → victory screen, game over with restart
- **Input everywhere** — keyboard (←→ / WASD / Space) + touch buttons on mobile, pause (P), mute (M)

## How to play

| Action | Key |
|---|---|
| Move | `←` `→` or `A` `D` |
| Jump (hold = higher) | `Space` `↑` `W` |
| Pause | `P` / `Esc` |
| Mute | `M` |

Stomp enemies from above. Hit `?` blocks from underneath. Grab the mushroom. Don't run out of time.

## Tech stack

- HTML5 Canvas 2D — fixed-timestep (60 Hz accumulator) game loop
- Hand-authored 16×16 pixel-grid sprites pre-rendered to offscreen canvases
- Web Audio API — all SFX + a looping chiptune bassline synthesized in code, no audio files
- Classic tile-grid levels built from a compact level spec (gaps, pipes, stairs, spawns)

## Verification

Shipped with a 54-assertion deterministic test harness (`spb_test.js`, headless Node with DOM/canvas stubs) covering physics, collisions, power-ups, scoring, and the full game-over → victory state machine — plus a browser render self-test that samples live canvas pixels.

*Single file, ~54 KB. Works offline. Open it in any modern browser.*
