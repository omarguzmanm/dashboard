# Dashboard

**Name:** Omar Alejandro Guzmán Munguía <br>
**Email:** omar.guzman5063@alumnos.udg.mx

In this activity, we simulate and analyze three key stochastic movement models: **Brownian Motion (BM)**, **Correlated Random Walk (CRW)**, and **Lévy Walk (LW)**. Each model represents a different way objects or organisms move in space, with unique mathematical properties. The goal is to implement these models, generate trajectories, and compare their behaviors using basic and advanced metrics.

**Trajectory Functions**
We define functions to generate 3D trajectories for each model. All functions take the following core arguments:

- `n_steps`: Number of steps (integer).
- `speed`: Step size (float).
- `start_pos`: Starting position as (x, y, z) coordinates.

**Brownian Motion (BM)**
- Function: `brownian_motion(n_steps, speed, start_pos)`
- Description: Random, isotropic movement with fixed step sizes.
- Output: Array of 3D coordinates.

**Correlated Random Walk (CRW)**
- Function: `correlated_random_walk(n_steps, speed, start_pos, cauchy_coeff)`
- Extra Argument: `cauchy_coeff` controls how much the direction persists.
- Description: Movement with correlated turns, making it less random than BM.
- Output: Array of 3D coordinates.

**Lévy Walk (LW)**
- Function: `levy_walk(n_steps, speed, start_pos, cauchy_coeff, alpha)`
- Extra Arguments: `cauchy_coeff` for turns, `alpha` (0–2) for step length distribution.
- Description: Movement with occasional long jumps (controlled by `alpha`) and correlated turns.
- Output: Array of 3D coordinates.

**Metric Functions**
We compute three metrics to analyze the trajectories:

1. **Path Length (PL)**
- Function: `path_length(trajectory)`
- Description: Total distance traveled.
- Output: Single float value.

2. **Mean Squared Displacement (MSD)**
- Function: `mean_squared_displacement(trajectory)`
- Description: Average squared distance from the start over time.
- Output: Array of values (one per step).

3. **Turning Angle Distribution (TAD)**
- Function: `turning_angle_distribution(trajectory)`
- Description: Distribution of angles between consecutive steps.
- Output: Array of angles.

**Dashboard**
The interactive dashboard includes:

- **Trajectory Panel:** A 3D plot showing the current trajectory (BM, CRW, or LW).
- **Metric Panel:** A plot or value showing the selected metric (PL, MSD, or TAD).
- **Trajectory Selector:** Radio buttons to pick BM, CRW, or LW.
- **Metric Selector:** Dropdown to choose PL, MSD, or TAD.
- **Parameter Controls:** Widgets for `n_steps`, `speed`, `start_pos` (all models), plus `cauchy_coeff` (CRW and LW) and `alpha` (LW only). These update dynamically based on the selected model.