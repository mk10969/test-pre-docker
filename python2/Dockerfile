# docker build -t switchbot2 .
# docker run -it switchbot2

FROM python:2.7.18-stretch

SHELL ["/bin/bash", "-c"]

RUN apt-get update \
    && apt-get install -y git

### install bluetooth library (python2)
RUN apt-get install -y python-pexpect
RUN apt-get install -y libusb-dev libdbus-1-dev libglib2.0-dev
RUN apt-get install -y libudev-dev libical-dev libreadline-dev
RUN pip install bluepy

### mv
WORKDIR /opt

### download switch bot module
RUN git clone https://github.com/OpenWonderLabs/python-host.git

### mv
WORKDIR /opt/python-host

### run
# CMD [""python", "switchbot.py", "DA:3C:93:0E:7D:C1", "Press"]
CMD ["sleep","1000"]
