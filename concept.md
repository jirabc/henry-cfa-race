# Henry's CFA Race — Game Concept

## Overview
A mobile-first browser racing game built for Henry. Chick-fil-A themed dirt oval track racer with tap-to-steer controls.

## Gameplay
- Player drives a red CFA-branded racecar around a dirt oval track
- Race against 3 AI opponents to complete 3 laps first
- Auto-accelerates — player only steers left or right
- Going off the dirt track slows the car down

## Controls
| Input | Action |
|-------|--------|
| Tap left half of screen | Turn left |
| Tap right half of screen | Turn right |
| Arrow keys ← → | Turn (desktop) |
| A / D keys | Turn (desktop) |

## Theme
- Chick-fil-A red (#E4002B) player car
- Infield reads: **"🐄 EAT MOR CHIKIN 🐄"** and **"HENRY'S SPEEDWAY"**
- Cow emoji (🐄) on the player car
- AI opponents named and themed after CFA menu items

## Cars
| Car | Color | Emoji | Name |
|-----|-------|-------|------|
| Player | CFA Red `#E4002B` | 🐄 | Henry |
| AI 1 | Black `#111111` | 🍗 | Nugget |
| AI 2 | Orange `#d47f00` | 🥤 | Lemonade |
| AI 3 | Dark Green `#1e5218` | 🧇 | Waffle Fry |

## Track
- Top-down view dirt oval
- Dark dirt background with texture
- Green infield with grass stripe detail
- Dashed white edge lines, yellow center dashes
- Checkered start/finish line at top of oval
- 2x2 car grid at race start

## Race Structure
- 3-lap race
- Countdown: 3 → 2 → 1 → GO! 🏁
- HUD shows current lap (x/3) and position (1st–4th)
- Win screen: trophy + celebration message
- Lose screen: encouragement + race again prompt

## Tech Stack
- Vanilla HTML / JavaScript / Canvas 2D
- No dependencies, no build step
- Single file: `index.html`
- Mobile-first, responsive to any screen size

## Car Physics
- Auto-acceleration up to top speed
- Friction-based deceleration (coast-down feel)
- Turn rate scales with speed (tighter at low speed)
- Off-track penalty: speed reduced to 88% per frame
- AI follows oval waypoints (80-point path), steers toward nearest target

## Lap Detection
- Oval divided into normalized progress (0.0–1.0, clockwise from top)
- Lap counted when progress wraps from >0.87 back to <0.13
- Position rank = laps completed + fractional progress

## Deployment
- GitHub: [github.com/jirabc/henry-cfa-race](https://github.com/jirabc/henry-cfa-race)
- Vercel: auto-deploys from `main` branch on push
- Entry point: `index.html` (required for Vercel static hosting)

## File Structure
```
henry-cfa-race/
├── index.html       # Main game file (Vercel entry point)
├── henry-race.html  # Original named copy
└── concept.md       # This file
```
