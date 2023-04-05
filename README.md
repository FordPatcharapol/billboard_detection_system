# Billboard Detection System

Table of Contents
1. Introduction
2. Main Components of The System
3. Technologies Used
4. Optimizations for Edge and Cloud Computing
5. Integration with Protocol Buffers / JSON
6. Deployment
7. Summary
8. Reference

# Introduction
This repository provides a detail overview of the design and installation of billboard detection systems across Thailand, utilizing cutting-edge technologies in Data Science, Machine Learning, Cloud Computing, and Edge Computing to deliver optimal performance in terms of speed and resource efficiency. Additionally, the system incorporates buffer and JSON protocols to facilitate efficient data communication.

![image](https://user-images.githubusercontent.com/106796461/229883664-2e9b2386-b558-4a5f-ad83-13160d57274e.png)

# Main Components of The System
- Data Collection and Preprocessing
  
  This section collects the information needed to train the model to detect specific objects. (In this system will focus on the billboard), which will be image or video information. which can be collected from various sources such as traffic cameras, CCTV or mobile phones, etc., and in the preparation of data to be used for training data. It will start by cleaning up the data such as removing the data that we don't want, images we don't care or duplicate images including the size of the image Then take all the information images that we have prepared to annotation. The annotation should contain the coordinates of the bounding boxes for each object in the image. In this part of the preparation, if we can prepare the data well in the right amount of data, we will be able to create a model with good efficiency.
  
- Machine Learning Model
  After we have prepared the data, before we can use the data to train the model, it is necessary to divide the data we have into 3 sets: training, validation, and testing sets. The training sets will be used to train your model. Validation sets are used to evaluate the performance of your model during training. and a series of tests will be used to evaluate the final performance of your model.
 
- Edge and Cloud Computing

# Technologies Used
 - Data Science: Python, NumPy, pandas, OpenCV
 - Machine Learning: YOLO
 - Cloud Computing: AWS, Google Cloud Platform
 - Edge Computing: NVIDIA Jetson, Raspberry Pi
 - Data Format: Protobuf / JSON


# Optimizations for Edge and Cloud Computing


# Integration with Protocol Buffers / JSON


# Deployment


# Summary


# Reference



