---
layout: default
title: Running deeplearning models
nav_order: 7
permalink: /docs/running_deeplearning_models
---

# Running deeplearning models

Flo Edge has out of the box capabilities for Deep learning. It comes equipped with Qualcomm's Adreno 630 GPU and Hexagon 685 DSP along with an SDK to harness their compute.

## Important
### Inferencing
- Currently only `.tflite` models are supported, and inferencing can be done only on the GPU.
- DSP support will be shipped in a future software update.

### Training
When training models to be run on Flo Edge, be sure to check out the [operations supported](https://www.tensorflow.org/lite/performance/gpu#supported_ops) by the GPU


## Using the SDK
The following code snippets should help you understand using the SDK to inference models.

`[inputs] --> model.tflite --> [outputs]`

1. Load model
  ```python
  from anx_interface import TfliteInterface, DeviceType
  tflite_interface = TfliteInterface(DeviceType.GPU)
  # success is True if model loaded correctly else False
  success = tflite_interface.load_model("/path/to/model.tflite")
  ```
2. Set inputs
  ```python
  tflite_interface.set_input([input1, input2, ...])
  ```
3. Invoke model
  ```python
  tflite_interface.invoke()
  ```
4. Get output
  ```python
  output1, output2, ... = tflite_interface.get_output()
  ```

## Examples
Be sure to check out our [examples repo](https://github.com/flomobility/floedge_examples/tree/master/ai).We've added example scripts to run well known models like YOLO v5, MiDAS, etc.