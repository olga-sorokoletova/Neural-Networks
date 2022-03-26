# Deep Convolutional Generative Adversarial Networks (DCGAN) used to Generate Anime Style Faces

This is the repository of the project proposed for the course of *Neural Networks*.

This work is implemented using Keras Library and is centered on the idea to **develop the Deep Convolution GAN** that can perform well on [**Anime-Face-Dataset**](https://github.com/bchao1/Anime-Face-Dataset) to generate new anime style images and **explore the latent feature representations**.

The  Jupyter Notebook with the code can be found in the repository files as [code.ipynb](https://github.com/olga-sorokoletova/Neural-Networks/blob/main/scripts/code.ipynb). 

For the implementational details refer the [```report```](https://github.com/olga-sorokoletova/Neural-Networks/tree/main/report.pdf).

## Dataset

Dataset is an unsupervised dataset of the 63632 high-quality anime faces with clean background and RGB colors rescaled to the (64, 64, 3) shape.

### Examples:

<p align="center">
  <img src="/images/dataset.png" width="236" height="231"/>
</p>

## Architecture

The general schematic representation of an architecture of the Baseline model is shown below. And it is a slightly modified basic architecture of the Deep Convolutional Generative Adversarial Network where the generator subnetwork attempts to generate fake samples of images and fool the discriminator subnetwork into believing about fakes to be real samples.

<p align="center">
  <img src="/images/gan_architecture.jpeg" width="774" height="420"/>
</p>

## Experiments

### Example of the Baseline output

The model has not grasped the distribution of the real data completely, but it is doing a decent work over random noises and is able to build some faces of an acceptable quality.

<p align="center">
  <img src="/images/generated/animes_9900_small.png" width="180" height="177"/>
</p>

Following model progresses over iterations (100, 300, 1000, 3000 epochs, correspondingly):

<p align="center">
  <img src="/images/generated/animes_100_small.png" width="180" height="177"/><img src="/images/generated/animes_300_small.png" width="180" height="177"/> <img src="/images/generated/animes_1000_small.png" width="180" height="177"/> <img src="/images/generated/animes_3000_small.png" width="180" height="177"/> 
</p>

### Baseline-A and Baseline-B versions of the Baseline model

The former has been trained over 20000 epochs, whereas the latter one - over 30000 epochs.

<p align="center">
  <img src="/images/generated/a01.png" width="236" height="231"/><img src="/images/generated/b01.png" width="236" height="231"/>
</p>

### Experiments with the Latent Vectors

The experiments performed over latent variable distribution: the variations of Mean and Standard Deviation.

#### Standard Deviation

 <img src="https://render.githubusercontent.com/render/math?math=\A: \mathcal{N}(0, 1)"> | <img src="https://render.githubusercontent.com/render/math?math=\A: \mathcal{N}(0, 0.4)"> |   <img src="https://render.githubusercontent.com/render/math?math=\B: \mathcal{N}(0, 1)"> | <img src="https://render.githubusercontent.com/render/math?math=\B: \mathcal{N}(0, 0.4)"> 
:---------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------:|:---------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------:
 <img src="/images/generated/a01.png" width="236" height="231"/> | <img src="/images/generated/a04.png" width="236" height="231"/>| <img src="/images/generated/b01.png" width="236" height="231"/> | <img src="/images/generated/b04.png" width="236" height="231"/>
 
1. The color distribution changed its intensity;
2. The generated faces still contain asymmetry;
3. The model performs better when the Standard Deviation is lower.
  
  #### Mean
  
   <img src="https://render.githubusercontent.com/render/math?math=\A: \mathcal{N}(-0.3, 0.4)"> | <img src="https://render.githubusercontent.com/render/math?math=\A: \mathcal{N}(0.3, 0.4)"> |   <img src="https://render.githubusercontent.com/render/math?math=\B: \mathcal{N}(-0.3, 0.4)"> | <img src="https://render.githubusercontent.com/render/math?math=\B: \mathcal{N}(0.3, 0.4)"> 
:---------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------:|:---------------------------------------------------------------------------------------:|:--------------------------------------------------------------------------------------------:
 <img src="/images/generated/a_34.png" width="236" height="231"/> | <img src="/images/generated/a34.png" width="236" height="231"/>| <img src="/images/generated/b_34.png" width="236" height="231"/> | <img src="/images/generated/b34.png" width="236" height="231"/>
 
Average faces from different Mean points:

 |−1 |−0.8|−0.6|−0.4|−0.2|  0 | 0.2| 0.4| 0.6| 0.8|
 |-|-|-|-|-|-|-|-|-|-|

<p align="center">
  <img src="/images/generated/a_means.png" width="907" height="96"/>
</p>

<p align="center">
  <img src="/images/generated/b_means.png" width="907" height="96"/>
</p>

1. The greater the point of the vector is, the «warmer» the hair color is;
2. The greater the point of the vector is, the more clear-cut, symmetric and circular shape of eyes is;
3. The greater the point of the vector is, the more clear-cut mouth is drawn;
4. The middle point faces are darker. It means that average faces in the dataset have these style.

## Author
- Olga Sorokoletova - 1937430
