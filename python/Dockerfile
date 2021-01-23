# docker build -t switchbot .
# sudo docker run --net=host --privileged -it switchbot /bin/bash

FROM python:3.7.2

SHELL ["/bin/bash", "-c"]

RUN apt-get update \
    && apt-get install -y sudo \
    && apt-get install -y git

### sudoer追加
RUN useradd --uid 1001 --create-home --shell /bin/sh -G sudo,root debian-sudoer
RUN echo '%sudo ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers

### install bluetooth
RUN apt-get install -y bluez bluetooth

### install bluetooth library (python3)
RUN apt-get install -y python3-pip
RUN apt-get install -y libboost-python-dev
RUN apt-get install -y libboost-thread-dev
RUN apt-get install -y libbluetooth-dev
RUN pip3 install pybluez
RUN pip3 install gattlib

### mv
WORKDIR /opt

### download switch bot module
RUN git clone https://github.com/OpenWonderLabs/python-host.git

### mv
WORKDIR /opt/python-host

### run
# CMD ["sudo", "python3", "switchbot_py3.py", "-d", "DA:3C:93:0E:7D:C1", "-c", "press"]
CMD ["sleep","1000"]
