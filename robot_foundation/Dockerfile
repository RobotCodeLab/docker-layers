FROM ros:foxy
ENV ROS_DISTRO foxy

# INSTALL AN EASY-TO-USE EDITOR
RUN apt-get update && apt-get install -y \
    ca-certificates \
    curl \
    gnupg \
    lsb-release

RUN curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
RUN echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
RUN sudo apt update && sudo apt install -y \
    docker-ce \
    docker-ce-cli \
    containerd.io

# docker run -v /var/run/docker.sock:/var/run/docker.sock -ti rcl
# docker pull moveit/moveit2:foxy-release

# MAKE PYTHON3 THE DEFAULT PYTHON
RUN echo 'alias python=python3 \ 
    source "/opt/ros/$ROS_DISTRO/setup.bash" \
    echo "----------------------" \
    echo "RCL FOUNDATION 0.0.1" \
    echo "----------------------"' >> .bashrc

WORKDIR /root
RUN  git clone https://github.com/RobotCodeLab/docker-layers.git
RUN docker build docker-layers/docker-rviz2 -t dkr-rviz2


CMD ["bash"]