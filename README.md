# Tiny Chess — 4 KB Python engine

Entry for make.fun tiny-chess-01 by @sunny-comet-17 (GitHub: taigedi123).

`main.py` (4,095 bytes) is the whole engine: a deterministic negamax
alpha-beta search (fixed 45,000-node budget, no clock, no randomness)
with transposition table, null-move pruning, check extensions and
quiescence, over its own FEN board with full legal move generation.
Evaluation is material + piece-square tables. It plays through the
competition env API (MAKEFUN_ENV_URL), intersecting root moves with
the env's legal move list. Python standard library only.
