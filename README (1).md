# Duel Arena

A two-player fighting game that runs in the browser. One HTML file, no dependencies, no build step.

Two fighters share a keyboard (or a touch screen). Pick a weapon, chain combos, use skills and knock out your opponent. First to win two rounds takes the duel.

## Run it

Open `index.html` in any modern browser. That's it.

To serve it locally instead:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

It also works on GitHub Pages: go to **Settings > Pages**, choose your branch and the root folder, and open the published URL.

## Controls

| Action | Player 1 | Player 2 |
|--------|----------|----------|
| Move   | `A` `D` | `Left` `Right` |
| Jump   | `W` | `Up` |
| Attack | `F` | `K` |
| Skill  | `G` | `L` |
| Weapon | `1` `2` `3` | `7` `8` `9` |

Press `Esc` or the `?` button to open the tutorial. On touch screens, tap the controller button in the arena to show on-screen controls for both players.

## Weapons

| Weapon | Damage | Reach | Skill |
|--------|--------|-------|-------|
| Sword | 8, fast | Short | **Dash Slash**: lunge through your opponent for 12 damage |
| Axe | 15, slow, big knockback | Medium | **Ground Slam**: shockwave for 20 damage to grounded opponents nearby (jump to dodge) |
| Spear | 10 | Longest | **Spear Throw**: 14 damage projectile |

## How it works

- **Combos:** land another hit within 0.9 seconds. Each hit adds 20% damage (up to 2.5x) and more knockback.
- **Energy:** skills cost 40. Energy refills over time, and every hit you land gives 12 back.
- **Rounds:** a round ends when someone's health reaches zero. First to two round wins takes the match.

## Terrains

- **Forest:** normal grip.
- **Ice Cavern:** slippery floor, so you slide and stop slowly.
- **Lava Pit:** the lava in the middle of the arena burns anyone standing on it. Jump across.

## Tech

Plain HTML, CSS and JavaScript. The fighters, stages and effects are drawn on a canvas, and the menus and controls are regular DOM elements.

## Project structure

```
index.html   the whole game
README.md    this file
```
