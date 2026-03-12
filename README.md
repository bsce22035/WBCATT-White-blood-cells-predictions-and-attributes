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

**Training Parameters:**

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

## Results

- Models achieve high accuracy on the PBC dataset.

- Testing on Raabin-WBC evaluates cross-dataset generalization.

- Confusion matrices highlight misclassifications per WBC type.

- Attribute-wise analysis provides insight into strengths and weaknesses of each model.

## Notebooks

You can open and run the full code for each model in Google Colab:

- **VGG16:** [Open in Colab](https://colab.research.google.com/drive/1zyKDCcAjwgC5xudZRHDvc_GumOUQaV0U?usp=sharing)  
- **ResNet50:** [Open in Colab](https://colab.research.google.com/drive/1UoHFk_smUQ0HOwFiko6zhyxpopWA6Bx5?usp=sharing)  
- **ViT-B16:** [Open in Colab](https://colab.research.google.com/drive/1RwEjt8Pf9Co9YH0A04LvS74TouIvT49m?usp=sharing)  
- **EfficientNet:** [Open in Colab](https://colab.research.google.com/drive/1wtqzTh_SuErx9AMiF-koRLJzTv2cIncF?usp=sharing)  
- **ConvNeXt:** [Open in Colab](https://colab.research.google.com/drive/1OLtVKfV7H4GupQUGZCHAMaDd3pf2MDvt?usp=sharing)  
- **Testing & Analysis:** [Open in Colab](https://colab.research.google.com/drive/1xShZJwC5tS7pmr7bP8MFiDpKkKxiqxC3?usp=sharing)
