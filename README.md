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

<div align="center">
  <img src="https://github.com/FordPatcharapol/billboard_detection_system/blob/main/imgs/billboard_detection.png"/>
</div>

# Introduction
This repository provides a detail overview of the design and installation of billboard detection systems across Thailand, utilizing cutting-edge technologies in Data Science, Machine Learning, Cloud Computing, and Edge Computing to deliver optimal performance in terms of speed and resource efficiency. Additionally, the system incorporates buffer and JSON protocols to facilitate efficient data communication.

# Main Components of The System
- Data Collection and Preprocessing
  
  This section collects the information needed to train the model to detect specific objects. (In this system will focus on the billboard), which will be image or video information. which can be collected from various sources such as traffic cameras, CCTV or mobile phones, etc., and in the preparation of data to be used for training data. It will start by cleaning up the data such as removing the data that we don't want, images we don't care or duplicate images including the size of the image Then take all the information images that we have prepared to annotation. The annotation should contain the coordinates of the bounding boxes for each object in the image. In this part of the preparation, if we can prepare the data well in the right amount of data, we will be able to create a model with good efficiency.
  
- Machine Learning Model
  After we have prepared the data, before we can use the data to train the model, it is necessary to divide the data we have into 3 sets: training, validation, and testing sets. The training sets will be used to train your model. Validation sets are used to evaluate the performance of your model during training. and a series of tests will be used to evaluate the final performance of your model.
   
<div align="center">
  <img src="https://github.com/FordPatcharapol/billboard_detection_system/blob/main/imgs/split_data.PNG"/>
</div>
 
- Edge Computing and Cloud Computing
   - **Edge Computing** - Edge computing refers to processing data closer to its source, such as sensors, cameras or smart devices, rather than sending it to central processing or cloud servers alone. The main goal of edge computing is to reduce the latency and bandwidth required for processing data to central or cloud servers by processing data close to the source for real-time performance.
      
      **Advantages** 
      - Reduce the Latency and Bandwidth Required.
      - Processing Data in Real-Time Performance.
      - Increased System Resilience and Scalability
      
      **Disadvantages**
      - Security Risks
      - High Cost
      - Increased Complexity of Overall System
      - Limited Resources


  - **Cloud Computing** - Cloud computing refers to the service of computing services, including servers, storage, databases, networking, software, analytics, and artificial intelligence, over the internet. It allows users to access and utilize these resources on a pay-as-you-go basis without having to invest in and manage physical infrastructure like data centers and servers. Cloud computing enables users to scale their infrastructure up or down based on their needs, providing flexibility and cost efficiency. This is particularly useful for businesses and organizations that experience fluctuating workloads or require rapid deployment of new applications.
   
      **Advantages** 
      - Cost Savings
      - Scalability and Flexibility
      - High Security
      - Easy to Updates and Maintenance
      
      **Disadvantages**
      - Hidden Costs / Data Transfer Costs
      - Security and Privacy Concerns
      - Dependency on Internet Connectivity
      - Limited Control and Customization


# Optimizations for Edge Computing and Cloud Computing
  * in designing the system to be effective The system must be managed well concurrently. But ultimately it depends on individual needs and design. In this section, I would like to present a system performance improvement for both Cloud Computing and Edge Computing models by adopting a container-based computing approach. made to be used in processors in the architecture Microservices  and proper data management for forwarding data in different formats.Microservice is the development of a software system that divides the functionality of an application into smaller units. and can work independently of each other Microservices often represent specific functions or capabilities that can be developed, tested, and extended independently from the rest of the application.

  * By designing a cloud computing system, it has advantages and disadvantages as mentioned earlier. In this design, I have designed all processing, data linking, and storage on the cloud, making operation and maintenance easy. Since most of the systems are located in the same place, there must be a shared resource sharing. Therefore, proper management is required. which I have brought to work Microservices Come to help in dividing the work separately and using the bus as an intermediary to link the used data. which in this part allows us to make our system flexible and able to adjust, increase or decrease to suit the applications we use but even though the work has been divided appropriately Managing the communication channel is also important. because we have With the rise of microservices, congestion in communication channels is a concern.

<div align="center">
  <img src="https://github.com/FordPatcharapol/billboard_detection_system/blob/main/imgs/cloud_computing_c.PNG"/>
</div>
  
  * From the congestion limitation of this communication channel, I have brought edge computing to help reduce bandwidth usage by introducing Microservices. that uses data from the camera to be in the same area as the camera Makes processing unnecessary to send some data to the cloud. This helps reduce congestion in the communication channel. and use the information as necessary In terms of doing edge computing, there are still limitations like in the part where resources are quite limited, causing the need to improve the software or model to be able to support work on edge computing and we can design work as Microservices on edge computing to increase efficiency.

<div align="center">
  <img src="https://github.com/FordPatcharapol/billboard_detection_system/blob/main/imgs/edge_computing_c.PNG"/>
</div>

# Integration with Protocol Buffers / JSON
  To exchange data between services or microservices, a data format that can be accessed and retrieved is essential. In this context, common data formats such as JSON are often employed due to their widespread support across various applications, browser compatibility, and ease of use with AJAX. JSON doesn't require prior knowledge of the data structure to access the data, making it highly convenient for developers.
  
<div align="center">
  <img src="https://github.com/FordPatcharapol/billboard_detection_system/blob/main/imgs/edge_computing_json.PNG"/>
</div>

However, an alternative data format known as Protocol Buffers (Protobuf) can potentially enhance overall system performance. The primary advantage of Protobuf is its compact file size, resulting from data being encoded in a binary format. This compactness enables faster processing speeds. The main drawback of Protobuf, however, is that it complicates development, as it necessitates a predefined data structure to process the data. But this data format is suitable for increasing the speed of data transmission in a distributed system where the speed of data transmission is quite effective.

<div align="center">
  <img src="https://github.com/FordPatcharapol/billboard_detection_system/blob/main/imgs/edge_computing_json_proto.PNG"/>
</div>

Ultimately, the choice of data format depends on the specific requirements of each component within a system, rather than any universally applicable criteria.

# Integration with Distributed System
The previous example is a data center processing example that combines all processing in one place. In this section, we can prevent the server from crashing and may not be able to use. application By solving problems in this section, we can adjust the form of the system structure to be in the form distributed processing It's a way for multiple computers to work together to solve common problems. This way the computer network becomes a single, powerful computer that provides massive resources to handle complex processing and prevent server crashes so that services can continue to be used.

For example, microservices can be modeled as distributed processing so that when one service dies, others can continue to run. Or we can add service to do the same job. to support increasing or decreasing service in processing, resulting in higher flexibility of the system

<div align="center">
  <img src="https://github.com/FordPatcharapol/billboard_detection_system/blob/main/imgs/edge-computing-distributed-system.PNG"/>
</div>

# Technologies Used
 - Data Science: Python, NumPy, pandas, OpenCV, Pytorch
 - label Tools: Roboflow / LabelImg / CVAT
 - Machine Learning: YOLO
 - Cloud Computing: AWS / Google Cloud Platform
 - Edge Computing: NVIDIA Jetson/ Raspberry Pi
 - Data Format: Protobuf / JSON
 - Container: Docker / Kubernetes
 - Resource: Nvdia Cuda

# Deployment
  In terms of deployment, it will create containers that contain programs and models that you want to use in order to easily manage and maintain each service, with Kubernetes that will help manage containers to be able to deploy, manage resources. automatically This can also help keep applications running on containers running smoothly.
  
# Summary
In this example is present about the system design and does not go into detail in the software development part. microservices, resources Or others as appropriate for the service, making the overall system highly flexible. However, the design of various systems depends mainly on the use. This system I designed based on my personal opinion only.

# Reference
- Ahmad I., Bakht H., Mohan U., (2017). Cloud Computing - A Comprehensive Definiton. Journal of Computing and Management Studies Vol. 1.
- 
- https://netway.co.th/kb/blog/cloud-managed-services/cloud-computing-คืออะไร
- https://innovationatwork.ieee.org/real-life-edge-computing-use-cases/
- https://aws.amazon.com/th/what-is/distributed-computing/
- https://www.howtoautomate.in.th/protobuf-101/

