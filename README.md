# Shoulder Implant X-ray Classification using Swin Transformer

## Overview
This repository contains the implementation of a deep learning-based approach for classifying shoulder implant X-ray images using a modified Swin Transformer model. The proposed method enhances image contrast, applies data augmentation, and integrates spatial interaction blocks to improve fine-grained spatial feature learning.

### 1. **Data Preprocessing**
- Applied **CLAHE (Contrast Limited Adaptive Histogram Equalization)** to enhance contrast.
- Normalized pixel values in the range [0, 1] to standardize input features.

### 2. **Data Augmentation**
- Due to the limited dataset size (597 images), augmentation techniques such as rotation, width/height shifts, shear, zoom, and flipping (horizontal & vertical) were applied.
- The dataset expanded to **4179 images**, split as **80% for training/validation and 20% for testing**.

### 3. **Model Architecture: Swin Transformer with Spatial Interaction Blocks**
- **Patch Splitting**: Images were divided into non-overlapping patches.
- **Shifted Window Attention**: Attention mechanisms integrated with shifted windows and relative position biases for efficient feature extraction.
- **Spatial Interaction Blocks**: Assigned importance to different regions, suppressing irrelevant features while maintaining a smooth information flow with residual connections.
- **Pretraining**: Swin Transformer was pretrained on the **ImageNet dataset**, enhancing feature learning and model convergence.

## Dataset
- **Shoulder Implant X-ray Classification Dataset** (Urban et al., 2020)
- **4 Classes**: Cofield (83), Depuy (294), Tornier (71), Zimmer (149)
- **Image Size**: 250x250 pixels
- **Total Images**: 597 (before augmentation)
- **Dataset Link**: [Shoulder Implant X-ray Classification Dataset](https://archive.ics.uci.edu/dataset/517/shoulder+implant+x+ray+manufacturer+classification)

## Implementation Details
- **Framework**: PyTorch
- **Hardware**: NVIDIA RTX 8000 GPU (46 GB VRAM)

### Model Training Parameters
| Parameter       | Value  |
|---------------|--------|
| Batch Size     | 256    |
| Epochs         | 200    |
| Learning Rate  | 0.001  |
| Optimizer      | SGD    |
| Loss Function  | Cross Entropy Loss |
| Activation     | Softmax |

## License
This project is licensed under the MIT License.

