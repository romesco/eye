SSD
===

Main Source Code
################

For running SSD on the Jetson Nano, there are some great established github repositories out there. A highly recommended repo is `<https://github.com/dusty-nv/jetson-inference>`_ which is by Nvidia developers themselves. 

Please follow the installation and build instructions of this repo for proper functionality. 

If you would like the ability to run **ssd_mobilenet_v2** as a **rosnode** please refer to the subset repository of the one above `<https://github.com/dusty-nv/ros_deep_learning>`_ and follow the directions to bring up rosnodes for instant detection!

Quick Integration of SSD with Existing Code
###########################################

If you want a way to quickly integrate deep learning model inferencing through python (not from command line but internally as part of another script or project etc) please refer to the following 4 lines of code that is using the repository above::
        
        import jetson.inference
        import jetson.utils
        class PeopleDetection:
                def __init__(self):
                self._net = jetson.inference.detectNet("ssd-mobilenet-v2")

                def get_detections(self, image):
                        img = jetson.utils.cudaFromNumpy(image)
                        width = image.shape[1]
                        height = image.shape[0]
                        detections = self._net.Detect(img, width, height)
                        return detections


The code chunk above is an example of a class that easily allows you to pass any image internally in python and returns a list of detections as objects which have their own attributes. This is the simplest way to integrate this github repository with your own code as part of internal detection of data.

**NOTE**: The code above takes in a open-cv image which is why **cudaFromNumpy** is used, however this is not needed for just passing in a RGB image.
