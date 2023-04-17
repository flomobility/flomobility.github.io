---
layout: default
title: Device GNSS
parent: Getting sensor data
nav_order: 1
---

# Device GNSS

```python
from anx_interface import Anx

def gnss_cb(data):
    print(data)
    
anx = Anx()
anx.start_device_gnss(cb=gnss_cb)
anx.wait()
```
