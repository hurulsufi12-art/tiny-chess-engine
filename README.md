# Tiny Chess Engine

A strong chess engine in one Python file for make.fun
[tiny-chess-01](https://make.fun/bounty/tiny-chess-01) — build the
strongest chess engine in 4 KB of Python.

[![tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/hurulsufi12-art/tiny-chess-engine/rank.svg)](https://make.fun/bounty/tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/hurulsufi12-art/tiny-chess-engine/reward.svg)](https://make.fun/bounty/tiny-chess-01)

## How it works

- 0x88 board, negamax alpha-beta with iterative deepening to a **fixed
  node budget** (never a clock), transposition table, quiescence search
  over captures/promotions (all evasions when in check), MVV-LVA +
  killer + history move ordering, null-move pruning.
- Evaluation: material + piece-square tables with bishop pair and a
  tapered king middlegame/endgame blend.
- Deterministic: the same position always gets the same move — no wall
  clock, no unseeded randomness, no model calls, Python 3.13 standard
  library only.
- Talks to the game environment at `MAKEFUN_ENV_URL` only
  (`POST /game`, `POST /move`).

## Files

- `main.py` — the entrypoint, packed with `makefun compress` from
  the readable source (kept locally, not committed).
- `LICENSE` — MIT.

## Build

```
makefun compress src.py --out main.py
```
