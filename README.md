# Sky-GVINS
Sky-GVINS: a Sky-segmentation Aided GNSS-Visual-Inertial System for Robust Navigation in Urban Canyons [paper link](TBD)


Authors: Jie Yin, Danping Zou

## Abstract:
Multi-sensor fusion is a new developing trend in the field of SLAM (Simultaneous Localization and Mapping) for higher accuracy and better robustness in highly diverse environments. Among them, SLAM systems integrating GNSS (Global Navigation Satellite Systems) are drawing increasing attention for a global and continuous localization solution. Nonetheless, in dense urban environments, these GNSS-SLAM systems will suffer from the NLOS measurements, which might lead to a sharp deterioration in location results. 

In this paper, we segment the sky-pointing images to improve GNSS measurement reliability for more accurate position estimation. Based on a recent work called GVINS which integrates GNSS, images and IMU (Inertial Measurement Unit) information, we present Sky-GVINS: a sky-segmentation aided GNSS-Visual-Inertial system. In our work, we firstly back-projection satellites to the fish-eye sky image. And then we conduct sky segmentation tests with different algorithms, in which Otsu algorithm reports a high classification rate and calculation efficiency. Therefore, Otsu algorithm is adopted to segment the acquired image. After that, we filter satellites in non-sky regions in the position calculation part for better localization in urban canyons. We carried out long-term real-world experiments on campus. Results show our methods effectively improve the location accuracy both in open-sky and 
dense urban environments. For the benefit of the research community, the source code and dataset in this work will be made public.




![](./figures/system_snapshot.png)

**Sky-GVINS** is a TBD. The system framework is adapted from [GVINS](https://github.com/HKUST-Aerial-Robotics/GVINS). Our system contains the following features:

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

## 3. Run Sky-GVINS on demo
Download our [Sky-GVINS-Dataset](TBD) and launch Sky-GVINS via:
```
roslaunch sky-gvins sky.launch
```
Open another terminal and launch the rviz by:
```
rviz -d Sky-GVINS_ws/src/GVINS/config/config.rviz
```
Then play the bag:
```
rosbag play bridge1.bag
```

## 4. Acknowledgements
TBD

## 5. Licence
The source code is released under [GPLv3](https://www.gnu.org/licenses/gpl-3.0.html) license.
