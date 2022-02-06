# Sky-GVINS
Sky-GVINS: a Sky-segmentation Aided GNSS-Visual-Inertial System for Navigation in Urban Canyons [paper link](TBD)



Authors: Jie Yin, Danping Zou

![](./figures/system_snapshot.png)

**Sky-GVINS** is a TBD. The system framework  are adapted from [GVINS](https://github.com/HKUST-Aerial-Robotics/GVINS). Our system contains the following features:

- TBD
- TBD

**Video:**

[![Sky-GVINS Video](TBD "Sky-GVINS Video")

## 1. Prerequisites
### 1.1 C++11 Compiler
This package requires some features of C++11.

### 1.2 ROS
This package is developed under [ROS Melodic](http://wiki.ros.org/melodic) environment.

### 1.3 Eigen
Our code uses [Eigen 3.3.3](https://gitlab.com/libeigen/eigen/-/archive/3.3.3/eigen-3.3.3.zip) for matrix manipulation.

### 1.4 Ceres
We use [ceres](https://ceres-solver.googlesource.com/ceres-solver) 1.12.0 to solve the non-linear optimization problem.

### 1.5 gnss_comm
This package also requires [gnss_comm](https://github.com/HKUST-Aerial-Robotics/gnss_comm) for ROS message definitions and some utility functions. Follow [those instructions](https://github.com/HKUST-Aerial-Robotics/gnss_comm#2-build-gnss_comm-library) to build the *gnss_comm* package.

## 2. Build Sky-GVINS
Create your catkin workspace :
```
mkdir -p Sky-GVINS_ws/src
cd Sky-GVINS_ws/src
git clone https://github.com/SJTU-ViSYS/Sky-GVINS
```
Then build the package with:
```
cd Sky-GVINS_ws/
catkin_make
source /devel/setup.bash
```
