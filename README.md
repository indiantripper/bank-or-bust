# Bank or bust

A one-thumb ocean game. Eat, grow, lock it in, and become the thing that hunted you.

**Play it:** https://indiantripper.github.io/bank-or-bust/

You start as a 3 cm minnow. Six evolutions later you are a 284 m leviathan.

## How to play

1. Eat green fish to grow. Orange fish eat you. Grey fish are too close to your size to matter.
2. Touch home (the green circle at the bottom of the sea) to lock in your growth and points. If you get eaten, you drop back to your last lock. Nothing can eat you while you are home, and the hunter backs off.
3. A hunter shows up once you are mid-sized. Outgrow it (a green ring appears around it when you can), eat it, and you become it.

Each time you evolve, the camera zooms out. The fish that used to chase you are now small enough to eat.

**Controls:** on mobile, drag anywhere: your fish copies your finger's movement, so your thumb never covers it. On desktop, move the mouse.

## The core tension

- Bigger means slower, and the hunter is faster than you once you are large.
- Every third fish eaten without banking raises your multiplier, up to x8.
- Banking is safe but resets the multiplier. Staying out scores more and risks it all.
- Every level is harder: the hunter arrives sooner, swims and turns faster, and comes back quicker after you hide at home. Fish are faster, easy meals are rarer, and you grow more slowly.
- Hard, not impossible: there are always a few fish you can eat, and each time you get eaten the current level eases slightly (up to three times).

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
| `eatHunterAt` | Size at which you can eat the hunter |
| `growth` | How fast you grow from each fish |
| `hunterAppearsAt`, `hunterSpeed`, `hunterTurn`, `hunterReturn` | Difficulty ramp, as [first level, last level]: when the hunter arrives, its speed and turning, and how soon it returns after you hide |
| `growthSlow`, `fishSpeed`, `foodShare`, `minFood` | Difficulty ramp: how much slower you grow, how fast fish swim, the share of fish you can eat, and the guaranteed minimum of edible fish |
| `mercyMax`, `mercyHunter`, `mercyFood` | How much a level eases after each bust, and for how many busts |
| `comboStep`, `comboMax` | Fish per multiplier step, and the multiplier cap |
| `hunterPoints` | Base points for eating the hunter |
| `touchGain`, `maxLead` | How far the fish moves per pixel of finger movement, and how far ahead of the fish the touch target may run |
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
