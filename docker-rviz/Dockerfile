FROM scratch

# INSTALL AN EASY-TO-USE EDITOR
RUN apt-get update && apt-get install -y \
    curl \
    lsb-release \
    ros-foxy-rviz2


# MAKE PYTHON3 THE DEFAULT PYTHON
RUN echo 'alias python=python3 \ 
    source "/opt/ros/$ROS_DISTRO/setup.bash" \
    echo "----------------------" \
    echo "RCL RVIZ 0.0.1" \
    echo "----------------------"' >> .bashrc

WORKDIR /root
CMD ["bash"]