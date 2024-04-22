# ESP_TF
run create.sf to update source this library just restructures the espressif tensorflow repo (https://github.com/espressif/tflite-micro-esp-examples) to be arduino compatible

Forked to make it work using the ESP-IDF@6.1.0 framework using Platform.io

TODO:

Change the create.sh to also change on creation: conv.cc, depthwise_conv.cc, esp_nn/conv.cc and esp_nn/depthwise_conv.cc like in the commit.

For the current project also change:
/ESP_TF/src/tensorflow/lite/micro/memory_planner/linear_memory_planner.h:48:3: note: in expansion of macro 'TF_LITE_REMOVE_VIRTUAL_DELETE'
/ESP_TF/src/tensorflow/lite/micro/tflite_bridge/micro_error_reporter.h:32:3: note: in expansion of macro 'TF_LITE_REMOVE_VIRTUAL_DELETE'
/ESP_TF/src/tensorflow/lite/micro/memory_planner/greedy_memory_planner.h:165:3: note: in expansion of macro 'TF_LITE_REMOVE_VIRTUAL_DELETE'

Make sure the TF_LITE_REMOVE_VIRTUAL_DELETE is not in the private section, but moved to the public section.
