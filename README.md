# JetsonTK1Setup
foolproof setup guide for working with the Nvidia Jetson TK1

Things to know:

1. Don't do apt-get upgrade on a fresh TK1 system until you sudo apt-mark hold xserver-xorg-core. (https://devtalk.nvidia.com/default/topic/775070/jetson-tk1/-l4t-r19-x-notice-on-apt-get-upgrade-libglx-so-corruption/)
2. It's basically a good idea to go through the whole Jetpack procedure from the get-go. The Jetpack L4T application is a better getting started guide than Nvidia's getting started doc. Run the .run file with root privileges.

FTDI RS232 Adapter Support:

My use case involves output to an ENTTEC DMX USB PRO. The chip in there is the same as many common usb-to-serial adapters used to program arduinos:
http://elinux.org/Jetson/Tutorials/Program_An_Arduino#FTDI_kernel_module

Near as I can tell, this process directs you compile a new kernel with the ftdi_sio kernel module included, then extract that module and patch it into your working kernel. But there are wrinkles:

https://devtalk.nvidia.com/default/topic/810295/jetson-tk1/jetson-tk1-ftdi-works-on-19-3-but-not-21-2/


The article also misses a step- in 'configuring the kernel', before you run 'make menuconfig', you have to cd into the newly-spawned kernel directory that was created in preceding steps.
