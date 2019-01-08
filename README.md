# Item Chest
- For collecting useful algorithms of generative ML
- Contains wiki (and some codes ... maybe?)

# Simple Overview

## Generative Models (especially ML)
- Variational Autoencoder(VAE)
- Generative Adversarial Network(GAN)
- Generative Flow
- etc.

### [Variational Autoencoder](Wiki/VAE.md)
- [Stochastic Backpropagation and Approximate Inference in Deep Generative Models](https://arxiv.org/abs/1312.6114)
- [Auto-Encoding Variational Bayes](https://arxiv.org/abs/1312.6114)
- Independent gaussians : VAE's latent vectors are means and stddevs of independent gaussian distributions
- Random sampling : in decoding, VAE generates samples from gaussian distributions

#### [DRAW](Wiki/DRAW.md)
- encoder/decoder model + RNN
- serial data
- [DRAW: A Recurrent Neural Network For Image Generation](https://arxiv.org/abs/1502.04623)

#### [Generative Query Network](Wiki/GQN.md)
- VAE + RNN
- [Neural scene representation and rendering](https://deepmind.com/blog/neural-scene-representation-and-rendering/)
- [Learning models for visual 3D localization with implicit mapping](https://arxiv.org/pdf/1807.03149.pdf)

### [Generative Adversarial Networks](Wiki/GAN.md)
- Generator vs discriminator : Generator generates "fake results" to deceive discriminator. Discriminator finds "fake data" from whole data.
- [Generative Adversarial Nets](https://arxiv.org/abs/1406.2661)

#### [DC-GAN](Wiki/DCGAN.md)
  - Uses convolution(transposed convolution) layers
  - [Unsupervised Representation Learning with Deep Convolutional Generative Adversarial Networks](https://arxiv.org/abs/1511.06434)

#### [PG-GAN](Wiki/PGGAN.md)
  - Generates images from low resolution to high resolution
  - Learns to generate bigger data from smaller ones
  - [Progressive Growing of GANs for Improved Quality, Stability, and Variation](https://arxiv.org/abs/1710.10196)

#### multi-modal GANs
  - [Cycle-GAN](Wiki/CycleGAN.md)
    - [Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks](https://arxiv.org/abs/1703.10593)
  - [DISCO-GAN](Wiki/DiscoGAN.md)
    - [Learning to Discover Cross-Domain Relations with Generative Adversarial Networks](https://arxiv.org/abs/1703.05192)
  - [STAR-GAN](Wiki/StarGAN.md)
    - [StarGAN: Unified Generative Adversarial Networks for Multi-Domain Image-to-Image Translation](https://arxiv.org/abs/1711.09020)

### [Generative FLOW (GLOW)](Wiki/GLOW.md)
- [Glow: Generative Flow with Invertible 1x1 Convolutions](https://arxiv.org/abs/1807.03039)