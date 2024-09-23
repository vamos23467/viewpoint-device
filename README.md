# viewpoint-device

## System for self-made HMD
1. Using THREE.js, project images from two fisheye cameras onto a hemisphere
2. IMU information of [LPMS-B2](https://www.lp-research.com/ja/9-axis-bluetooth-imu-lpmsb2-series)  is published by ROS, communicated by websocket, and received by the browser side.

<img width="500" alt="スクリーンショット 2024-09-23 23 21 45" src="https://github.com/user-attachments/assets/1095b4d3-0437-4a6f-9b65-420448041588">


## How to excute
1. Connection to imu sensor via ROS

~~~
roscore
rosrun openzen_sensor openzen_sensor_node _sensor_interface:="Bluetooth" _sensor_name:="your ble address"
~~~

2. Establish websocket server

~~~
roslaunch rosbridge_server rosbridge_websocket.launch
~~~

3. Establish local server

~~~
python -m http.server 8000
~~~
