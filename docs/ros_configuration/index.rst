ROS Configuration
===============================
.. toctree::
   :hidden:
   :glob:
    
   *
   ./*/index

What do I really need to configure for ROS to play nice?

Since our wireless perception communication is all based on ROS communication. We need to tweet our parameters to make the camera streaming in nearly real time, otherwise, there will be a lot of overhead causing high latency or low FPS.

Normally, ROS would not compress the image stream over the network, and this affects the internet bandwith and latency of the stream. 

In order to fix this, we should definite use some kind of compression method to encode our image stream before tranmitting and decode it when receiving. 

ROS provides a native way which is image transport, which automatically subscribes the original image topic and apply the compression before sending it over the network. Please see this for more details.[http://wiki.ros.org/image_transport#Overview]

We can create our own way to compressing the image and create another tunnel for communication outside of ROS. There is definitely a lot of pros and cons for this methods. Check here to send RGB+D image stream wireless with custom protocol. [https://github.com/ramonidea/wireless-data-transmission/tree/master/RealSense]

Image Transport
---------------------

Tutorial
http://wiki.ros.org/image_transport/Tutorials


**Using Image Transport**

	The local reconstruct point cloud requires Color and aligned_depth_to_color frames. We applied Compressed Image Transport on the color frames and CompressedDepth Image transport on the depth (Aligned depth to color) frames.

	But in order to make the wireless transmission smoothly, we may need to set the dynamic parameters of the transport, like the compression quality.
	:: 
		#After running the camera on the joule site, open another ssh window to joule.
		rosrun dynamic_reconfigure dynparam set /camera/color/image_raw/compressed jpeg_quality 70
		rosrun dynamic_reconfigure dynparam set /camera/aligned_depth_to_color/image_raw/compressedDepth png_lev

Not recommend to using CompressedDepth, since it would convert a 1D array to 3D array, which actually increase the bandwidth usage and decrease the speed of transmission. We should use custom lossless compression method for this. (We can just use Zlib to dump the depth image to a string format and decode it from the receiver back to image)

Networking
---------------------
Since the image steam takes up a lot of bandwidth of a network, we need to be careful about the settings of the network as well. 

Every image is usually 480*640*3 as the common lab test size. And RGB+D camera provides another layer, which brings the raw image size to 480*640*4. 

1. Depends on the task and purpose of the image stream, we can use either TCP or UDP for tranmission. 

2. Make sure no other lossy wifi frequency or inteference nearby

3. If transmitter and receiver are relatively close to each other, we should preferably use 5Ghz, not 2.4 Ghz. 

4. Try to use private connection, not using public mesh wifi network, like school or mall wifi. 
