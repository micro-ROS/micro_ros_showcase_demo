# micro-ROS demos for conferences

## ToF demo for ST Disco

```bash
# Build the image
# docker build demo_tof/ -t microros/rosindustrial:demo_tof

docker run -it --rm --privileged -v /dev:/dev microros/rosindustrial:demo_tof
ros2 run micro_ros_setup flash_firmware.sh

docker run -it --rm --net=host -v /dev:/dev --privileged microros/micro-ros-agent:foxy serial --dev /dev/serial/by-id/usb-STMicroelectronics_STM32_STLink_066FFF303931594E43221650-if02 -v6

ros2 topic echo /sensors/tof
ros2 topic echo /sensors/imu
ros2 topic pub /sensors/led std_msgs/Bool '{data: 1}'
```

## Pingpong demo for ST Disco

```bash
# Build the image
# docker build demo_pingpong_st/ -t microros/rosindustrial:demo_pingpong_st

docker run -it --rm --privileged -v /dev:/dev microros/rosindustrial:demo_pingpong_st
ros2 run micro_ros_setup flash_firmware.sh

docker run -it --rm --net=host -v /dev:/dev --privileged microros/micro-ros-agent:foxy serial --dev /dev/serial/by-id/usb-STMicroelectronics_STM32_STLink_066FFF303931594E43221650-if02 -v6

ros2 topic echo /microROS/ping
```

## Pingpong demo for RCLC

```bash
# Build the image
# docker build demo_pingpong_host/ -t microros/rosindustrial:demo_pingpong_host

docker run -it --rm --net=host microros/rosindustrial:demo_pingpong_host
source /opt/ros/foxy/setup.bash
source install/local_setup.bash 
ros2 run rclc_examples example_pingpong
```


<!-- 1. Explain the micro-ROS build system
2. Explain we are using Dockers because of the time
3. Flash the sensors demo
4. Open the agent in the ST serial port
5. Show the ros2 topic list

6. Explain the ping pong demo.
7. Flash the ping_pong app in the ST
8. Open the agent in the ST serial port

9. Open the micro-ROS host prebuilt Docker
10. Run the ping pong app -->
