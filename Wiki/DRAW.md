# DRAW

## Summary
- Generates images like "drawing"
- uses deep RNN layers(LSTM) with convolutional VAE
  - basic form and loss are almost same with VAE
  - Loss function(objective function) : `(negetive log-likely) + (KL-divergence)`
- works better with attention algorithms

## Model Description
<img src="./Resources/DRAW_model.PNG" width="70%">

- Left : Conventional VAE
- Right : DRAW Model
- Z -> Z<sub>1:t</sub> : Latent variables are serialized (such like time)
- VAE : Uses gaussian distribution to predict z. Because of "reparameterization trick"
  - reparameterization trick : `N(μ,σ) == (N(0,1)+μ)*σ`
- Variables
  - x'<sub>t</sub> : error image
  - r<sub>t</sub> : computed **read** variable
  - h<sub>t</sub><sup>enc</sup> : encoder's hidden layer
  - h<sub>t</sub><sup>dec</sup> : decoder's hidden layer
  - z<sub>t</sub> : samples from `Q`
  - c<sub>t</sub> : computed **write** variable
- Computations
  - x'<sub>t</sub> = x - sigmoid(c<sub>t-1</sub>)
  - r<sub>t</sub> = read(x,x'<sub>t</sub>,h<sub>t-1</sub><sup>dec</sup>) -> (NOTICE : error in paper)
  - h<sub>t</sub><sup>enc</sup> = RNN<sup>enc</sup>(h<sub>t-1</sub><sup>enc</sup>, concat[r<sub>t</sub>,h<sub>t-1</sub><sup>dec</sup>])
  - z<sub>t</sub> ~ Q(Z<sub>t</sub>|h<sub>t</sub><sup>enc</sup>)
  - h<sub>t</sub><sup>dec</sup> = RNN<sup>dec</sup>(h<sub>t-1</sub><sup>dec</sup>,z<sub>t</sub>)
  - c<sub>t</sub> = c<sub>t-1</sub> + write(h<sub>t</sub><sup>dec</sup>)

- Loss function
  - almost same with VAE
  - reconstruction loss : L<sup>x</sup> = - logD(x|c<sub>T</sub>)
  - latent loss(KL divergence) : L<sup>z</sup> = Sum(KL(Q(Z<sub>t</sub>|h<sub>t</sub><sup>enc</sup>||P(Z<sub>t</sub>)))) -> sum of KL divergences of z in each time
  - total loss : (reconstruction loss) + (latent loss)

- Read/Write Functions
  - without attention models
    - read(x,x'<sub>t</sub>,h<sub>t-1</sub><sup>dec</sup>) : concat[x,x'<sub>t</sub>]
    - write(h<sub>t</sub><sup>dec</sup>)=W(h<sub>t</sub><sup>dec</sup>)
  - with selective attention model
    - use gaussian filters
    - multiplication with filters in read/write functions