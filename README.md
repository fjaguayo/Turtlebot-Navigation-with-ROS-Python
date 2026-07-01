# Python Basics for Robotics — Course Project

## Overview

This repository contains my final project for **The Construct's "Python for Robotics"** course. The goal of the project is to apply Python programming fundamentals to control a real ROS2-based mobile robot, moving from simulation to a live robot.

The exercise is built around a **rosject** (a self-contained ROS development environment provided by The Construct) that includes:

- A **simulation** of the **TurtleBot3** robot in Gazebo, used to develop and test the code safely.
- A **remote connection to a real robot**, the **FastBot**, physically located in Barcelona, Spain, which can be controlled live from the same environment once the simulated code works correctly.

## Project Objective

The main objective is to build a set of Python control programs for a differential-drive mobile robot using **ROS2**, and to use them to implement simple autonomous behaviors. The project is structured in three parts:

### Part 1 — Get Familiar with the Rosject Environment
Learn how to work in a professional ROS development setup: launching terminals, the IDE, the simulation, and (later) the connection to the real robot lab.

### Part 2 — Create Programs to Control the Robot
Write **two versions** of a robot control program that provide the same functionality but with different code structures:
- `robot_control_noclass.py` — a **non-object-oriented** implementation.
- `robot_control_classed.py` — an **object-oriented** implementation.

Both files implement a common set of functions covering:
- **Robot movement**: reading current velocities, stopping, moving forward/backward, turning left/right, timed movements, and distance/angle-based movements.
- **Laser scan (LIDAR) data**: reading scan ranges, angles, and specific directional ranges (front, back, left, right).
- **Odometry / distance calculation**: computing distance between points using the Euclidean formula.

Comparing both versions highlights the practical advantages of object-oriented programming for robotics applications.

### Part 3 — Implement Basic Robot Algorithms
Using the object-oriented control program, implement simple autonomous behaviors:
- **Obstacle Prediction**: analyze the frontal 90° of laser scan data to estimate whether the robot is facing open space, a wall, or an obstacle.
- **Direction Tracking**: use the robot's yaw (orientation) to determine which of 16 compass-like directions it is currently facing.
- **Naive Obstacle Avoider**: a simple reactive navigation algorithm that segments the laser scan into zones (left, front-left, front, front-right, right) and steers the robot to avoid collisions while tracking distance traveled and reporting IMU data.

Each of these algorithms was first validated in the **Gazebo simulation** with the TurtleBot3, and then run on the **real FastBot robot** through the remote real-robot lab connection.

## Technologies Used

- **Python 3**
- **ROS2**
- **Gazebo** (simulation)
- Real robot hardware (**FastBot**) accessed remotely via The Construct's Real Robot Lab

## Repository Contents

This HTML file is the exported version of the Jupyter notebook that contains the full project instructions, along with the images and animations illustrating each step (environment setup, simulation, real robot booking/connection process, and expected results).

## Acknowledgements

Special thanks to **[The Construct](https://www.theconstruct.ai/)** for providing the course materials, the simulation and real-robot infrastructure, and the rosject environment that made this hands-on learning experience possible.
