### **1. Object Detection**

Object detection is the task of assigning both a **label** and a **bounding box** to every object within an image. The lecture discusses two primary approaches:

* **Detection as Classification**:
* This involves testing many positions and scales.


* **R-CNN**: This model extracts approximately 2,000 "region proposals" from an image and uses a CNN to classify each. However, it is slow and difficult to optimize for real-time use.




* **Detection as Regression (YOLO)**:
* **YOLO (You Only Look Once)**: Treats detection as a single regression problem, predicting bounding boxes and class probabilities directly from full images in one evaluation.


* **Speed**: It is extremely fast, capable of processing 45 frames per second.


* **Procedure**: The image is divided into an  grid. Each cell predicts  bounding boxes, confidence scores, and class probabilities.


* **Architecture**: It uses 24 convolutional layers and 2 fully connected layers, often based on a modified GoogLeNet.


* **Inference**: Employs **Non-Maximum Suppression (NMS)** to remove redundant overlapping boxes based on **Intersection over Union (IoU)** scores.





### **2. Semantic Segmentation**

* **Definition**: The process of linking **each pixel** in an image to a specific class label (e.g., person, car, road). It is essentially image classification at the pixel level.


* **Applications**: Crucial for scene understanding in autonomous driving, robot vision, and medical imaging.


* **Architectures**: Modern models use CNNs as their main structure, often utilizing pre-trained ImageNet networks as building blocks. A key architecture mentioned is the **Fully Convolutional Network (FCN)**.



### **3. Datasets**

The lecture highlights several standard datasets used for these tasks:

* **COCO**: Over 200k images with 80 categories for detection, segmentation, and captioning.


* **Pascal VOC**: 20k images with 20 object classes.


* **Open Images**: A massive collection of 9M annotated images.