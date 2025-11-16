FROM ubuntu:24.04

ARG CANABLE_GIT_URL="https://github.com/Elmue/CANable-2.5-firmware-Slcan-and-Candlelight.git"

ENV DEBIAN_FRONTEND=noninteractive
RUN echo 'APT::Install-Suggests "False";' >> /etc/apt/apt.conf.d/00-docker
RUN echo 'APT::Install-Recommends "False";' >> /etc/apt/apt.conf.d/00-docker
RUN /usr/bin/apt-get update
RUN /usr/bin/apt-get install -yq vim sudo tzdata 
ENV TZ="Europe/Madrid"

# Crossdev packages
RUN /usr/bin/apt-get install -yq ca-certificates build-essential git autoconf automake libtool pkg-config
RUN /usr/bin/apt-get install -yq gcc-arm-none-eabi libstdc++-arm-none-eabi-dev libstdc++-arm-none-eabi-newlib

# Prepare
USER ubuntu
WORKDIR /home/ubuntu
RUN git clone $CANABLE_GIT_URL CANable
COPY files/build_and_move_to_volume /home/ubuntu/CANable
WORKDIR /home/ubuntu/CANable

# EOF
