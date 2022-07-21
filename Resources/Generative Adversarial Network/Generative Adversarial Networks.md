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

## ****The Generator Model****

The generator model takes a fixed-length random vector as input and generates a sample in the domain.

The vector is drawn from randomly from a Gaussian distribution, and the vector is used to seed the generative process. After training, points in this multidimensional vector space will correspond to points in the problem domain, forming a compressed representation of the data distribution.

This vector space is referred to as a latent space, or a vector space comprised of [latent variables](https://en.wikipedia.org/wiki/Latent_variable). Latent variables, or hidden variables, are those variables that are important for a domain but are not directly observable.

In the case of GANs, the generator model applies meaning to points in a chosen latent space, such that new points drawn from the latent space can be provided to the generator model as input and used to generate new and different output examples.

After training, the generator model is kept and used to generate new samples

