# Item Chest
- For collecting useful algorithms of generative ML
- Contains wiki (and some codes ... maybe?)

# Simple Overview

## Generative Models (especially ML)
- Variational Autoencoder(VAE)
- Generative Adversarial Network(GAN)
- Generative Flow
- etc.

### Variational Autoencoder
- [Stochastic Backpropagation and Approximate Inference in Deep Generative Models](https://arxiv.org/abs/1312.6114)
- [Auto-Encoding Variational Bayes](https://arxiv.org/abs/1312.6114)
- Independent gaussians : VAE's latent vectors are means and stddevs of independent gaussian distributions
- Random sampling : in decoding, VAE generates samples from gaussian distributions

#### DRAW
- encoder/decoder model + RNN
- serial data
- [DRAW: A Recurrent Neural Network For Image Generation](https://arxiv.org/abs/1502.04623)

#### GQN
- VAE + RNN
- [Neural scene representation and rendering](https://deepmind.com/blog/neural-scene-representation-and-rendering/)
- [Learning models for visual 3D localization with implicit mapping](https://arxiv.org/pdf/1807.03149.pdf)

### Generative Adversarial Networks
- Generator vs discriminator : Generator generates "fake results" to deceive discriminator. Discriminator finds "fake data" from whole data.
- [Generative Adversarial Nets](https://arxiv.org/abs/1406.2661)

#### DC-GAN
  - Uses convolution(transposed convolution) layers
  - [Unsupervised Representation Learning with Deep Convolutional Generative Adversarial Networks](https://arxiv.org/abs/1511.06434)

#### PG-GAN
  - Generates images from low resolution to high resolution
  - Learns to generate bigger data from smaller ones
  - [Progressive Growing of GANs for Improved Quality, Stability, and Variation](https://arxiv.org/abs/1710.10196)

#### multi-modal GANs
  - Cycle-GAN
    - [Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks](https://arxiv.org/abs/1703.10593)
  - DISCO-GAN
    - [Learning to Discover Cross-Domain Relations with Generative Adversarial Networks](https://arxiv.org/abs/1703.05192)
  - STAR-GAN
    - [StarGAN: Unified Generative Adversarial Networks for Multi-Domain Image-to-Image Translation](https://arxiv.org/abs/1711.09020)

### Generative FLOW (GLOW)
- [Glow: Generative Flow with Invertible 1x1 Convolutions](https://arxiv.org/abs/1807.03039)