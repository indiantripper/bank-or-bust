# Bank or bust

A one-thumb ocean game. Eat, grow, lock it in, and become the thing that hunted you.

**Play it:** https://indiantripper.github.io/bank-or-bust/

You start as a 3 cm minnow. Six evolutions later you are a 284 m leviathan.

## How to play

1. Eat green fish to grow. Orange fish eat you. Grey fish are too close to your size to matter.
2. Touch home (the green circle at the bottom of the sea) to lock in your growth and points. If you get eaten, you drop back to your last lock. Nothing can eat you while you are home, and the hunter backs off.
3. A hunter shows up once you are mid-sized. Outgrow it (a green ring appears around it when you can), eat it, and you become it.

Each time you evolve, the camera zooms out. The fish that used to chase you are now small enough to eat.

**Controls:** drag anywhere on mobile (it works as a joystick), or move the mouse on desktop.

## The core tension

- Bigger means slower, and the hunter is faster than you once you are large.
- Every third fish eaten without banking raises your multiplier, up to x8.
- Banking is safe but resets the multiplier. Staying out scores more and risks it all.

## Stages

| Stage | You are | Hunter | Starting length |
| --- | --- | --- | --- |
| 1 | Minnow | Perch | 3 cm |
| 2 | Perch | Barracuda | 14 cm |
| 3 | Barracuda | Shark | 63 cm |
| 4 | Shark | Orca | 2.9 m |
| 5 | Orca | Whale | 13 m |
| 6 | Whale | Leviathan | 62 m |
| End | Leviathan | none | 284 m |

## Run it

No build step and no dependencies. Open `index.html` in a browser.

The live version is served by GitHub Pages from `main`, root folder (Settings, then Pages, then "Deploy from a branch").

## Tuning

Every number that affects feel is in the `CFG` object at the top of the script in `index.html`.

| Setting | What it does |
| --- | --- |
| `speed`, `slowPerSize` | Your swim speed, and how much each unit of size slows you |
| `startSize`, `maxSize` | Your size at the start of each stage, and the size cap |
| `hunterAppearsAt`, `eatHunterAt` | Size at which the hunter arrives, and size at which you can eat it |
| `hunterSpeed`, `hunterSpeedPerStage`, `hunterTurn`, `hunterRadius` | How fast and how big the hunter is, and how quickly it turns |
| `growth`, `growthSlowPerStage` | How fast you grow, and how much longer each later stage takes |
| `comboStep`, `comboMax` | Fish per multiplier step, and the multiplier cap |
| `hunterPoints` | Base points for eating the hunter |
| `eatRatio`, `dangerRatio` | How much smaller a fish must be to eat it, and how much bigger to eat you |
| `startLengthCm`, `lengthPerStage` | The length readout and how much it scales per stage |
| `baseFish` | How many fish are in the sea |

To add a stage, add a name to the `NAMES` array. The last name is always the final form.

## Design notes

- **The score points at the fun.** Points reward the risky behaviour (long streaks away from home), not time spent.
- **The goal is always one line.** The text above the sea tells you the single next thing to do.
- **No daily streaks, timers, or nags.** The aim is "one more go", not obligation.
- **Reversal is the reward.** The best moment in each stage is eating what was hunting you.

## Status and roadmap

This is a prototype: flat shapes, no sound, single player, no backend. The best score is saved on the device only.

**Known issue:** phones in landscape leave the sea very short. Portrait is the intended layout.

Ideas for next steps:

- Sound and haptics on eat, bank, bust, and evolve
- Distinct art for each stage and hunter
- Stage-specific hazards (jellyfish, nets, currents)
- A share card at the end with time, score, and final length
- Installable app (PWA) with offline play
- Keyboard controls
- A layout that works in landscape

## Credits

Inspired by eat-and-grow ocean games and by ideas about scoring and play in C. Thi Nguyen's book *The Score*.

## License

MIT. See `LICENSE`.
