GAN on Fashion-MNIST (TensorFlow / Keras)

This repository contains a simple implementation of a Generative Adversarial Network (GAN) trained on the Fashion-MNIST dataset using TensorFlow/Keras.

The model learns to generate 28×28 grayscale images of clothing items by training a generator and discriminator in an adversarial setup.

Dataset

The model is trained on the Fashion-MNIST dataset:

60,000 training images

10,000 test images

28×28 grayscale images

10 clothing categories

Images are normalized to the range [-1, 1] to match the generator’s tanh output activation.

**Model Architecture**

Generator

Input: 100-dimensional noise vector (latent_dim = 100)

Fully connected layer → reshape to 7×7×256

Conv2DTranspose blocks with:

Batch Normalization

LeakyReLU activation

Output layer:

Conv2DTranspose (1 channel)

tanh activation

The generator progressively upsamples noise into 28×28 grayscale images.


Discriminator

Input: 28×28×1 image

Conv2D blocks with:

LeakyReLU activation

Batch Normalization

Flatten + Dense(1)

Output activation: sigmoid

The discriminator performs binary classification (real vs fake).