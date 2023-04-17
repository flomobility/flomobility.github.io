---
layout: default
title: Device IMU
parent: Getting sensor data
nav_order: 2
---

# Device IMU

```python
import numpy as np
from anx_interface import Anx

def imu_cb(data):
    print(data)
    
anx = Anx()
anx.start_device_imu(fps=100, cb=imu_cb)
anx.wait()
```
