# Particle Filter Simulation of Ball Trajectories

## Overview

This repository contains a Python simulation of two balls' trajectories under the influence of gravity, using a particle filter to estimate their positions based on noisy observations. The simulation models two balls launched from different initial positions and speeds, and tracks their movement in 2D space. The particle filter is used to estimate the true positions of the balls at each time step based on noisy observations.

## Features

- **Ball Simulation**: Simulates the motion of two balls with the given launch parameters (position, speed, angle) under gravity.
- **Particle Filter**: Implements a particle filter to estimate the position of the balls from noisy observations.
- **Error Calculation**: Computes Mean Squared Error (MSE) and Root Mean Squared Error (RMSE) to evaluate the performance of the particle filter.
- **Visualization**: Plots the true trajectories, noisy observations, and estimated trajectories using `matplotlib`.

## Requirements

The code requires the following Python libraries:
- `numpy` for numerical operations
- `matplotlib` for plotting the results
- `time` for runtime tracking

Install the required dependencies by running:
```bash
pip install numpy matplotlib
```

## How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/particle-filter-ball-simulation.git
   ```

2. Navigate to the project directory:
   ```bash
   cd particle-filter-ball-simulation
   ```

3. Run the simulation:
   ```bash
   python simulation.py
   ```

4. The script will simulate the ball trajectories, estimate their positions using a particle filter, and display the results.

## Description of Functions

### 1. `initialize_ball()`
Initializes the state of a ball, including its position, velocity, gravity, and time.

### 2. `step_ball()`
Updates the ball's position and velocity based on the current velocity and gravitational acceleration.

### 3. `generate_noisy_observation()`
Generates noisy observations based on the true position of the ball and a specified noise covariance.

### 4. `initialize_particle_filter()`
Initializes the particles, weights, and covariance matrices for the particle filter.

### 5. `predict_particles()`
Predicts the positions and velocities of the particles at the next time step using a transition model.

### 6. `update_weights()`
Updates the particle weights based on the difference between the true position and the noisy observation.

### 7. `resample_particles()`
Resamples the particles when the effective number of particles falls below a threshold.

### 8. `estimate_state()`
Estimates the state (position and velocity) using the weighted average of the particles.

### 9. `simulate_and_filter()`
Simulates the trajectory of the two balls and uses the particle filter to estimate their positions. It also collects data for analysis and visualization.

### 10. `calculate_errors()`
Calculates the Mean Squared Error (MSE) and Root Mean Squared Error (RMSE) between the true positions and estimated positions of the balls.

### 11. `plot_results()`
Plots the true trajectories, noisy observations, and estimated positions of the balls using `matplotlib`.

## Input Parameters

- **Time Step (`dt`)**: The time step for the simulation (default: `0.1` seconds).
- **Total Simulation Time**: The total duration of the simulation (default: `10` seconds).
- **Observation Noise Covariance**: Covariance matrix for observation noise (default: `[[0.5, 0.5], [0.5, 0.5]]`).
- **Launch Parameters**: 
  - `launch_position`: Initial position of the ball `[x, y]`.
  - `launch_speed`: Launch speed in meters per second.
  - `launch_angle`: Launch angle in degrees.

- **Particle Filter Parameters**:
  - `num_particles`: Number of particles for the filter (default: `1000`).
  - `init_state_mean`: Initial state mean `[x, y, vx, vy]`.
  - `init_state_cov`: Initial state covariance matrix.
  - `transition_cov`: Transition covariance matrix.

## Example Output

1. **Error Metrics**: The simulation will print the Mean Squared Error (MSE) and Root Mean Squared Error (RMSE) for both balls.
   
   Example:
   ```
   Ball 1 - MSE: 0.0234, RMSE: 0.1531
   Ball 2 - MSE: 0.0178, RMSE: 0.1333
   ```

2. **Plots**: The simulation will display a plot of the true trajectories, noisy observations, and estimated trajectories of both balls.

## Runtime

The total runtime of the simulation will be printed at the end of the script.

Example:
```
Total time taken: 5.24 seconds
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
