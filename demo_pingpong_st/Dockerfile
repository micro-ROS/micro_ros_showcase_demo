from microros/base

WORKDIR /uros_ws

RUN . install/setup.sh && \
apt update && \
apt install -y python3-pip

RUN . install/setup.sh && ros2 run micro_ros_setup create_firmware_ws.sh zephyr discovery_l475_iot1
RUN . install/setup.sh && ros2 run micro_ros_setup configure_firmware.sh ping_pong -t serial -d 1
RUN . install/setup.sh && ros2 run micro_ros_setup build_firmware.sh
