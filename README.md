# docker-coreelec
Docker 20.10 for CoreELEC distro

CoreELEC is a Linux system (JeOS - Just enough Operational system) that works on devices with Amlogic processors. It has the minimum required to run the Kodi system. Some of its advantages is that it uses the original Amlogic Kernel for Android (4.9.113) and has support for almost all device embedded (Bluetooth, WiFi, Ethernet, Audio and Video Output, Hardware Video Decoding) using the original Android structure while other Linux distributions often do not support all installed devices.

Usually new software are installed through add-on using the interface itself (Kodi), where the software is usually aimed for multimedia activities. One exception is the system-oriented software Docker, however it is limited to version 19.

Generally boxes sold with the Amlogic processors line have reasonably high memory for this type of system (4/8 GB) and multi-core processor with a very attractive price. The possibility of using a docker, especially the latest versions with security fixes, can make this type of equipment very efficient for various domestic applications, such as servers for IoT.

This project provides structure to install the Docker version 20.10, latest (fetched directly from Github), on these devices.

##Compilation instructions (Linux X86_64/arm64 and macOS)
**Note: If you're compiling it on a platform with a different target architecture, you have to use cross-compiling (buildx).**

First step: know the device architecture with CoreELEC
- Enable ssh via Kodi / CoreELEC interface on the device
- Access the device via SSH
- Look for the architecture with the uname command:

```bash
# uname -m
```

####Output table

Output contains |Architecture is
------|------------
aarch64|arm64
arm7   |arm7
arm6   |arm6

Second step: compile it on a platform with docker installed and running

To compile for the same platform

```bash
./compile-docker.bash buid
```

To compile on different platform (<arch> is the architecture: arm64, arm7 or arm6)

```bash
./compile-docker.bash buidx -a <arch>
```

**Depending on your system performance the compilation can take up to 30 minutes.**

It will generate a file 