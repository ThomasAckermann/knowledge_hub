Date: 17-04-2025
Tags: #MachineLearning #DeepLearning 
## Definition
GAN consists of two parts
- Generator
- Discriminator
both are connected in such a way that the generated data becomes more and more realistic. The goal is to create data which the discriminator can no longer differentiate from real data. The networks train each other. Both networks have to be equally good so that this process works. Both discriminator and generator try to improve each other.
The discriminator has a binary cross entropy loss and the generator also a binary cross entropy on the combined model. The generator input is noise which is sampled from the latent space. The latent space is a visualization of data where similar data points are close together. 

---
## References
[[Overview Types of Neural Networks]]
