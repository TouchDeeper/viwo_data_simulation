**Read this in other languages: [English](README.md), [中文](README_zh.md).**
# wheel-imu-cam simulation
Wheel speed, IMU, and camera data simulation for testing VIWO algorithms.

## Features
- Simulate motion and observation data for wheel speed, IMU, and camera
- Simulate extrinsic parameters for wheel speed, IMU, and camera
- Simulate time delays between wheel speed, IMU, and camera

## 坐标系
- **O**dom frame: Wheel speed coordinate system

- **B**ody frame: IMU coordinate system

- **C**am frame: Camera coordinate system

- **W**orld frame: The position of the first frame of the IMU coordinate system

- **N**avigation frame: NED (North-East-Down) or ENU (East-North-Up), this code uses ENU, with the gravity vector in this coordinate system as \( (0,0,-9.81) \)

Currently, the IMU's z-axis is upwards, with elliptical motion within the xy-plane, no motion along the z-axis, and the x-axis moves outward along a circumference. The extrinsic parameter Tbc rotates the camera coordinate system to face the feature points. Additionally, there are extrinsic parameters Tbo representing the extrinsic parameters between IMU and wheel speed, as well as parameters td_wheel and td representing the wheel speed-IMU delay and camera-IMU delay, respectively.
## Usage
main/gener_alldata_VIW.cpp: Used to generate wheel speed data, IMU data, camera trajectory, feature point pixel coordinates, and 3D coordinates of feature points.

## 感谢
This tool is developed based on [vio_data_simulation](https://github.com/HeYijia/vio_data_simulation), thank you for their outstanding work.