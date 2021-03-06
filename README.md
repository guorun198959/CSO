# calibration_stereo_odom (CSO)
Calibrate the rigid transformation between the stereo and odometry

 ![image](https://github.com/doomzzju/CSO/blob/master/img.png)

**Authors:** Doom

Calibration_stereo_odom (CSO) is a tool to calibrate the rigid body transformation between a stereo camera and robot odometry.

#1. Before installation
This tool is compiled under Ubuntu(14.04) and g2o, libviso2, Suitesparse, libpng++, yaml-cpp are required.

## C++11 or C++0x Compiler
Use the new thread and chrono functionalities of C++11.

## G2O
The G2O(General Graph Optimization) is used to perform non-linear optimizations. 
[g2o](https://github.com/RainerKuemmerle/g2o). Make sure you have installed g2o into your PC.

## libviso2
The visual odometry library, used to calculate the stereo-vo to estimate the stereo's movement. The code has already involved in the ThirdParty folder of CSO.
**Website:** www.cvlibs.net

## yaml-cpp
There are some parameters used in this project, we use yaml tool to read them in. This lib have already involved in the ThirdParty folder.
[yaml-cpp](https://github.com/jbeder/yaml-cpp).

## Suitesparse, libpng++
use the command line below to install this lib.
```
$ sudo apt-get install libsuitesparse-dev libpng++-dev
```
#2. Building CSO
Clone the repository into your workspace, e.g CSO:
```
git clone https://github.com/doomzju/calibration_stereo_odom.git CSO
```
I provide a script `build.sh` to build the *ThirdParty* libraries and *calibration_stereo_odom*. Please make sure you have installed all required dependencies (see section 1). Execute:
```
cd CSO
chmod +x build.sh
./build.sh
```
after that you can find the execute file in the build folder.

#3. Usage and Examples.
In this tool, if you want use viso2 to estimate the stereo camera's motion, please set the `use_viso` parameter to true; if you want not only use graph optimization but also use closed form solution, please set the `use_closed_form` to true. e.g.:
```
./CSO [params_folder_name]
```

#4. Data format:
There are some test data in the /data folder of this project.
