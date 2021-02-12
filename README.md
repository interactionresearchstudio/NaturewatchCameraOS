# My Naturewatch Camera OS distribution builder


This repo uses [CustomPiOS](https://github.com/guysoft/CustomPiOS) built by
[Guy Sheffer](https://github.com/guysoft) to build the My Naturewatch Camera
operating system. It automates setting up the hotspot and installs all software
requirements, including OpenCV. By default, it pulls the latest commit on
the [NaturewatchCameraServer](https://github.com/interactionresearchstudio/NaturewatchCameraServer)
repository and sets it up to run as a service with systemd.

This has only been tested on a Pi Zero W.

## How to set up a Raspberry Pi to build the OS distribution

write the latest release to an SD card with atleast 16GB of space.
