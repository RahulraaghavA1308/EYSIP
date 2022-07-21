# Generative adversarial Networks

We simultaneously train two models:

A generative model G
that captures the data distribution, and a discriminative model D that estimates
the probability that a sample came from the training data rather than G.

The training procedure for G is to maximize the probability of D making a mistake.

- G should be able to produce data that tricks D such that D estimates that the data came from training data
- In the case where G and D are defined
by multilayer perceptrons, the entire system can be trained with backpropagation.

The special case when the generative model generates samples
by passing random noise through a multilayer perceptron, and the discriminative model is also a
multilayer perceptron. We refer to this special case as adversarial nets. In this case, we can train
both models using only the highly successful backpropagation and dropout algorithms [17] and
sample from the generative model using only forward propagation. No approximate inference or
Markov chains are necessary.
