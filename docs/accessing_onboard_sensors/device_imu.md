---
layout: default
title: IMU
parent: Accessing onboard sensors
nav_order: 2
---

# Device IMU

With Flo Edge, you get access to a pre calibrated 9 axis IMU.

## Create a stream
You can stream both filtered and raw data upto 200 Hz. Here's an simple example to illustrate that.
```python
from anx_interface import Anx

def imu_cb(data):
    print(data)
    
anx = Anx()
anx.start_device_imu(fps=100, cb=imu_cb)
anx.wait()
```
