# WBC Classification Using Deep Learning Models
## Project Overview

This project implements and evaluates five state-of-the-art deep learning models for white blood cell (WBC) classification:

- VGG16

- ResNet50

- ViT-B16 (Vision Transformer)

- EfficientNet

- ConvNeXt

The models are trained on the PBC dataset and tested on the Raabin-WBC dataset. The workflow includes saving best epoch checkpoints, testing on a separate dataset, and analyzing both cell-wise and attribute-wise predictions.

## Datasets
### PBC Dataset (Training)

- Used for training and validation.

- Contains labeled images of different WBC types.

- Split into training, validation, and test sets.

### Raabin-WBC Dataset (Testing)

- Used for evaluating model generalization.

- Contains WBC images from a different source.

- Models are tested using the best checkpoint saved during training.

## Model Workflow
1. Data Preprocessing

  Resize all images to the input size required by each model.

  Normalize pixel values (ImageNet normalization for pretrained models).

2. Model Training

**Models:** VGG16, ResNet50, ViT-B16, EfficientNet, ConvNeXt

**Optimizer:** Adam or SGD

**Loss Function:** Cross-Entropy Loss

**Training Parameters:""

- **Epochs:** 20

- **Batch size:** 32

- **Checkpointing:** Save the model after every 5 epoch.

3. Evaluation on Raabin-WBC

- Load the saved best checkpoint.

- Perform inference on the Raabin-WBC dataset.

- **Compute metrics:**

- Accuracy per cell type

- Attribute-wise performance (shape, size, granularity)

- Generate confusion matrices and visualizations for analysis.

4. Analysis

- Cell-wise analysis: Performance per WBC type (e.g., Neutrophil, Lymphocyte, Monocyte, Eosinophil, Basophil)

- Attribute-wise analysis: Performance based on features like:

+ Shape

+ Size

+ Granularity

- Compare all five models to identify strengths and weaknesses.



Pretrained weights from ImageNet are used where applicable.

Checkpoints ensure reproducibility and enable evaluation on other datasets.

Analysis scripts generate numeric metrics and visualization plots.
