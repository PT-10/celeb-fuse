# celeb-fuse
### Domain Adaptation for Hair Color Classification
An attempt at balancing highly imbalanced datasets using diffusion generated images.
Experiments involve:
- Finetuning Dreambooth using cherry picked sub class images focusing on blond/ non blond classification.
- Trial and errors to find the best specific token to generate images that are similar to celebA and avoid mode collapse
- Training with different loss functions for establishing baseline ResNet accuracy
- Finetuning ResNet-18/50 with synthetic data and DANN


## Overview

This project aims to adapt pre-trained ResNet-18/50 to a new domain (hair color images) with a specific class imbalance problem.

## Models Trained

* Base Model: Actual Data Full
* Model 1: Balanced Data
* Model 2: Synthetic Data (2782 images per subgroup)
* Model 3: Synthetic Data Full (with multiple sub-models for different hair colors)
* Model 4: Focal Loss + Class-Balanced Loss
* Model 5: Modified Focal Loss
* Model 6: Class-Balanced Loss
* Model 7: CB + Focal Loss

## Results

* Overall performance drop from 95% to 89% after switching from real to synthetic training data.
* Synthetic data distribution is quite different from real, mainly in male blond images.
* Domain adaptation reduced subgroup bias, but overall accuracy dropped.

## Domain Adaptation

* A basic DANN (Domain Adversarial Neural Network) is implemented using the GradientReversal and GPT models.
* The model is trained on the synthetic data with a small validation set.

## Notes

* The model overfits on old females and one particular blond man.
* Weighted random sampling and normal sampling are tried, but not implemented.
* Domain drift visualization is done, but not fully understood.

## References

* DreamBooth: https://huggingface.co/blog/dreambooth
* DANN: https://github.com/tadeephuy/GradientReversal/
