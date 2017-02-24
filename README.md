# JetsonTK1Setup
foolproof setup guide for working with the Nvidia Jetson TK1

Things to know:

1. Don't do apt-get upgrade on a fresh TK1 system until you sudo apt-mark hold xserver-xorg-core. (https://devtalk.nvidia.com/default/topic/775070/jetson-tk1/-l4t-r19-x-notice-on-apt-get-upgrade-libglx-so-corruption/)
2. It's basically a good idea to go through the whole Jetpack procedure from the get-go. The Jetpack L4T application is a better getting started guide than Nvidia's getting started doc. Run the .run file with root privileges.
