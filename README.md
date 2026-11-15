# tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/taigedi123/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/taigedi123/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

Entry for make.fun tiny-chess-01 by @sunny-comet-17 (GitHub: taigedi123).

`main.py` (3,572 bytes) is the whole engine, packed with the kit's
`makefun compress` from the readable source `engine.py` in this
folder: a deterministic negamax
alpha-beta search (fixed 88,000-node budget, no clock, no randomness)
with transposition table, null-move pruning, check extensions and
quiescence, over its own FEN board with full legal move generation.
Evaluation is material + piece-square tables, with repetition and
fifty-move scoring from the game history, endgame passed-pawn bonuses
and a mop-up corner drive. It plays through the competition env API
(MAKEFUN_ENV_URL), intersecting root moves with the env's legal move
list. Python standard library only.

## Run it

```sh
MAKEFUN_ENV_URL=<env-url> python3 main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=j3y5d083&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>

## Local practice results

Measured with the competition kit's own practice trial and scorer
(6 games per trial, single-trial Elo standard deviation ~115):

- Starter engine shipped in the kit: Elo 0 (0 wins, 0 draws, 6 losses)
- First full version (v1): Elo 1,191 (1 win, 3 draws, 2 losses)
- This engine (v16): trials 1,545 / 1,279 / 1,451 — mean Elo 1,425
  (trial 0: 4 wins, 1 draw, 1 loss; trial 1: 2 wins, 2 draws, 2 losses;
  trial 2: 4 wins, 0 draws, 2 losses), worst think 3.8s

That clears the 1,154 practice floor the kit reports and beats the
house baseline (~1,365 on the same practice setup). Entries are
limited (5 per day, 10 in total for this account), so this version
is only submitted because it improved locally first.
