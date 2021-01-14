# SLAM-Basic
This is a basic introduction to <b>Simultaneous Localzation and Mapping</b> (SLAM). The motivation of the writing is to help reader understand SLAM better. Specifically, a completely SLAM solution with <b>Extended Kalman Filter</b> (EKF) will be introduced here. Notice that a complete solution doesn't mean that SLAM problem is solved. There are still many researches going on in the field.

## Introduction
SLAM was originally developed by Hugh Durrant-Whyte and John J. Leonard [[1](https://ieeexplore.ieee.org/document/88147)]. The SLAM is the technique that solves the problem of building a map of an unknown environment by the robot while localizing itself within the map.

## SLAM Components
SLAM can be decomposed into multiple modules, including
* landmark extraction
* data association
* state estimation
* state and landmark update
### Landmark
Landmarks are features which can be re-observed and distinguished from the environment. Through frequently observing the landmarks, robot can identify where it is. One key property of the landmarks is uniqueness which means that robot can easily identify landmarks even after some time-steps. Besides that, there should be plenty of landmarks in the map for localization. Thirdly, landmarks should be stationary.
### Landmark Extraction
#### Spike Algorithm
The spike landmark extraction algorithm uses extrema to find landmarks. They are identified by finding values in the range of a Lidar where two values differ by a threshold. Another way to find spikes are having three values next to each other, A, B, and C. Substracting B from A and B from C and adding the two numbers will yield a value. One drawback of the algorithm is the failure in smooth environments.
#### RANSAC Algorithm
Random Sampling Consensus (RANSAC) is another landmark extraction algorithm. The algorithm extract lines from the Lidar readings, and the lines are treated as landmarks. Indoor environments usually contains straight walls which is very suitable for RANSAC.\
The method randomly taking data points and then using a least squares approximation to find the best fit line that runs through the points. When there are certain number of points close to the best fit line, we assume that this line is a landmark. The threshold is called consensus.

## Hardware
### Lidar
Lidar is a type of range measurement sensor. It uses laser beams to measure the distance from the source to obstacles if the beams hit any. Although the sensor has very high precision, i.e., centimeter level accuracy or higher, price is pretty high when compared to other ranging sensors. Also, it could produce bad results when the beam hits certain surfaces including glass.

### Camera
Vision is the alternative option to perform SLAM. Because of the advancement of high-dynamic-range camera, saturation problem of vision can be ignored in most situations. Also, the great improvement in computation power makes machine learning a great tool to estimate distance to obstacles in the image. As a result, vision becomes a cheaper solution for SLAM. Some camera setup includes mono camera and stereo camera.
