# Gradient-Based Learning Algorithms 

## Introduction

Once you have specified a learning problem (loss function, hypothesis space, parameterization), the next step is to find the parameters that minimize the loss. This is an optimization problem, and the most common optimization algorithm we will use is **gradient descent**. Gradient descent is like a skier making their way down a snowy mountain, where the shape of the mountain is the loss function.

There are many varieties of gradient descent, and we will call this whole family **gradient-based learning algorithms**. All share the same basic idea: at some operating point, calculate the direction of steepest descent, then use this direction to find a new operating point with lower loss.

:::{.column-margin}
We use the term **operating point** to refer to a particular point (setting of the parameters) where we are currently evaluating the loss.

## Technical Setting

In this chapter, we consider the task of minimizing a cost function $J: \cdot \rightarrow \mathbb{R}$, which is a function that maps some arbitrary input to a scalar cost.

In learning problems, the domain of $J$ is the training data and the parameters $\theta$. We will often consider the training data to be fixed and only denote the objective as a function of the parameters, $J(\theta)$. Our goal is to solve:
$$\theta^* = \arg\min_{\theta} J(\theta)$$

Pretty much all optimizers work by some iterative process, where they update the parameters to be better and better. Different optimizers differ in how the parameter update function works. The update function gets to view some information about the loss landscape, then uses that information to update the parameters.

**Gradient-based optimization**, is also called **first-order optimization**, where the update function takes as input the gradient of the cost with respect to the parameters at the current operating point, $\nabla_{\theta}J(\theta)$. This reveals hugely useful information about the loss that directly tells us how to minimize it: just move in the direction of steepest descent, that is, the gradient direction.

Higher-order optimization methods observe higher-order derivatives of the loss, such as the Hessian $H$, which tells you how the landscape is locally curving. The Hessian is costly to compute, but many methods use approximations to the Hessian, or other properties related to loss curvature, and these are growing in popularity.

## Basic Gradient Descent

The simplest version of gradient descent just takes a step in the gradient direction of length proportional to the gradient magnitude. 
This algorithm has two hyperparameters, the **learning rate** $\eta$, which controls the step size (learning rate times gradient magnitude), and the number of steps $K$. If the learning rate is sufficiently small and the initial parameter vector $\theta^0$ is random, then this algorithm will almost surely converge to a local minimum of $J$ as $K \rightarrow \infty$~\cite{lee2016gradient}. However, to descend more quickly, it can be useful to set the learning rate to a higher value. 

## Learning Rate Schedules

A generally useful strategy is to start with a high value for $\eta$ and then decay it until convergence according to a **learning rate schedule**. Researchers have come up with innumerable schedules, and they generally work by calling some function $\texttt{lr}(\eta^0,k)$ to get the learning rate on each iteration of descent:
$$\eta^{k} = \texttt{lr}(\eta^0,k)$$
Generally, we want an update rule where $\eta^{k+1} < \eta^k$, so that we take smaller steps as we approach the minimizer.
