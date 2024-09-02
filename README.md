# Particle Filter Simulation of Ball Trajectories

This repository contains a Python simulation that tracks and estimates the trajectories of two balls using particle filters. The simulation is designed to demonstrate the use of particle filtering to estimate the states of moving objects in the presence of noise.

## Features

- **Initialization**: The simulation initializes the position, velocity, and other parameters of two balls launched at different angles and speeds.
- **Particle Filter Implementation**: A particle filter algorithm is employed to estimate the position of the balls as they move, with support for:
  - Prediction of particle positions based on their current state.
  - Updating particle weights according to the observation model.
  - Resampling particles to focus on the most probable estimates.
- **Noisy Observations**: The simulation includes the generation of noisy observations to simulate real-world sensor measurements.
- **Error Calculation**: The Mean Squared Error (MSE) and Root Mean Squared Error (RMSE) are calculated to evaluate the accuracy of the estimated positions.
- **Visualization**: The true trajectories, noisy observations, and estimated trajectories are visualized using `matplotlib`.

## Simulation Workflow

1. **Initialization**:
   - The balls are initialized with specified launch positions, speeds, and angles.
   - Particles are initialized with a Gaussian distribution based on the initial state mean and covariance.

2. **Simulation Loop**:
   - At each time step, the balls' positions are updated based on their velocity and gravity.
   - Noisy observations of the ball positions are generated.
   - The particle filter predicts the next state of the particles, updates their weights based on the observations, and resamples them as needed.
   - The estimated position is computed as a weighted average of the particles.

3. **Error Measurement**:
   - The simulation calculates and prints the MSE and RMSE to assess the accuracy of the particle filter's estimates.

4. **Visualization**:
   - The true, observed, and estimated trajectories are plotted for both balls to visually compare their performance.

## Requirements

- Python 3.x
- `numpy`
- `matplotlib`
