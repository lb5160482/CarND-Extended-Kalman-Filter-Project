# Sensor Fusion Using Extended Kalman Filter 

[//]: # (Image References)
[image1]: ./img/result.png

This project utilizes a kalman filter to estimate the state of a moving object of interest with noisy lidar and radar measurements.  

This project involves the Simulator which can be downloaded [here](https://github.com/udacity/self-driving-car-sim/releases)

This repository includes two shell scripts that can be used to set up and install [uWebSocketIO](https://github.com/uWebSockets/uWebSockets) for either Linux or Mac systems.

Once the install for uWebSocketIO is complete, the main program can be built and run by doing the following from the project top directory.

1. mkdir build
2. cd build
3. cmake ..
4. make
5. ./ExtendedKF


Here is the main protcol that main.cpp uses for uWebSocketIO in communicating with the simulator.(simulator using data from data folder)

INPUT: values provided by the simulator to the c++ program

["sensor_measurement"] => the measurement that the simulator observed (either lidar or radar)


OUTPUT: values provided by the c++ program to the simulator

["estimate_x"] <= kalman filter estimated position x
["estimate_y"] <= kalman filter estimated position y
["rmse_x"]
["rmse_y"]
["rmse_vx"]
["rmse_vy"]

---

## Other Important Dependencies

* cmake >= 3.5
  * All OSes: [click here for installation instructions](https://cmake.org/install/)
* make >= 4.1 (Linux, Mac), 3.81 (Windows)
  * Linux: make is installed by default on most Linux distros
  * Mac: [install Xcode command line tools to get make](https://developer.apple.com/xcode/features/)
* gcc/g++ >= 5.4
  * Linux: gcc / g++ is installed by default on most Linux distros
  * Mac: same deal as make - [install Xcode command line tools](https://developer.apple.com/xcode/features/)

---

## Procedures

* State Vector: [positionX, positionY, velocityX, velocityZ]
* Kalman Filter for Lidar Measurement: [positionX, positionY]
* Extended Kalman Filter for Radar Measurement: [Rho(distance to origin), Phi(angle counter-clockwise from the x-axis), Rho_velocity]

---

## Result
As shown in the image, lidar measurements are red circles, radar measurements are blue circles with an arrow pointing in the direction of the observed angle, and estimation markers, which is the output from the Kalman Filter, are green triangles.

The accuracy here is caculated using RMSE(Root Mean Square Error).   

![alt text][image1]