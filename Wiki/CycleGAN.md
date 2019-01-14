# Cycle-GAN

## Summary

- Cross-modal GAN : image to image, image to map, etc.
- Cross-modal : generates X -> Y and vice versa. Changes modality.
- Cycle-consistency : if X -> Y -> X', X~=X'
  - Differences with reconstruction : Loss
    - Reconstruction loss : L2 loss or Cross-Entropy loss
    - Cycle-consistency loss : **L1 loss**
    - It makes differences with [DiscoGAN](DiscoGAN.md)
- Not uses Noises to generate

## Model Description

<img src="./Resources/CycleGAN_model.PNG" width="70%">

- (a) : basic structure of Cycle-GAN
- Variables
  - X, Y : dataset (with different modality)
  - G : generator of (X->Y)
  - F : generator of (Y->X)
  - D<sub>X</sub>, D<sub>Y</sub> : Discriminator of each dataset
  - X',Y',x',y' : predicted(generated) data
- Losses
  - Adversarial loss
    - L<sub>GAN</sub>(G,D<sub>Y</sub>,X,Y) -> (-1) * (E[log(D<sub>Y</sub>(y))]+E[log(1-D<sub>Y</sub>(G(x))]) ...(discriminator)
    - L<sub>GAN</sub>(G,D<sub>Y</sub>,X,Y) -> (-1) * (E[log(D<sub>y</sub>(G(x)))]) ...(generator)
    - L<sub>GAN</sub>(F,D<sub>X</sub>,X,Y) -> (-1) * (E[log(D<sub>X</sub>(x))]+E[log(1-D<sub>X</sub>(F(y))]) ...(discriminator)
    - L<sub>GAN</sub>(F,D<sub>X</sub>,X,Y) -> (-1) * (E[log(D<sub>X</sub>(F(y))]) ...(generator)
    - In paper, they used **least square loss(L2 loss)** instead of upper losses
  - Cycle consistency loss
    - L<sub>cyc</sub>(G,F) = E[||F(G(x))-x||<sub>1</sub>] + E[||F(G(y))-y||<sub>1</sub>]
  - L<sub>total</sub> = L<sub>adv</sub> + λ * L<sub>cyc</sub>