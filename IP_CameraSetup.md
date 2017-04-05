To get off the ground:

sudo apt-get install libopencv4tegra-python

This is a way to get started using opencv on the tk1. This library doesnt use the GPU resources- code has to be ported over later.

Chosen workflow:

Since the opencv python api doesn't have the ability to use GPU stuff, here's what I settled on:
1. If I need to use the GPU for my opencv processing, I'll write that code in c++.
2. I'll use swig to wrap that code. Tried boost.python, it didn't work.
3. Any outputs will be handled by python, pulling fully-cooked data out of the c++ module.

Setting up swig:
sudo apt-get install swig

Ignore this: http://www.swig.org/tutorial.html and this: http://www.swig.org/Doc3.0/SWIGDocumentation.html

Use this: http://www.swig.org/Doc3.0/Python.html

The important detail is to use distutils to compile your extension module.

Opencv c++ gpu compilation command (from cudacasts video):
g++ yourfile.cpp -lopencv_core -lopencv_imgproc -lopencv_highgui -lopencv_video -lopencv_gpu -o yourcompiledscript

DHCP config:

Using the tk1 as a dhcp server & gateway. Remember to configure your DHCP interface in NetworkManager, with gateway and address being same, and subnet mask matching what you entered in dhcpd.conf.
