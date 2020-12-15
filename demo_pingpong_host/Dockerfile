from ros:foxy

RUN mkdir ros_ws
WORKDIR /ros_ws

RUN . /opt/ros/foxy/setup.sh && \
apt update && \
apt install -y python3-pip ros-foxy-osrf-testing-tools-cpp ros-foxy-test-msgs ros-foxy-example-interfaces

RUN git clone -b feature/ping_pong_demo https://github.com/micro-ROS/rclc src/rclc
RUN . /opt/ros/foxy/setup.sh && colcon build
