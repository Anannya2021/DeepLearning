# Foundations of Learning {#sec-foundations-of-learning}

Learning is one of the key components of a computer vision system. In these chapters, we cover the foundations of machine learning from a general perspective but explore examples using vision problems.

## Outline

- **Intro To Learning** introduces the basic principles of machine learning.

- **Gradient-Based Learning Algorithm** describes how to learn the parameters that fit a model to data.

- **Problem_Of_Generalization** describes the difference between fitting to training data and generalizing to test data, and the new considerations that arise given this difference.

- **Neural Networks** introduces neural networks, a general family of models common in both biological and artificial vision systems.

- **Backpropagation** describes the backpropagation algorithm for calculating the gradient of a neural network with respect to its parameters.

## Notation

  
- Neural networks consist of a sequence of layers that perform a sequence of transformations $\mathbf{x}_0 \rightarrow \mathbf{x}_1 \rightarrow \ldots \rightarrow \mathbf{y}$. When we consider a single layer in isolation, we will generically refer to its input as ${\mathbf{x}_{\texttt{in}}}$ and its output as ${\mathbf{x}_{\texttt{out}}}$. We will also use the variables $\mathbf{h}$ and $\mathbf{z}$ to represent certain kinds of intermediate representations in neural nets, which will be defined when they are first used.
