### 1. Biological Inspiration and the Human Brain

* **Replicating Human Learning**: Researchers aim to simulate the human brain’s ability to learn from experience.


* **Structure**: The brain consists of approximately 100 billion neurons.One neuron is connectedly with approximately 10,000 other neurons.
Each neuron receives signals through **dendrites**, processes them in the **cell body**, and sends outputs through an **axon** via **synapses** (between the axon and each dendrite).


* **Comparison**: While digital computers excel at rapid calculation, the human brain is superior in vision, pattern recognition, and perception, utilizing parallel computing and understanding based on experience.

* **The human nervous system** is a **three-stage system**: brain (neural net), receptors, and effectors.  
 The **brain** : (neural net) receives information, perceives it, and makes decisions.  
**Receptors** : convert stimuli (internal or external) into electrical impulses for the brain.  
**Effectors** : convert brain-generated electrical impulses into visible responses.  
**Simplified flow** : Stimulus → Receptors → Neural net → Effectors → Response.

* **Knowledge** is acquired from environment through learning process.
* **Interneuron connection strengths**, known as synaptic weights, are used to store
the acquired knowledge

### 2. The Artificial Neuron Model

* **Core Elements**: An artificial neuron consists of:
* **Synaptic Weights**: Characterize the strength of connection links.


* **Adder (Linear Combiner)**: Sums the weighted input signals.


* **Activation Function**: Limits (squashes) the output to a specific range (e.g., 0 to 1 or -1 to 1).

* **Why do we need activation functions?**
▪ Non-linearity is achieved through the use of activation functions, which limit or squash
the range of values a neuron can express,The squashing function serves to limit the domain (0 to 1 or -1 to 2).



* **Bias ()**: An extra input (often +1) that shifts the activation potential, helping the network converge to a solution.

### 3. Neural Network Architectures

* **Feedforward Networks**: Data moves in one direction from input to output with no loops.


* **Single-layer**: Only an input layer and an output layer (where computation occurs).


* **Multilayer**: Includes one or more "hidden" layers between input and output.




* **Recurrent Networks**: Contain at least one feedback loop, allowing them to remember information and model sequential data like stock prices. Examples include Hopfield networks(No hidden layer , No self-feedback loops.) and Boltzmann machines.



### 4. Learning Methods and Tasks

* **Supervised Learning (Learning with a Teacher)**: The network is trained with labeled data (inputs and desired outputs). The goal is to minimize the error between actual and desired output.


* **Tasks**: Regression (predicting continuous values) and Classification (predicting discrete labels).




* **Unsupervised Learning (Learning without a Teacher)**: No desired response is provided; the network discovers internal structures or patterns in the data.


* **Tasks**: Clustering (grouping similar data) and Dimensionality Reduction (simplifying data features).




* **Learning Rules**: Common rules include Hebbian, Error Correction (Gradient Descent), Competitive, and Stochastic learning.



### 5. Common Applications
* **Regression**: The output of this problem will be continuous variable.

* **Classification**: in this case we are trying to get something called **Decision Boundary** instead of curve.

* **Pattern Recognition**: Including face detection (non-linear.), speech recognition, and character recognition.


* **Prediction**: Estimating future values in financial markets.
* **Clustering**: image segmentation

* **Optimization**: Finding optimal solution. for complex problems like the "Traveling Salesman".


* **Automatic Driving**: Using video images and distance data to determine steering directions.


### 6. Activation Functions Range

### **1. Identity Function (Linear Function)**

* **Range:** (-∞, ∞)


### **2. Threshold (Step) Function**

* **Range:** {0, 1}


### **3. Symmetric Threshold Function with Bi-polar Output**

* **Range:** {-1, 1}


### **4. Sigmoid Function (Logistic)**

* **Range:** (0, 1)


### **5. Hyperbolic Tangent Sigmoid Function with Bi-polar Output (tanh)**

* **Range:** (-1, 1)


### **6. Ramp Function or Rectified Linear Unit (ReLU)**

* **Range:** [0, ∞)


### **7. Piecewise-Linear Function**

* **Range:** (0, 1)


### **8. Softmax Function**

* **Range:** (0, 1) for each output, **sum = 1**
---

### 1. Identity (Linear) Function

* **Definition:** The output is exactly equal to the input ().
* **Use Case:** Often used in the output layer of regression models where a continuous numerical value is needed.

### 2. Threshold (Step) Function

* **Definition:** Based on the **McCulloch-Pitts** model (1943). It outputs a `1` if the input is $\ge 0$ , and `0` if the input is $\lt 0$.
* **Property:** Known as "all-or-none." It is a discrete (non-continuous) function.

### 3. Symmetric Threshold (Signum) Function

* **Definition:** Similar to the step function but provides a **bi-polar output**.
* **Range**: Outputs 1 if $v \ge 0$ and -1 if $v < 0$.

### 4. Sigmoid (Logistic) Function

* **Definition:** An S-shaped graph defined by the formula $\phi(v) = \frac{1}{1 + \exp(-av)}$.
* **Characteristics:**
* It is **continuously differentiable**, which is essential for training via back-propagation.
* The parameter 'a' controls the slope. As 'a' approaches infinity, it mimics the Step function.



### 5. Hyperbolic Tangent (Tanh) Function

* **Definition:** A sigmoid-style function that provides a bi-polar output.
* **Rule**: The function given is:$\phi(v) = \frac{1-\exp(-av)}{1 + \exp(-av)}$


### 6. Rectified Linear Unit (ReLU)

* **Definition:** Outputs `0` for any negative input and the input value itself () for any non-negative input.
* **Significance:** It is the most widely used activation function in deep learning today because it helps networks train faster.

### 7. Piecewise-Linear Function

* **Definition:** A function composed of straight-line sections.
* **Behavior:** It acts linearly within a specific range (e.g., between -1/2 and +1/2) but "saturates" to 0 or 1 outside that range.

### 8. Softmax Function

* **Definition:** A "normalized exponential" function.
* **Purpose:** It takes a vector of numbers and converts them into a **probability distribution** (where all outputs sum to 1).
* **Use Case:** Almost exclusively used in the output layer of **multiclass classification** models to determine the most likely category.
