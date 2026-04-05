# Explore

Experimental project space.

## Repository

- Remote: https://github.com/annar-bohn/explore
- Branch: `main`

## Workflow

- Clone/pull from remote before starting work: `git pull origin main`
- Push changes to remote after committing: `git push origin main`

## Current project: Wolfram Cellular Automata Flyover

Single-file app (`index.html`) — no dependencies.

### Architecture
- **Rendering**: Mode-7 style flat plane perspective (Canvas 2D), delta-time based animation
- **CA engine**: Elementary 1D cellular automata (rules 0-255), rows computed on demand via `getRow(absRow)` with `cellMap` cache
- **Frontier system**: CA rows computed progressively at constant `FRONTIER_SPEED` (rows/sec), independent of camera speed
- **Cells**: Drawn as perspective-correct trapezoid quads matching the grid, gridlines drawn on top

### Key constants
- `CAM_HEIGHT`, `HORIZON_FRAC`, `FOV` — camera/perspective
- `FRONTIER_SPEED` — CA row advance rate (rows/sec)
- `FLY_SPEED_MIN/MAX/STEP` — camera speed bounds

### Controls
- Arrow Up/Down: adjust camera fly speed (sluggish easing)
- Rule input + Fly button to start a rule
- Back button to return to intro
