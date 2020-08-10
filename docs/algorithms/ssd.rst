SSD
===

Main Source Code
################

For running SSD on the Jetson Nano, there are some great established github repositories out there. A highly recommended repo is `<https://github.com/dusty-nv/jetson-inference>`_ which is by Nvidia developers themselves. 

If you would like the ability to run **ssd_mobilenet_v2** as a **rosnode** please refer to the subset repository of the one above `<https://github.com/dusty-nv/ros_deep_learning>`_ and follow the directions to bring up rosnodes for instant detection!

Quick Integration of SSD with Existing Code
###########################################

If you want a way to quickly integrate deep learning model inferencing through python (not from command line but internally) please refer to the following code that is using the repository above::
        
        import jetson.inference
        import jetson.utils
        net = jetson.inference.detectNet('ssd_mobilenet_v2')
        detections = net.Detect(img)

The code above easily allows you to pass any image internally in python and returns a list of detections as objects which have their own attributes. This is the simplest way to integrate this github repository with your own code as part of internal detection of data.

