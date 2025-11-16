# Purpose
This Dockerfile builds a basic ubuntu 24.04 image with the required toolchain for ARM crossdev.

# Build the image
Execute `./1_build`. This script will:
- build the docker image from ubuntu:24.04
- clone the git repository with CANable 2.5 firmware
- install a scipt to build all variants of the CANable 2.5 firmware

# Run the container
Execute `./2_run`. This script will:
- prepare an `output` directory for compiled firmwares
- start the container with the local `output` directory mounted on `/mnt`
- Execute the script

# Expected output
The `output` directory will contain one subdirectory per firmware type, plus one directory for the build logs (stdout + stderr):
```
Build_STM32G431xx_Candlelight_MksMakerbase
Build_STM32G431xx_Candlelight_OpenlightLabs
Build_STM32G431xx_Slcan_MksMakerbase
Build_STM32G431xx_Slcan_OpenlightLabs
logs
```
