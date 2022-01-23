# Pothole_Detection
Preprocessing of images and classification using convolutional neural networks (CNN) models 

ABSTRACT

A huge problem in roads is the formation of potholes. These can vary in size from small holes in the road the size of little bowls to large holes with diameters half the width of the road. These potholes cause continuous wear and tear on vehicles that pass these roads regularly, leading to huge costs in the long term. At the other extreme potholes have been known to cause serious injuries to commuters on the roads and might even lead to death. Potholes are a danger that need to be tackled as quickly as possible but authorities take a long time to identify and act on this problem. One way to hasten this is to have drones or remote controlled vehicles that can visit roads and identify if a road contains potholes or not in a few seconds. Using digital image processing to identify potholes would help greatly in documenting and planning road redevelopment projects. In this group-project we propose one such method. We use the concept of transfer learning to identify potholes in roads with accuracies higher than 85% on the test data.  With the largescale implementation and integration of systems such as this in urban planning, the threats faced by potholes can be greatly reduced.





INTRODUCTION

With the increase in world’s population, there has been increasing load on the infrastructure. Roads have been flooded with the vehicular traffic. It has become increasingly difficult to manage this traffic. This is the prime motivation behind making a vehicle intelligent enough to aid driver in various aspects. One of the increasing problems the roads are facing is worsened road conditions. Because of many reasons like rains, oil spills, road accidents or inevitable wear and tear make the road difficult to drive upon. Unexpected hurdles on road may cause more accidents. Also because of the bad road conditions, fuel consumption of the vehicle increases; causing wastage of precious fuel. Because of these reasons it is very important to get the information of such bad road conditions, Collect this information and distribute it to other vehicles, which in turn can warn the driver. But there are various challenges involved in this. First of all there are various methods to get the information about the road conditions. Then this information must be collected and distributed to all the vehicles that might need this information. Lastly the information must be conveyed in the manner which can be understood and used by driver. We in this project try to design and build such a system. In this system the access point collects the information about the potholes in the vicinity of a wireless access point and distributes to other vehicles using a wireless broadcast. Here 'vicinity' is a user defined term. Ideally the vicinity is every rout till the next access point







PROBLEM STATEMENT AND OBJECTIVES
Pothole detection system is a system that aims at warning the driver about the uneven roads and potholes in its path. We study the different ways in which goal of the system can be achieved. We justify the methods we have chosen in this projects. And then we give details about the working of the different subsystems. The problem statement can be given as follows. This system consists of two components one is mobile node and other is the access point. Access points responsible for storing the information about potholes in its vicinity, taking the feedback from vehicles, updating the information in repository and broadcasting the information to other vehicles. Whereas Mobile node which is the small device placed in vehicle is responsible for sensing those potholes which it did not have previous information about, locating and warning the driver about the potholes which it has information about, and giving the data about newly sensed pothole to access point. The whole scenario works as follows. While deploying the access point we feed in some initial data about potholes to it. Then it keeps on broadcasting the data. Vehicle equipped with the client device catches that data. Now the device has the information about the locations of potholes. The device is responsible for warning the driver about occurrences of pothole. But new potholes may always be formed because of environment or fatigue. So client device also acts as a sensor and finds out the occurrence of newly formed potholes on the road. If it finds out any new potholes it gives data of new pothole to Access point in terms of the feedback. Access points updates this information to its data store and then adds it to the information broadcast.
There are various challenges involved in this project.
• Client device must be able to sense the pothole. It will be an added advantage if it can characterize the pothole telling how severe it is.
• Placement of access points is an important factor. It should be in such a way that the data should be distributed to maximum vehicles. 
• Communication between access point and client device can have many problems which should be resolved. Some of the problems that communication can face are interference, Low throughput due to large no of client devices, end to end reliability. 
• Data representation should be in such a way that the client device should be able to locate and warn the driver about the potholes which it has information about.







METHODOLOGY:

CNN Model using RESNET 50

A ResNet is a standard feature extractor which detects low-level features at early layers, and high-level features at later layers. The network accepts an image of 1, 024 × 1, 024. The image is padded with zeros if it is not given as per the assumed aspect ratio.
Thus, our plan was to collect data containing thermal images of roads with and without potholes. After data acquisition, the images were pre-processed to remove the temperature scales and other marks and brought to the same dimensions by resizing and cropping. After this, various techniques were applied to augment the collected data to increase the number of images in the dataset. Finally, classification using convolutional neural networks (CNN) models was done and the results were compared. The below figure depicts the workflow of the proposed work.
												
 


Data pre-processing
After the collection of images of potholes and non-potholes, we performed the pre-processing of the collected image dataset. During pre-processing of the dataset, the following various operations were performed on the images.
Resizing of images
After trying to run the CNN model on the cropped images, the hardware (GPU memory) was found not to be enough to handle images of the above-mentioned pixels and 4500 images (after augmentation), therefore the images were resized to half i.e. 256 x 256 pixels before training.
Classification of images using Convolutional Neural Networks
ResNet (Residual Network) models were chosen as they are trained on an ImageNet dataset that contains a very large number of images of various objects. Also, these networks have performed fairly in various deep learning competitions with very less error percentage. They also solve the problem generally observed in large networks that is with increase in depth of networks, saturation and degradation in accuracy start taking place.
ResNet or Residual Network uses residual learning instead of trying to learn some features. Residual can be simply understood as subtraction of features learned from input of that layer. The core idea of ResNet is introducing a shortcut connection that skips one or more layers. ResNet50 has 50 layers deep, below is the architecture of ResNet50 with 34 layer residual.
 
Results and Discussion
Parameters:
●	Batch normalization after the last layer 5 convolution layers with output size 16,32,64,128
●	Dropout 0.7 in the dense layer and sigmoid activation
●	Learning rate = 0.01, decay = 0.0
●	No. of epochs = 50
●	Batch size = 32768

Graphical Representation of the Results:
Model Accuracy:
 Model accuracy v/s Epoch
Model Loss:
 
Observations:
●	From this model, we achieved an average training accuracy of 96.2% and average validation accuracy of 89.42%
●	The training and validation loss of 27.57%
●	Test accuracy achieved was 96.06%


EXPERIMENTAL RESULTS & ANALYSIS
Smooth road with bumps : 
On a smooth road we placed some pins to generate the bumps. Then we ran FireBird over such road. And as shown in the graph below we got sudden change or spikes in the readings on at least one of the axis. 
                          
Uneven roads :
 For this the FireBird was run on three types of road smooth, moderately uneven road and highly uneven road. The graphs produced are as follows.
                          
                          
CONCLUSION:

Vibration were seen to be increased in terms of the accelerometer reading. Standard deviation of at least one of the Axis was increased significantly when we made the road conditions increasingly worse. Whereas large difference was found between readings of smooth road and moderately uneven roads.

Various choices for implementing the System have been studied. These choices were also compared to each other on various criterion. We have specified the High level design choices of the Subsystems and justified the corresponding selections. We did experiments on the platform called Firebird. We were also able to characterize road condition into categories like smooth, moderately uneven and highly uneven from the results of the experiments.











REFERENCES

1.	R Gass, J Scott, C Diot, “Measurements of In-Motion 802.11 Networking”, IEEE Workshop on Mobile Computing System and Applications, 2006 

2.	X Zhang, JK Kurose, BN Levine, D Towsley, H Zhang , “Study of a bus-based disruption-tolerant network: mobility modeling and impact on routing”, 13th annual ACM international conference, 2007 


3.	 “http://www.its.dot.gov/vii”, RITA | ITS | Vehicle Infrastructure Integration, JAN 2007

4.	 “http://dev.emcelettronica.com/datasheet/st/LIS3L06AL”, Datasheet of ST LIS3L06AL accelerometer, JAN 2008 


5.	 “http://www.gps.gov/”, Global Positioning System, JAN 2007 

6.	JW Byers, M Lubyt, M Mitzenmachert, “A Digital Fountain Approach to Reliable Distribution of Bulk Data”, SIGCOMM, 1998 


7.	M Mitzenmacher, “Digital fountains: a survey and look forward”, Information Theory Workshop, 2004. IEEE, 2004 

8.	 “Pothole detection System using WiFi”, Mtech project Report submitted by Shonil Vijay, JUL 2007 


9.	 “FireBird Reference manual”, Embedded and real Time Systems Lab, Computer science and Engineering Department, IITB
