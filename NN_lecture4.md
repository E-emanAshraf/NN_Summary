**Convolutional Neural Networks (CNNs)**.

### **Core Concepts of Deep Learning**

* **Definition**: Deep learning consists of neural network algorithms that automatically learn important features and representations directly from data (images, text, sound) rather than relying on manual feature extraction.


* **Architecture**: Deep models are formed by multiple layers; a Multi-Layer Perceptron (MLP) with more than two hidden layers is considered a deep model.


* **Rule of Thumb**: Deeper models generally perform better than shallow ones but require more data to avoid **overfitting**.



### **Convolutional Neural Networks (CNNs)**

CNNs are specifically designed for tasks like object recognition, detection, and image captioning. Key components include:

* **Convolution Layer**: The most important operation where filters (kernels) slide over input data to create "feature maps," identifying patterns like edges or shapes.


* **Stride**: The number of pixels the window moves at a time.


* **Padding**: Adding zeros around the input to maintain spatial size or avoid circular convolution effects.




* **ReLU (Rectified Linear Unit)**: A non-linear activation function () used after convolution layers to enable the network to learn complex patterns and speed up training.


* **Pooling Layer**: Reduces the spatial dimensions (width and height) of feature maps to decrease the number of parameters and computation while controlling overfitting. **Max pooling** is the most common type.


* **Fully Connected (FC) Layer**: Traditionally placed at the end of the network, it uses high-level features from previous layers to classify the input into specific categories.



### **Practical Training Techniques**

* **Training Process**: Involves initializing weights, forward propagation to find output probabilities, calculating total error, and using **backpropagation** to update weights.


* **Mini-batches**: Instead of using the entire dataset for one gradient step, training is done using small portions (e.g., ~100 examples). This leads to faster training, smoother convergence, and better GPU utilization.


* **Batch Normalization (BN)**: A technique applied between layers to normalize activations.


* **Benefits**: It reduces **internal covariate shift**, speeds up training, allows for higher learning rates, and reduces the need for other regularization methods like dropout.


* **Placement**: It is typically used after linear layers (FC or Conv) and before non-linear layers (ReLU).