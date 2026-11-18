# Experiment 7: Webots (reactive swarm and lidar navigation)

**Status: runs not yet done.** Webots R2025a does not run on my laptop (macOS 27.0.1, Apple M1), so the
simulations have to be run on another computer. No result in this folder or in the report has been taken
from the sample runs shipped with webots-robotics-sim.

## How to run
1. On a machine with Webots R2025a: `git clone https://github.com/reshamrajs/webots-robotics-sim` and `cd` into it.
2. Open `worlds/swarm_arena.wbt` in the GUI once and take the screenshot for Figure 7.1.
3. `bash /path/to/aisr-lab-500119330/exp07-webots/run_all.sh`: Part A (swarm default and cruise = 0.9, 3 repeats each),
   Part B (Pioneer default, bubble = 0.15, k_turn = 0.5) and Exercise 1 (cruise 0.2 to 1.0, 3 repeats each).
4. Exercise 4: change `basicTimeStep` in `worlds/swarm_arena.wbt` to 64, then 8, and run the commented commands in `run_all.sh`.
5. Copy `analysis/runs/*.csv` into `exp07-webots/runs/` and run `python analyse_runs.py`.
   It prints Tables 7.1 to 7.3 and writes `figs/fig7_2_swarm.png`, `figs/fig7_3_pioneer.png` and `figs/fig7_4_exercise1_cruise.png`.

## Metrics (same definitions as analysis/metrics.py)
- path length = sum of distances between logged poses; mean speed = path / duration
- stuck % = share of samples in which the robot moved slower than 1 cm/s
- coverage = share of grid cells visited by any robot (10 cm cells in the 1.6 m arena, 50 cm cells in the 8 m room)
