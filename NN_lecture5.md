### **1. Core Components and Hyperparameters**

* **Neural Network Components**: Beyond neurons, essential elements include **Activation functions** (adding non-linearity), **Loss functions** (measuring reproduction accuracy), and **Optimization algorithms** like stochastic gradient descent to minimize loss.


* **Loss Functions**: Used to update weights by comparing predicted and actual values. Common types include:


* **Regression**: Mean Squared Error (MSE), Mean Absolute Error (MAE).


* **Classification**: Binary Cross-Entropy, Hinge Loss, and Multi-Class Cross-Entropy.




* **Hyperparameters**: Settings chosen before training that cannot be learned from the data, such as learning rate, network architecture, and convolution filter size.



### **2. Regularization Strategies**

Regularization aims to reduce **generalization error** (the gap between training and test error) to prevent **overfitting**.

## ✅ **1. Dropout**

> *Randomly ignores (drops) entire neurons during training.*

### **Why?**

To stop neurons from relying too much on each other → reduces overfitting.

### **How it works**

Suppose a layer has 4 neurons:

```
[ N1, N2, N3, N4 ]
```

With **dropout probability 0.5**, during each training step we randomly remove half of them:

```
Step 1: [ N1, --, N3, -- ]
Step 2: [ --, N2, --, N4 ]
Step 3: [ N1, N2, --, -- ]
```

The network learns to work even when some neurons disappear → making it more robust.

---

## 🔧 **2. Weight Decay (L2 Regularization)**

> *Penalizes large weights to prevent overfitting.*

### **Idea**

The loss function becomes:
[
Loss = Loss_{original} + \lambda \sum w_i^2
]

Large weights increase the penalty → network prefers small, stable weights.

### **Example**

Weights before decay:

```
w1 = 2.0, w2 = -1.5, w3 = 0.3
```

With λ = 0.1:

```
Penalty = 0.1 * (2.0² + (-1.5)² + 0.3²)
        = 0.1 * (4 + 2.25 + 0.09)
        = 0.634
```

So the model tries to lower `w1` and `w2` to reduce the penalty.

---

## 📸 **3. Data Augmentation**

> *Expands dataset with modified copies of original data.*

### **Example with one cat image**

Original:
🐱

After augmentation:

```
Flip horizontally  →  (mirror cat)
Add noise          →  grainy image
Rotate +10°        →  tilted cat
Crop               →  zoomed cat face
Color jitter       →  darker or brighter cat
```

This makes the model more invariant to orientation, lighting, and noise → reducing overfitting, especially when dataset is small.

---

## 🔗 **4. DropConnect**

> *Drops (zeros) individual **weights**, not entire neurons.*

### **Difference from Dropout**

| Technique       | What is removed?       |
| --------------- | ---------------------- |
| **Dropout**     | whole **neurons**      |
| **DropConnect** | individual **weights** |

### **Visual Example**

Weights between input and hidden layer:

```
Weights before:
[0.6, -0.8, 1.2, 0.4]

DropConnect mask:
[1, 0, 1, 0]

After DropConnect:
[0.6, 0, 1.2, 0]
```

The neuron still exists, but some of its connections become inactive → forces diverse paths through the network.

---

## 🧱 **5. Parameter Reduction**

> *Reduce model complexity to fight overfitting.*

### **Techniques**

* Fewer layers
* Fewer neurons
* **Bottleneck layers** (compress features)
* Depthwise-separable convolutions (MobileNet)

### **Example**

Original CNN block:

```
Conv 64 → Conv 64 → Conv 64
```

Bottleneck block:

```
Conv 64 → Conv 16 → Conv 64
             ↑ bottleneck
```

This can reduce parameters by **75%+** without hurting accuracy much (used in ResNet, MobileNet).

---

# 📌 Summary Table

| Technique               | What it does                    | Prevents overfitting by                     |
| ----------------------- | ------------------------------- | ------------------------------------------- |
| **Dropout**             | disable random neurons          | forcing redundancy                          |
| **DropConnect**         | disable random weights          | reducing reliance on individual connections |
| **Weight Decay (L2)**   | shrink large weights            | making network simpler                      |
| **Data Augmentation**   | increase data size artificially | improving generalization                    |
| **Parameter Reduction** | reduce number of parameters     | limiting model capacity                     |

### **3. Notable CNN Architectures**

The lecture traces the evolution of object recognition through key historical models:

* **LeNet (1998)**: Applied to handwritten digit recognition (MNIST) using a CONV-POOL-CONV-POOL-FC structure.


* **AlexNet (2012)**: The first CNN-based ImageNet winner; it popularized the use of ReLU, heavy data augmentation, and dropout.


* **ZFNet (2013)**: An improvement on AlexNet with optimized hyperparameters like smaller filter sizes and strides.


* **VGGNet (2014)**: Used very small (3x3) filters in deep stacks (16–19 layers) to achieve the same receptive field as larger filters but with more non-linearity and fewer parameters.


* **GoogLeNet (2014)**: Introduced "Inception modules" with parallel filter operations and 1x1 "bottleneck" convolutions to reduce computational complexity and parameters.


* **ResNet (2015)**: Introduced **residual connections** to solve optimization issues in very deep networks (up to 152 layers), enabling the training of deeper models without performance degradation.