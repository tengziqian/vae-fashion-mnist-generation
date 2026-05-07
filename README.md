# Variational Autoencoders for Image Generation on Fashion-MNIST

## Project Overview

This project explores image generation with Variational Autoencoders (VAEs) using the Fashion-MNIST dataset. The main goal is to train a generative model that can learn a compact latent representation of clothing images and generate new samples that resemble the training distribution. Fashion-MNIST is a useful benchmark for this project because it has the same image size and structure as MNIST, but the classes represent real clothing categories such as shirts, sneakers, bags, and coats. This makes the generation task more visually interesting than handwritten digits while still being small enough for efficient experimentation.

The baseline model will be a convolutional VAE trained on grayscale 28 x 28 Fashion-MNIST images. The encoder will map each image to the parameters of a latent Gaussian distribution, and the decoder will reconstruct images from samples drawn using the reparameterization trick. The training objective will combine reconstruction loss with KL divergence so that the model learns both image-level accuracy and a smooth latent space. After establishing the baseline, we plan to evaluate generated samples, inspect reconstructions, and explore how latent dimensionality, network depth, and loss weighting affect image quality.

## Data

We will use the Fashion-MNIST dataset, originally released by Zalando Research.

- Dataset link: https://github.com/zalandoresearch/fashion-mnist
- Number of training images: 60,000
- Number of test images: 10,000
- Image shape: 1 x 28 x 28 grayscale
- Number of classes: 10
- Classes: T-shirt/top, Trouser, Pullover, Dress, Coat, Sandal, Shirt, Sneaker, Bag, Ankle boot

The data can be loaded through `torchvision.datasets.FashionMNIST`, which provides a standard train/test split and automatic download support.

## Goals

- Build a baseline convolutional VAE for Fashion-MNIST image generation.
- Train the model using a reconstruction term and KL divergence regularization.
- Generate new clothing images by sampling from the latent space.
- Compare reconstructed images with generated samples to understand what the VAE learns.
- Study how latent dimension and model capacity affect sample quality.
- Use the baseline as a foundation for Milestone 2 improvements, such as beta-VAE loss weighting, deeper convolutional architectures, or comparison with another generative model.

## Proposed Approach

1. Preprocess Fashion-MNIST images by converting them to tensors and normalizing pixel values.
2. Implement a convolutional encoder that outputs latent mean and log-variance vectors.
3. Use the reparameterization trick to sample latent vectors while keeping training differentiable.
4. Implement a decoder that maps latent vectors back to 28 x 28 grayscale images.
5. Train the VAE with a combined reconstruction and KL divergence objective.
6. Visualize reconstructions, random samples, and latent interpolation results.

## Baseline

The baseline solution will be a standard convolutional VAE. This baseline is appropriate because it directly addresses the core image generation problem while remaining interpretable. The reconstruction results will show whether the model captures basic clothing shape and structure, while generated samples will show whether the learned latent distribution is useful for producing new images. In Milestone 2, we plan to improve on this baseline by tuning the latent space, experimenting with architecture choices, and evaluating sample quality more systematically.

## Expected Deliverables

- Source code for the VAE model and training pipeline
- Generated image grids and reconstruction examples
- Training loss curves
- Presentation slides
- Video presentation
- Final written summary of findings

