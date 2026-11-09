# SHIFT

A fast, minimalist arcade survival game. You are either **white** or **black**. Shapes that match your color are absorbed for points; everything else hurts. Switch at the right moment, build combos, and survive the swarm.

Single HTML file. No build step, no dependencies, works offline.

## Quick start

1. Download `shift_game.html`.
2. Open it in any modern browser (Chrome, Firefox, Safari, Edge).
3. Click **Start Game**.

To host it, upload the file to any static host (itch.io, GitHub Pages, Netlify). On itch.io, zip it as `index.html` and set the project type to "HTML".

## Controls

| Action | Mouse | Keyboard / trackpad | Touch |
|---|---|---|---|
| Move | Move the cursor | Move the cursor | Drag |
| Switch to White | Left-click | Space or Shift (toggle) | SHIFT button (toggle) |
| Switch to Black | Right-click or Ctrl-click | Space or Shift (toggle) | SHIFT button (toggle) |
| Pause | Pause button | Esc or P | Pause button |

The game also pauses automatically when the window loses focus or the tab is hidden.

## How to play

**Colors.** Pass through shapes of your own color to absorb them. Shapes of the opposite color cost a life. Grey shapes always cost a life.

**Energy.** Every color switch costs 20 energy. Energy regenerates over time (28 per second) and absorbing a shape refills a little. With less than 20 energy you can't switch, so you can't just spam the button.

**Combos.** Absorb shapes within 2.5 seconds of each other to chain them. The multiplier climbs to a maximum of x8. Getting hit resets it.

**Camping.** Stay on one color for more than 5 seconds and opposite-colored shapes will home in on you. Shapes also aim at your position, so corners are not safe. The purple bar under the energy bar shows this timer.

**Warnings.** A pulsing ring at the screen edge shows where a shape is about to enter.

**Tiers.** Every 10 coins raises the tier. Higher tiers make shapes faster and bigger (both capped) and speed up the music.

### Enemies

| Type | Behavior |
|---|---|
| Standard | Drifts toward you in a straight line. |
| Dart | Small, very fast, long warning. |
| Orbiter | Weaves side to side while approaching (cyan inner ring). |
| Splitter | Breaks into two smaller shapes after about a second on screen (yellow inner ring, appears after 25 s). |
| Wave | A line of six same-colored shapes entering from one side, every 14 to 22 seconds. |

### Pickups

| Pickup | Icon | Effect |
|---|---|---|
| Coin | $ | +55 points (times combo). Every 10 raises the tier. |
| Heart | ♥ | +1 life (max 5). At full lives, gives +300 points. |
| Shield | S | 5 seconds of damage immunity. |
| Slow-mo | ◔ | 5 seconds at 45% obstacle speed. |
| Bomb | ✸ | Clears every shape on screen for +10 points each. |
| Magnet | M | 7 seconds of pulling pickups toward you. |

### Scoring

- Surviving: a small amount of points per second, rising with difficulty.
- Absorbing a shape: 15 points times your combo multiplier.
- Coins: 55 points times your combo multiplier.
- Bomb: 10 points per shape cleared.

You start with 3 lives. Your high score is saved in the browser's local storage.

## Settings

Open **Settings** from the main menu or pause screen:

- Music volume and effects volume (separate)
- Screen shake on/off
- Reduced motion (disables shake and cuts particle effects). It defaults to on if your operating system requests reduced motion.

The speaker button in the HUD mutes everything.

## Tips

- Switch just before contact, not early. Energy is your real limit.
- Waves are the same color, so line up with the matching side and chain the whole row.
- Use bombs and slow-mo when a tier jump makes the screen crowded.
- Keep moving toward the middle. Hiding on the edge only delays the swarm.

## Technical notes

- Plain HTML, CSS and JavaScript with the Canvas 2D API. No libraries, no external requests.
- Frame-rate independent (delta-time), so it plays the same at 60 Hz and 144 Hz.
- Audio is synthesized live with the Web Audio API: a chord progression whose tempo rises with the tier.
- High-DPI aware canvas.
- Local storage access is wrapped so the game still runs where storage is blocked (the high score just won't persist).

## Known limitations

- No boss encounters yet.
- Audio starts only after the first click or tap, as browsers require.
- Settings and high score are stored per browser and don't sync.

## Credits

Design and code: [YOUR NAME]

## License

[CHOOSE A LICENSE, e.g. MIT]
