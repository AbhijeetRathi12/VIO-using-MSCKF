# Visual-Inertial Odometry using Multi-state Constraint Kalman Filter (MSCKF)

## Table of Contents

- [Overview](#overview)
- [Requirements](#requirements)
- [Usage](#usage)
- [Results](#results)

## Overview

This project implements a Visual-Inertial Odometry (VIO) system using a Multi-state Constraint Kalman Filter (MSCKF). It integrates data from an IMU and a stereo camera to accurately determine the robot's location and state. The project includes initialization of gravity and bias, batch IMU processing, state propagation using a fourth-order Runge-Kutta integration technique, state augmentation, and feature observation addition. Evaluations are conducted using the EuRoC dataset.

| **Trajectory Overview** |  |
|----------|----------|
| ![Alt1](Images/Trajectory_side_view.png) | ![Alt2](Images/Trajectory_top_view.png) |
| Side View  | Top View  |


## Requirements

To run this script, you need Python 3 and the following Python packages:
- `Numpy`
- `Opencv-python`
- `Scipy`
- `pangolin`(https://github.com/uoip/pangolin) (optional, for trajectory/poses visualization)


You can install these packages using pip:

```bash
pip install numpy opencv-python scipy
```

## Usage

* Clone the repository:

```bash
git clone https://github.com/AbhijeetRathi12/VIO-using-MSCKF.git
cd VIO-using-MSCKF-main
```

* Ensure you have the EuRoC MAV dataset. You can download it from [here](http://projects.asl.ethz.ch/datasets/doku.php?id=kmavvisualinertialdatasets).

* Run the `vio.py` script with the path to your dataset:
```bash
python Code/vio.py --path path/to/your/EuRoC_MAV_dataset/MH_01_easy --view
```

or (no visualization)

```bash
python Code/vio.py --path path/to/your/EuRoC_MAV_dataset/MH_01_easy
```

* Use `pangolin` for trajectory/poses visualization.

## Results

Evaluations are performed using the EuRoC dataset. The absolute median trajectory error (ATE) and root mean square translation error (RMSE) are used to measure the performance. The absolute median trajectory error (ATE) is 0.07072745620375322 m and root mean square translation error (RMSE) is 0.08225543715390592 m.

## Author
Abhijeet Sanjay Rathi

## Acknowledgments
Special thanks to the Computer Vision course instructors and teaching assistants for their guidance and support.
