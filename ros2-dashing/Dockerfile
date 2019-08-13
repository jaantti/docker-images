FROM ubuntu:18.04
MAINTAINER Antti Jaaniste (jaantti@gmail.com)

ENV DEBIAN_FRONTEND=noninteractive 

RUN apt-get update
RUN apt-get upgrade -y
RUN apt install -y curl gnupg2 lsb-release locales git
RUN locale-gen en_US en_US.UTF-8
RUN update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8
RUN export LANG=en_US.UTF-8
RUN curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | apt-key add -
RUN sh -c 'echo "deb [arch=amd64,arm64] http://packages.ros.org/ros2/ubuntu `lsb_release -cs` main" > /etc/apt/sources.list.d/ros2-latest.list'
RUN apt update
RUN apt install -y ros-dashing-ros-base
RUN apt install -y python3-argcomplete python3-colcon-common-extensions
RUN echo "source /opt/ros/dashing/setup.bash" >> ~/.bashrc