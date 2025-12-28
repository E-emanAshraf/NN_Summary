# Lecture 2

* **McCulloch-Pitts Neuron Model:** This early model uses a threshold logic unit (TLU) where the output is determined by a threshold function: if the weighted sum of inputs plus a bias is $\ge 0$, the output is 1; otherwise, it is 0.


* **Decision Surfaces and Linear Separability:**
* A **decision surface** (or hyperplane) is where the node output exactly equals the bias ().


* **Linearly Separable Problems:** Problems like the **AND** and **OR** logic functions can be separated by a linear surface.


* **Non-linearly Separable Problems:** The **XOR** problem cannot be solved by a single-layer network because no single line can separate the classes.

* **In general**, an n-dimensional input space can be divided by an (n-1)-dimensional plane or hyperplane.



### Rosenblatt's Perceptron

The Perceptron is the simplest neural network form, designed for pattern classification.

* **Architecture:** It uses a hard-limit transfer function (signum) to return +1 or -1.


* **Convergence Theorem:** If a problem is linearly separable, the Perceptron is guaranteed to converge in a finite number of steps.



### ADALINE and the LMS Algorithm

Introduced by Widrow and Hoff, ADALINE uses the **Least Mean Square (LMS)** algorithm, also known as the Delta Rule.

* **Architecture:** Unlike the Perceptron's hard-limit function, ADALINE typically uses a linear transfer function for learning.


* **Optimization:** It utilizes **Gradient Descent** to minimize the mean square error (MSE).


* **Training Variants:**
* **Batch Gradient Descent:** Scans the entire dataset before updating weights.


* **Stochastic Gradient Descent (SGD):** Updates weights after each individual training sample, often reaching a solution faster.





### Comparison: Perceptron vs. ADALINE

| Feature | Perceptron | ADALINE (LMS) |
| --- | --- | --- |
| **Separability** | Only solves linearly separable problems. | Also limited to linear problems, but finds the "best" solution for non-separable ones.|
| **Convergence** | Stops only when the error is zero.| Always converges; stops when the error reaches a specific bound.|
| **Robustness** | Can be sensitive to noise because patterns often lie close to the decision boundary.| More powerful as it minimizes the overall error rather than just finding a valid boundary.|
| **Training** | Uses the Perceptron Learning Rule.| Uses the Widrow-Hoff/LMS algorithm.|