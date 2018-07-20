#FROM ubuntu:16.04
FROM resin/rpi-raspbian:stretch

# Install necessary packages for the installer
RUN apt-get update && apt-get install -y \
    build-essential \
    sed \
    sudo \
    tar \
    udev \
    wget \
    && apt-get clean

#RUN apt update -y && apt install -y python3 python3-dev python3-pip libatlas-base-dev

#RUN pip3 install https://github.com/lhelontra/tensorflow-on-arm/releases/download/v1.9.0/tensorflow-1.9.0-cp35-none-linux_armv7l.whl


#RUN apt -y update && apt install -y software-properties-common && add-apt-repository -y ppa:ubuntu-toolchain-r/test && apt-get -y update &&  apt-get upgrade -y libstdc++6


# Copy over the NCSDK
COPY ./ ncsdk/
# Set the current working directory to the cloned ncsdk directory
WORKDIR "/ncsdk"



# Run the installer
RUN make install
