# SLAM-Basic
This is a basic introduction to <b>Simultaneous Localzation and Mapping</b> (SLAM). The motivation of the writing is to help reader understand SLAM better. Specifically, a completely SLAM solution with <b>Extended Kalman Filter</b> (EKF) will be introduced here. Notice that a complete solution doesn't mean that SLAM problem is solved. There are still many researches going on in the field.

## Introduction
SLAM was originally developed by Hugh Durrant-Whyte and John J. Leonard [1](https://ieeexplore.ieee.org/document/88147). The SLAM is the technique that solves the problem of building a map of an unknown environment by the robot while localizing itself within the map.
\\
SLAM are decomposed into multiple parts, including
* landmark extraction
* data association
* state estimation
* state and landmark update
