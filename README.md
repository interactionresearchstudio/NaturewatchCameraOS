# My Naturewatch Camera OS distribution builder


This repo uses [CustomPiOS](https://github.com/guysoft/CustomPiOS) built by
[Guy Sheffer](https://github.com/guysoft) to build the My Naturewatch Camera
operating system. It automates setting up the hotspot and installs all software
requirements, including OpenCV. By default, it pulls the latest commit on
the [NaturewatchCameraServer](https://github.com/interactionresearchstudio/NaturewatchCameraServer)
repository and sets it up to run as a service with systemd.

This has only been tested on a Pi 3B+ with the latest Raspbian Buster.

## How to set up a Raspberry Pi to build the OS distribution

```
# install docker and docker compose
curl -sL get.docker.com | sed 's/9)/10)/' | sh
sudo usermod -aG docker pi
sudo apt-get install -y libffi-dev libssl-dev python3 python3-pip
sudo apt-get remove python-configparser
sudo pip3 install docker-compose

# clone CustomPiOS
git clone https://github.com/guysoft/CustomPiOS.git

# clone this repo
git clone https://github.com/interactionresearchstudio/NaturewatchCameraOS.git

# up the container
cd NaturewatchCameraOS && sudo docker-compose up -d

# build!
sudo docker exec -it mydistro-build build
```

The zipped image will appear on the src/workspace/ directory and can be
transferred to an SD card to run on another Pi.
