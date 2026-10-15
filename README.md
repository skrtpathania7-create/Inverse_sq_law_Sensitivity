# Sensitivity of the Inverse-Square Law
A Python simulation that shows how orbits change when the gravitational force law is slightly altered. It compares the real inverse-square law (n = 2) with a nearly identical one (n = 2.1).

## The idea
Gravity pulls with a force proportional to 1/r^n. In our universe n = 2, and orbits close into stable ellipses. This project asks: what happens if n is only slightly different?

## What it does
- Simulates an orbiting body around a central mass using numerical integration (semi-implicit Euler)
- Runs two cases: n = 2.0 and n = 2.1
- Plots both trajectories on the same graph with Matplotlib

## Results
- **n = 2.0:** The orbit closes into a stable ellipse.
- **n = 2.1:** The orbit no longer closes. It keeps a similar size but precesses, with its closest-approach point shifting by roughly 17 degrees each orbit.

Even a 5% change in the exponent breaks the closed orbit, which shows how special the inverse-square law is.

## Setup
pip install numpy matplotlib

## Usage
Run the script. You can change the exponent in the calls near the bottom:

stable = get_path(2.0)
unstable = get_path(2.1)

## Simulation parameters
- Initial position: (1, 0), initial velocity: (0, 0.8)
- Time step: 0.02, steps: 2000
- Units where GM = 1
- The simulation stops early if the body escapes (r > 5) or crashes (r < 0.05)

## Limitations
- Euler-type integration accumulates numerical error over long runs.
- The simulation is 2D with a fixed central mass.

## Future improvements
- Use a higher-order integrator (Runge-Kutta or leapfrog)
- Measure and plot the precession angle for a range of n values
- Check energy and angular momentum conservation
