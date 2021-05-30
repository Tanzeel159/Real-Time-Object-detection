# Real-Time-Object-detection
![1_N8H9Z3RDQz2LW_NHh9l3Fw](https://user-images.githubusercontent.com/20295349/120095122-bf36b280-c141-11eb-8fbe-380d0a813ad9.jpeg)


### Table of Contents
-  [Introduction](#introduction)
-  [System Analysis](#system-analysis)
-  [Proposed System](#proposed-system)
-  [Requirements](#requirements)
-  [Algorithm](#algorithm)
-  [Implementation](#implementation)

# Introduction
When we're shown an image, our brain instantly recognizes the objects contained in it. On the other hand, it takes a lot of time and training data for a machine to identify these objects.The processing of visual data happens in the ventral visual stream. It is a hierarchy of areas in the brain which helps in object recognition. Humans can easily recognize different sized objects and put them in the same category.
Object detection refers to the capability of computer and software systems to locate objects in an image/scene and identify each object. Object detection has been widely used for face detection, vehicle detection, pedestrian counting, web images, security systems and driverless cars. 
Like human brain composed of neurons and the feedforward processing, the artificial neurons are used in the deep neural networks for performing object detection.

[Back to the Top](#table-of-contents)

# System Analysis
- Faster RCNN
- YOLO V3

[Back to the Top](#table-of-contents)
# Proposed System
SSD: Single Shot MultiBox Detector (by C. Szegedy et al.) was released at the end of November 2016 and reached new records in terms of performance and precision for object detection tasks, scoring over 74% mAP (mean Average Precision) at 59 frames per second on standard datasets such as PascalVOC and COCO.
- Single Shot: this means that the tasks of object localization and classification are done in a single forward pass of the network
- MultiBox: this is the name of a technique for bounding box regression developed by Szegedy et al. (we will briefly cover it shortly)
- Detector: The network is an object detector that also classifies those detected objects

Advantages: 
It is clearly faster than Faster-RCNN and optimized for low end devices.

[Back to the Top](#table-of-contents)

# Requirements

![WINWORD_0XxYEQqaFh](https://user-images.githubusercontent.com/20295349/120095338-112c0800-c143-11eb-84b4-5609f54cf0ad.jpg)


[Back to the Top](#table-of-contents)

# Algorithm 

- Pass the image through a series of convolutional layers
- For each location in each of these feature maps, use a 3x3 convolutional filter to evaluate a small set of default bounding boxes.
- For each box, simultaneously predict the bounding box offset and the class probabilities
- During training, match the ground truth box with these predicted boxes based on IoU(Intersection over union). 
- Instead of using all the negative examples, sort the results using the highest confidence loss for each default box and pick the top ones so that the ratio between the negatives and positives is at most 3:1.

![image](https://user-images.githubusercontent.com/20295349/120095406-7b44ad00-c143-11eb-9d4c-c2218864a255.png)


[Back to the Top](#table-of-contents)

# Implementation

- Install Tensorflow-GPU 1.5
- Setup Tensorflow Directory and Anaconda Virtual Environment
- Download Tensorflow Object Detection API
- Download the SSD-Mobilenet FPN

![image](https://user-images.githubusercontent.com/20295349/120095514-06be3e00-c144-11eb-8a92-be6c4609aa9a.png)

- Set up new Anaconda virtual Environment and downloading libraries

![anaconda](https://user-images.githubusercontent.com/20295349/120095605-70d6e300-c144-11eb-825a-5851bf6ee343.png)

- Configure PYTHONPATH environment variable 
- Test TensorFlow setup to verify it works


![image](https://user-images.githubusercontent.com/20295349/120095633-94019280-c144-11eb-9222-6158a20ba3be.png)

- Gather and label images

![snipping](https://user-images.githubusercontent.com/20295349/120095648-a5e33580-c144-11eb-81b6-abd7619d9379.png)


- Generate training data
- Create Label Map and configure training

![label](https://user-images.githubusercontent.com/20295349/120095668-bc898c80-c144-11eb-8671-7b530122091d.png)

- Run the training 

![image](https://user-images.githubusercontent.com/20295349/120095706-fa86b080-c144-11eb-92ee-afb1ef6aef80.png)

![image](https://user-images.githubusercontent.com/20295349/120095715-17bb7f00-c145-11eb-823e-47d12a75a050.png)


[Back to the Top](#table-of-contents)
