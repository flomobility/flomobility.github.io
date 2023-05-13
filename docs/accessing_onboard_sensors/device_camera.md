---
layout: default
title: Camera
parent: Accessing onboard sensors
nav_order: 3
---

# Device Camera

Flo Edge comes with a 12 MP camera. To access this, you can either use the pre installed [cli tool](/docs/anx) or via the SDK with the following example.

## Available Streams
The anx cli tool can help you out here.

1. SSH into your Flo Edge
2. Run `anx camera_config`
3. This would print all available configurations for the on board camera

> Note : The SDK currently only supports MJPEG streams (pixel_format=0)

## Create a stream and read frames
Let's create an `MJPEG` stream with images sized `640x480` at `30fps`

### Using the CLI tool
> To know more use : `anx stream_camera --help`

1. SSH into your Flo Edge
2. Run `anx stream_camera --fps 30 --width 640 --height 480 --pixel_format 0`
3. You would then see on your terminal the dimensions of every new frame and measured fps
    ```bash
    $ anx stream_camera --fps 30 --width 640 --height 480 --pixel_format 0
    [hz = 30] (480, 640, 3)
    [hz = 30] (480, 640, 3)
    [hz = 30] (480, 640, 3)
    [hz = 29] (480, 640, 3)
    [hz = 29] (480, 640, 3)
    ...
    ```

### Using the SDK
The following example shows how you can use the SDK to read frames from the stream

```python
import cv2
import numpy as np
from anx_interface import Anx

import threading

class StreamCamera:
    def __init__(self):
        self.anx = Anx()
        self.running = False
        self.display_thread = None
        
    def start_stream(self, width, height, fps, pixel_format):
        self.anx.start_device_camera(fps=fps, width=width, height=height, pixel_format=pixel_format)
        self.running = True
        self.display_thread = threading.Thread(target=self.display_loop)
        self.display_thread.start()

    def display_loop(self):
        while self.running:
            ret, img = self.anx.device_camera.read() 
            if not ret: 
                continue 
            cv2.imshow('ImageWindow', img) 
            cv2.waitKey(1)

    def wait(self):
        self.anx.wait() # blocks till interrupt is received
        self.running = False
        self.display_thread.join()
        cv2.destroyAllWindows()
 
def main(): 
    stream_camera = StreamCamera()
    stream_camera.start_stream(fps=30, width=640, height=480, pixel_format=0)
    stream_camera.wait()

if __name__ == "__main__": 
    main()

```

