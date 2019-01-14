# Awesome Generative Models
- For collecting useful algorithms of generative ML
- Contains wiki and link of example codes(repositories)

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
- VAE+ RNN
- serial data
- [DRAW: A Recurrent Neural Network For Image Generation](https://arxiv.org/abs/1502.04623)

#### [Generative Query Network](Wiki/GQN.md)
- evidences(Images + positions) + (target position) -> (image)
- [Neural scene representation and rendering](https://deepmind.com/blog/neural-scene-representation-and-rendering/)
- [Learning models for visual 3D localization with implicit mapping](https://arxiv.org/pdf/1807.03149.pdf)
- [Sample codes](https://github.com/ogroth/tf-gqn)

### [Generative Adversarial Networks](Wiki/GAN.md)
- Generator vs discriminator : Generator generates "fake results" to deceive discriminator. Discriminator finds "fake data" from whole data.
- [Generative Adversarial Nets](https://arxiv.org/abs/1406.2661)

#### [DC-GAN](Wiki/DCGAN.md)
  - Uses convolution(transposed convolution) layers
  - [Unsupervised Representation Learning with Deep Convolutional Generative Adversarial Networks](https://arxiv.org/abs/1511.06434)
  - [Sample codes](https://github.com/carpedm20/DCGAN-tensorflow)

#### [PG-GAN](Wiki/PGGAN.md)
  - Generates images from low resolution to high resolution
  - Learns to generate bigger data from smaller ones
  - [Progressive Growing of GANs for Improved Quality, Stability, and Variation](https://arxiv.org/abs/1710.10196)
  - [Sample codes](https://github.com/zhangqianhui/progressive_growing_of_gans_tensorflow)

#### [Conditional-GAN](Wiki/ConditionalGAN.md)

- Z layer : Noise + Y(condition)
- GAN : random generate
- Conditional-GAN : pseudo-random generate (random generate with specific characteristics)
- [Conditional Generative Adversarial Nets](https://arxiv.org/abs/1411.1784)

#### multi-modal GANs
  - [Cycle-GAN](Wiki/CycleGAN.md)
    - [Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks](https://arxiv.org/abs/1703.10593)
    - [Sample codes](https://github.com/xhujoy/CycleGAN-tensorflow)
  - [DISCO-GAN](Wiki/DiscoGAN.md)
    - [Learning to Discover Cross-Domain Relations with Generative Adversarial Networks](https://arxiv.org/abs/1703.05192)
    - [Sample codes(pytorch)](https://github.com/SKTBrain/DiscoGAN)
  - [STAR-GAN](Wiki/StarGAN.md)
    - [StarGAN: Unified Generative Adversarial Networks for Multi-Domain Image-to-Image Translation](https://arxiv.org/abs/1807.03039)
    - [Sample codes](https://github.com/taki0112/StarGAN-Tensorflow)

#### [Adversarial Variational Bayes](Wiki/Adversarial_Variational_Bayes.md)

- [Adversarial Variational Bayes: Unifying Variational Autoencoders and Generative Adversarial Networks](https://arxiv.org/abs/1701.04722)
- VAE <-- GAN
- [Sample codes](https://github.com/LMescheder/AdversarialVariationalBayes)

#### [BEGAN](Wiki/BEGAN.md)

- [BEGAN: Boundary Equilibrium Generative Adversarial Networks](https://arxiv.org/abs/1703.10717)
- GAN <-- AE
- [Sample codes](https://github.com/carpedm20/BEGAN-tensorflow)

### [Generative FLOW (GLOW)](Wiki/GLOW.md)

- [Glow: Generative Flow with Invertible 1x1 Convolutions](https://arxiv.org/abs/1711.09020)