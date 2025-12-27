### 1. Multilayer Perceptron (MLP) Architecture

* **Structure**: An MLP is a feed-forward network consisting of an input layer, one or more hidden layers, and an output layer.


* **Connections**: Nodes in adjacent layers are fully connected, but there are no connections between nodes within the same layer.


* **Activation**: Neurons use non-linear, differentiable activation functions—most commonly sigmoid functions—to model the behavior of biological neurons.



### 2. Backpropagation Algorithm

The lecture summarizes the standard method for training MLPs:

* **Forward Step**: Inputs are passed through the network to compute outputs for each layer ( for hidden,  for output).


* **Backward Step**: Error signals () are calculated starting from the output layer and propagated back to the hidden layers.


* **Weight Update**: Weights are adjusted based on these error signals and a learning rate ().



### 3. Activation Functions

Differentiability is the primary requirement for activation functions in backpropagation. Common types include:

* **Logistic Sigmoid**: Defined as $y_j = \frac{1}{1 + \exp(-a \cdot net_j)}$.


* **Hyperbolic Tangent**: Defined as $y_j = a \tanh(b \cdot net_j)$.



### 4. Solving the XOR Problem

* The XOR problem cannot be solved by a single-layer perceptron because its patterns are not linearly separable.


* It is solved by adding a **hidden layer** with at least two neurons. The lecture provides a step-by-step example of the feedforward and backpropagation process for XOR.


### 5. Advantages and limitations of the Backpropagation Using Gradient Descent
### Advantages
* Relatively simple implementation
* Standard method after 80s and generally works well to solve linear & non linear problem
### Limitations
* The convergence obtained from backpropagation learning is very slow.
* If train too long, you run the risk of overfitting!!!!
* The convergence in backpropagation learning is not guaranteed.
* Can get stuck in local minima resulting in sub-optimal solutions

### 6. Training Challenges and Improvements

* **Local Minima**: Gradient descent can get stuck in sub-optimal solutions. Strategies to avoid this include using different initial weights, changing the number of hidden nodes, or using momentum.


* **Momentum**: Adding a momentum term () to the weight update rule helps speed up convergence, avoid oscillations, and provides some immunity to local minima.


* **Overtraining (Overfitting)**: This occurs when a network performs well on training data but poorly on test data. **Cross-validation** and **early stopping** are used to find the point of best generalization.


* **Adaptive Learning Rates**: Methods for adjusting the learning rate () include assigning smaller values to later layers or adjusting based on the sign of the error gradient.



### 7. Preprocessing

* **Normalization**: Data should be scaled (e.g., to [0,1] or [-1,1]) so that different input types have the same impact and the cost function optimizes faster.


* **Curse of Dimensionality**: To handle high-dimensional data with limited samples, component reduction methods like PCA are recommended.

---
### 1. Uniform vs. Layer-Specific Rates

* **Uniform Rate:** The basic approach where all neurons share the same learning rate.
* **Gradient-Based Distribution:** Since gradients often diminish as they back-propagate, the **last layers** typically have larger local gradients than the front layers. To balance this, a **smaller** should be assigned to the last layers, while a **larger** is used for the front layers to compensate for smaller gradients.

### 2. Input-Based Adaptation (Weight Specific)

* **Connectivity Volume:** Neurons with many inputs (high fan-in) should have a **smaller learning rate** to prevent massive weight swings, whereas neurons with few inputs can afford a larger rate.
* **LeCun’s Rule (1993):** Specifically, the learning rate for a neuron should be **inversely proportional to the square root of its synaptic connections**. This helps normalize the total weight change reaching a neuron.

### 3. Gradient-Sign Adaptation (Directional)

This method adjusts the learning rate dynamically based on the history of the error gradient:

* **Shallow Slopes:** If the sign of the gradient remains the same over iterations, the network is likely on a "flat" part of the error surface. The learning rate is **increased** to speed up progress.
* **Steep Slopes/Valleys:** If the signs of the gradient fluctuate (change from positive to negative), the network is likely on a steep slope or near a minimum. The learning rate is **decreased** to prevent overshooting or oscillation.

### Summary Table: Adaptive Learning Rate Strategies

| Method | Strategy | Objective |
| --- | --- | --- |
| **Layer Position** | Smaller  at the back, larger at the front. | Balancing gradient magnitude differences. |
| **Input Density** | Smaller  for neurons with many inputs. | Preventing excessive weight updates. |
| **Gradient Sign** | Increase  if sign is same; decrease if sign changes. | Accelerating on flat planes and slowing down on steep curves. |