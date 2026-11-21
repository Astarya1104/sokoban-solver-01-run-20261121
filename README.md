[![make.fun · sokoban-solver-01-run-20261121](https://make.fun/badge/sokoban-solver-01-run-20261121.svg)](https://make.fun/bounty/sokoban-solver-01-run-20261121?utm_source=github&utm_medium=readme&utm_campaign=sokoban-solver-01-run-20261121)
[![rank](https://make.fun/badge/sokoban-solver-01-run-20261121/Astarya1104/sokoban-solver-01-run-20261121/rank.svg)](https://make.fun/bounty/sokoban-solver-01-run-20261121/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=sokoban-solver-01-run-20261121)
[![reward](https://make.fun/badge/sokoban-solver-01-run-20261121/Astarya1104/sokoban-solver-01-run-20261121/reward.svg)](https://make.fun/bounty/sokoban-solver-01-run-20261121?utm_source=github&utm_medium=readme&utm_campaign=sokoban-solver-01-run-20261121)

# Push-optimal Sokoban solver, room by room

An entry for make.fun's "Build the best Sokoban solver, 21 November 2026" bounty.

`main.ts` (Node 22, no dependencies) solves each 5-instance set in one run: room decomposition — cut the hallway's dead squares, solve each room as an independent sub-problem (a box never leaves its room) — then push-optimal BFS per room (state = box positions + player's reachable region, dead-square + frozen-2×2 pruning, deterministic 250,000-state budget per room, no clock, no randomness), joined by BFS walks between rooms.

Practice set: score 1,000,000, passed 5/5, every instance at P* (13/16/29/47/60 pushes), ~0.9 s wall, byte-identical across runs.
