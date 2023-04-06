---
layout: default
title: Home
nav_order: 1
description: "Flo Edge home page"
permalink: /
---

TODO: Add Flo Edge banner

## What is Flo Edge
Flo Edge is a compute, sensor & comms platform for ai and robotics application.

It comes pre installed with ubuntu 22.04 with most of the commonly used tools and packages for robotics and ai application (i.e. ROS2, OpenCv, zmq, ceres, sophus, g2o etc) and anx_inteface which provides access to devices resources (like device camera, device imu, device gnss ets). Any other packages requred can either be installed via apt or build from source.

## Specifications:
### Compute and memory

|--------------|-----------------------------------------------------------------|
| Chipset      | Qualcomm Snapdragon 845 (10 nm)                                 |
| Architecture | aarch64                                                         |
| CPU          | Octa-core (4x2.8 GHz Kryo 385 Gold & 4x1.8 GHz Kryo 385 Silver) |
| GPU          | Qualcomm Adreno 630                                             |
| DSP          | Qualcomm Hexagon 685                                            |
| RAM          | 6GB                                                             |
| Storage      | 80GB (UFS 2.1)                                                  |

### Sensors and others

|---------|----------------------------------------------------------------------------|
| Cameras | 12 MP f/1.9 1/2.55 1.4µm dual pixel PDAF                                   |
| IMU     | 9 axis (accelerometer(BMI160) + gyroscopei(BMI160) + magnetometer(ak0991)) |
| GNSS    | GLONASS, Beidou, GPS, QZSS, Galileo                                        |

### Comms

|:--------|:-------------------------------------------------------|
| Network | GSM/HSPA/LTE                                           |
| WLAN    | Wi-Fi 802.11 a/b/g/n/ac, dual-band, Wi-Fi Direct, DLNA |
| USB     | USB Type-C 2.0, OTG                                    |
