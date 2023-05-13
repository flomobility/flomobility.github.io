---
layout: default
title: GNSS Module
parent: Accessing onboard sensors
nav_order: 1
---

# Device GNSS

The on board GNSS module has connectivity with the following satellite systems: QZSS, Galileo, Beidou, SBAS, GLONASS, GPS

## Stream data
> Each data frame is an [NMEA 0183](https://en.wikipedia.org/wiki/NMEA_0183) sentence

Here's an example using the pre installed SDK to stream gnss data. 
```python
from anx_interface import Anx

def gnss_cb(data):
    print(data)
    
anx = Anx()
anx.start_device_gnss(cb=gnss_cb)
anx.wait()
```
