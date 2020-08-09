Drivers / Interface Software
=============================
Linux (Ubuntu 18.04) [To be tested on 20.04]

Intel librealsense: https://github.com/IntelRealSense/librealsense

Relsense ros wrapper: https://github.com/IntelRealSense/realsense-ros

Installation
*************

TL;DR
::
	# Add apt repository server key
	sudo apt-key adv --keyserver keys.gnupg.net --recv-key F6E65AC044F831AC80A06380C8B3A55A6F3EFCDE || sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-key F6E65AC044F831AC80A06380C8B3A55A6F3EFCDE	
	
	# Add apt repository server to local list
	sudo add-apt-repository "deb http://realsense-hw-public.s3.amazonaws.com/Debian/apt-repo bionic main" -u
	
	# Install realsense libraries
	sudo apt-get install librealsense2-dkms	
	sudo apt-get install librealsense2-utils



