# Drone Guidance & Control — PID Simulations

A Python-based simulation project exploring the fundamentals of **Guidance and Control (G&C)** for autonomous systems, developed as part of the *Advanced Drone Technology* project (India Space Lab). All simulations are implemented from scratch in NumPy/Matplotlib and run in Google Colab or any local Python environment.

## Objectives

- Understand the fundamentals of Guidance and Control for autonomous moving systems
- Learn the basics of PID (Proportional–Integral–Derivative) controller tuning
- Observe the effect of environmental disturbances (wind/current) on stability and tracking
- Develop intuition behind feedback-based control systems
- Understand trajectory/path-following concepts used in drones and boats

## Project Structure

```
├── task1_drone_pid.py           # Task 1: Drone altitude PID control
├── task2_boat_guidance.py       # Task 2: Autonomous boat path tracking
├── bonus_figure8_drone.py       # Bonus: Drone figure-eight trajectory tracking
├── results/
│   ├── task1_pid_result.png
│   ├── task2_boat_result.png
│   └── bonus_figure8_result.png
└── Drone_Guidance_Control_Project_Report.docx   # Full written report
```

## Task 1 — PID Controller Design for Drone Altitude Control

A simulated drone attempts to reach and hold a desired altitude of 10 m. A **No-Wind Zone** runs from t = 0–6 s, after which a constant wind disturbance is introduced. The plot compares a poorly-tuned controller (P-only) against a well-tuned PID controller (tuned P → D → I, per standard practice).

![Task 1 Result](results/task1_pid_result.png)

**Key results (well-tuned):** ~13% max overshoot, ~6.5 s settling time, minimal steady-state error despite wind.

```bash
python task1_drone_pid.py
```

## Task 2 — Guidance and Path Tracking Using an Autonomous Boat

An autonomous boat uses a line-of-sight (LOS) guidance law with PD heading control to follow a sinusoidal reference path, evaluated both **with** and **without** a water current disturbance.

![Task 2 Result](results/task2_boat_result.png)

| Condition | Mean Cross-Track Error |
|---|---|
| Without current | 0.083 m |
| With current | 0.618 m |

```bash
python task2_boat_guidance.py
```

## Bonus — Drone Figure-Eight Trajectory Tracking

A PD position controller drives a simulated drone along a parametric figure-eight trajectory, with a small disturbance added to test robustness.

![Bonus Result](results/bonus_figure8_result.png)

```bash
python bonus_figure8_drone.py
```

## Requirements

```bash
pip install numpy matplotlib
```

## Full Report

See [`Drone_Guidance_Control_Project_Report.docx`](Drone_Guidance_Control_Project_Report.docx) for complete theory, methodology, and analysis of all three tasks.

## Author

*Add your name here*
