# mpc_noetic

# How to install Ipopt on x86 environment  

## Install CPPAD & Fortran  
```
sudo apt-get install cppad gfortran  
```
  
## Build and install the libraries
 
```
cd {$CUSTOM_PATH}/Ipopt-3.12.8  
mkdir build  && cd build  
../configure  
make -j4  
make install  
```

## Copy install files into specific directory 
```
cd CUSTOM_PATH/Ipopt-3.12.8/build  
sudo cp -a include/* /usr/include/.  
sudo cp -a lib/* /usr/lib/.  
```

## Build ros packages and run 
```
cd ..
catkin_ cmake
cd devel
source ./setup.bash
```

## Launch

### Run Navigation algorithm with MPC in simulation: 

- It can be selected with DWA, MPC, Pure persuit according to 'controller' argument.
```
roslaunch mpc_ros nav_gazebo.launch
```


### Run tracking the reference line with MPC

- Tracking the trajectory such as infinity-shaped, epitrochoid, square using non-linear model predictive control.
```
roslaunch mpc_ros ref_trajectory_tracking_gazebo.launch
```


## How to use as local planner

- After building successfully, you should just change the base_local_planner param with `mpc_ros/MPCPlannerROS`.
```
<param name="base_local_planner" value="mpc_ros/MPCPlannerROS"/>
```