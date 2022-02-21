# Sky-GVINS
Sky-GVINS: a Sky-segmentation Aided GNSS-Visual-Inertial System for Robust Navigation in Urban Canyons [paper link(To be released)](TBD)


Authors: Jie Yin, Tao Li, Wenxian Yu and Danping Zou

## Abstract:
Multi-sensor fusion is a new developing trend in the field of SLAM (Simultaneous Localization and Mapping) for higher accuracy and better robustness in highly diverse environments. Among them, SLAM systems integrating GNSS (Global Navigation Satellite Systems) are drawing increasing attention for a global and continuous localization solution. Nonetheless, in dense urban environments, these GNSS-based SLAM systems will suffer from the NLOS (Non-Line-Of-Sight) measurements, which might lead to a sharp deterioration in location results. 

In this paper, we segment the sky-pointing image to improve GNSS measurement reliability for more accurate position estimation. Based on a recent work called GVINS which integrates GNSS, images and inertial information, we present Sky-GVINS: a sky-segmentation aided GNSS-Visual-Inertial system. Firstly, we adopt the global threshold method to segment the acquired fish-eye sky-pointing image to sky regions and non-sky regions. And then we back-projection satellites to the image using the geometric relationship between satellites and the camera. After that, we filter satellites in non-sky regions to eliminate NLOS signals for a more accurate position calculation. A sky segmentation test is conducted for different segmentation algorithms, in which the Otsu algorithm reports the highest classification rate and calculation efficiency. To test the effectiveness of Sky-GVINS, we construct a ground robot and carry out extensive real-world experiments on campus. Experimental results demonstrate that our methods effectively improve the location accuracy both in open-sky and dense urban environments compared to the baseline method. We make a detailed analysis of the experiment and point out the direction that can be further optimized for future research. For the benefit of the research community, the source code and datasets in this work will be made public. 




## Contributions

**Sky-GVINS** is a a Sky-segmentation Aided GNSS-Visual-Inertial System for Robust Navigation in Urban Canyons. The system framework is adapted from [GVINS](https://github.com/HKUST-Aerial-Robotics/GVINS). Our system contains the following features:

- We introduce a lightweight method that uses the global threshold algorithm on the sky-pointing images to separate LOS and NLOS signals. Our approach is efficient and effective, which can be easily extended to other GNSS-based systems.
- We propose a robust SLAM system that can obtain accurate global state estimation robustly both in dense urban environments and open-sky regions, which outperforms other existing systems in real-world experiments. 
- We present a large-scale sky segmentation dataset with manually marked labels and a multi-sensor SLAM dataset with accurate ground truth trajectories. We will make them public, facilitating tests of sky segmentation algorithms and GNSS/SLAM systems in urban canyons.

**Video:**

[![Sky-GVINS Video](fig/cover.png)](https://www.youtube.com/watch?v=XGGV9fB7raA)

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
Download our [Sky-GVINS-Dataset(To be released)](TBD) and launch Sky-GVINS via:
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

## 4. Sky Segentation Dataset
Our sky segmentation datasets with mannually labeled GT are released in the following link [Sky-Seg(TBD)](TBD)
## 5. Acknowledgements
TBD

## 5. Licence
The source code is released under [GPLv3](https://www.gnu.org/licenses/gpl-3.0.html) license.
