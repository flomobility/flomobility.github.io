---
layout: default
title: Running deeplearning models
nav_order: 6
permalink: /docs/running_deeplearning_models
---

# Running deeplearning models

`[inputs] --> model.tflite --> [outputs]`

1. Load model
```python
from anx_interface import TfliteInterface, DeviceType

# success is true if model loaded correctly else false
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
