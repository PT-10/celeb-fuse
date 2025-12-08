# celeb-fuse
An attempt at balancing highly imbalanced datasets using diffusion generated images.
Experiments involve:
- Finetuning Dreambooth using cherry picked sub class images focusing on blond/ non blond classification.
- Trial and errors to find the best specific token to generate images that are similar to celebA and avoid mode collapse
- Training with different loss functions for establishing baseline ResNet accuracy
- Finetuning ResNet-18/50 with synthetic data and DANN
