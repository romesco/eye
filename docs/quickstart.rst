Quickstart
==========

|example|

.. |example| image:: _images/quickstart_header.png

| This quickstart is designed around the most common use case of the
| `Nvidia Jetson Nano <https://developer.nvidia.com/embedded/jetson-nano-developer-kit/>`_ + `Intel Realsense D435 <https://www.intelrealsense.com/depth-camera-d435/>`_.

Configure Nano
---------------------

0. Startup Nano
*****************
If the Nano is completely stock, please first follow Nvidia's:
`Getting Started Guide <https://developer.nvidia.com/embedded/learn/get-started-jetson-nano-devkit>`_.

For best results, install Ubuntu 18.0.4 LTS as the Nano's OS.

1. Download Drivers
********************


2. Download Libraries
**********************

Configure Realsense
--------------------------

1. Download Drivers
********************

Download the Intel Realsense drivers though librealsense:
::
	# Add apt repository server key
	sudo apt-key adv --keyserver keys.gnupg.net --recv-key F6E65AC044F831AC80A06380C8B3A55A6F3EFCDE || sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-key F6E65AC044F831AC80A06380C8B3A55A6F3EFCDE	
	
	# Add apt repository server to local list
	sudo add-apt-repository "deb http://realsense-hw-public.s3.amazonaws.com/Debian/apt-repo bionic main" -u
	
	# Install realsense libraries
	sudo apt-get install librealsense2-dkms	
	sudo apt-get install librealsense2-utils

2. Configure settings
**********************
    

3. Test Realsense
******************


Algorithmic Framework
-----------------------------------

1. Install Pytorch / or Tensorflow 
************************************

2. Download Model (easiest example) 
************************************

3. Run inference
*****************


