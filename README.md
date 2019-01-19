# CarND-Unscented-Kalman-Filter-Project



[//]: # (Image References)

[image1]: ./RMSE_values_images/Dataset-1.png "Dataset-1 result"
[image2]: ./RMSE_values_images/Dataset-2.png "Dataset-2 result"

### Overview

I have implemented Unscented Kalman Filter (UKF) in C++ on LIDAR measurements (x and y positions)and RADAR measurement data(radius, angle, and radial velocity relative to a fixed measurement site) from simulator provided by Udacity. The UKF initialises, predicts and updates the postions and velocities in X & Y of the vehicle.  A 'Constant Turn Rate and Velocity magnitude' (CTRV) process model was used to carry out the Kalman filter's predict steps. The CTRV model tracks a state vector of 5 quantities: x position, y position, velocity magnitude, yaw angle, and yaw rate.

To measure the performance of the filter, the Root Mean Square Error(RMSE) between the filter results and the actual ground truth is calculated.

The RMSE values of px,py,vx,vy need to be less than or equal to 
 [.09, .10, 0.40, 0.30] to meet the project milestone.
 
Note:

For comprehensive instructions on how to install and run project, please, refer to the following repo, which was used as a skeleton for this project: https://github.com/udacity/CarND-Unscented-Kalman-Filter-Project
 
#### Files in the Github src Folder

main.cpp - Communicates with the Term 2 Simulator receiving data measurements, reads in data, calls a function to run the Unscented Kalman filter, calls a function to calculate RMSE

ukf.cpp -initializes the Unscented Kalman filter, calls the predict and update function, defines the predict and update functions

tools.cpp - Function to calculate RMSE.

#### Basic Build instructions
    $ mkdir build && cd build
    $ cmake .. && make
    $ ./UnscentedKF

Or use the `$ bash build_and_run.sh` provided to execute the above commands.

### Final results after Filter:

On the simulator: 
The red circles are LIDAR measurements and blue circles are RADAR measurements data. The green triangles are the estimated markers. The simulator provides the script the measured data (either lidar or radar), and the script feeds back the measured estimation marker, and RMSE values from its Kalman filter.

Dataset-1 results:

![alt text][image1]


Dataset-2 results:

![alt text][image2]


