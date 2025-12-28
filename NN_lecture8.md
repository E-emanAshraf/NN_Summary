### **1. Generative Adversarial Networks (GANs)**

GANs are unsupervised generative frameworks that use an adversarial process to train two competing models:

* **Generator (G)**: Uses a multi-layer perceptron (MLP) to map noise (z) from a probability distribution into a sample space (G(z)), attempting to create "fake" data that looks real.


* **Discriminator (D)**: An MLP that takes both real samples (x) and fake samples (G(z)) as input and outputs the probability that a sample is real.


* **Training Objective**: The goal is to reach a Nash equilibrium where the generator is so good that the discriminator can no longer distinguish fake data from real data (i.e., its output probability is 0.5).


* **Applications**: Image and text generation, speech enhancement, and image super-resolution.



### **2. Recurrent Neural Networks (RNNs)**

RNNs are designed for **sequential data** (videos, audio, sentences) because they can maintain a "context state" over time.

* **Architecture**: Unlike standard ANNs, RNNs have connections between hidden layer nodes across time steps, allowing them to store information from previous inputs.


* **Why use RNNs?**: They handle variable-length inputs and preserve the importance of sequence order (e.g., "how are you" vs. "how you are").


* **Backpropagation Through Time (BPTT)**: RNNs are trained by unfolding the network over time and accumulating gradients from all time steps.


* **Limitations**: Standard RNNs suffer from **vanishing or exploding gradients**, meaning they struggle to remember information over long sequences.



### **3. LSTM and GRU**

These are specialized RNN variants designed to solve the long-term memory problem:

* **LSTM (Long Short-Term Memory)**: Uses three "gates" (forget, input, and output) to regulate the flow of information, allowing it to connect information across long gaps.


* **GRU (Gated Recurrent Unit)**: A simpler, more computationally efficient version of LSTM that combines the forget and input gates into a single "update gate" and uses a "reset gate".



### **4. Attention Mechanism**

Inspired by biological vision, attention allows a neural network to focus on specific, relevant portions of data rather than processing everything with equal weight.

* **Types**:
* **Hard Attention**: Selects specific locations (often trained with reinforcement learning).


* **Soft Attention**: Assigns continuous weights to different parts of the input.




* **Applications**:
* **Visual Attention**: A "glimpse network" can outperform a standard CNN by focusing high resolution only on relevant parts of an image.


* **Image Captioning**: Selects specific image regions to generate corresponding words in a caption.


* **Machine Translation**: Uses a context vector to focus on specific source words while translating a target word.





### **5. Transformers**

The Transformer architecture moves away from the recurrent structure entirely:

* **Core Idea**: It relies on **Attention** and **Positional Encodings** within a traditional multi-layer network.


* **Function**: It learns word embeddings that are dynamically adjusted based on the word's specific position and surrounding context in a sentence.