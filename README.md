# Deep Learning for Image Classification and Object Detection

## Overview

The project focuses on experimental settings and results for image classification and object detection tasks using deep learning techniques.

## Contents

1. **Report File**: [Assignment-2-Report-KiranShankerDas-24580348.pdf](https://github.com/kirandas-dev/ImageClassification-Object-Detection/blob/master/Assignment-2-Report-KiranShankerDas-24580348.pdf)
2. **Scripts**: Contains scripts for data preprocessing, model training, and evaluation.
3. **Data**: Sample datasets used for the experiments (if applicable).
4. **Results**: Outputs from the experiments, including performance metrics and visualizations.

## Experimental Settings

### Image Classification

- **Baseline Data Augmentation**:
  - Rotation range: 40
  - Width shift range: 0.2
  - Height shift range: 0.2
  - Shear range: 0.2
  - Zoom range: 0.2
  - Horizontal flip: True
  - Fill mode: 'nearest'
- **Baseline Regularizers**:
  - Kernel regularizer: l2(1e-5)
  - Dropout rate: 0.2 (in the ResBlock)
  - Classifier Block: Dropout(0.5) (in the Dense layer)
- **Custom Settings**:
  - Data Augmentation: Similar to baseline
  - Regularizers:
    - Kernel regularizer: l2(1e-4)
    - Dropout rate: 0.2 (in the ResBlock)
    - Classifier Block: Dropout(0.5) (in the Dense layer)
- **Learning Rate**:
  - Initial: 1e-4
  - After 50 epochs: lr *= 0.1

### Object Detection

- **Models**:
  - Faster R-CNN:
    - Batch size: 2 (trained on PyTorch 3.8 GPU ml.g4dn.xlarge)
    - Mean Average Precision (mAP): 50.27%
    - Average Recall (AR): 53.89%
  - YOLOv5:
    - Batch size: 16
    - Image size: 416x416 pixels
    - Precision and Recall for various classes (e.g., No-Anomaly, Shadowing, Cell-Multi, Cell, Unclassified)

## Experimental Results

### Image Classification

#### Baseline/Standard Architecture

- Test Loss: 1.8152
- Test Accuracy: 0.4076
- Validation Loss: 1.9527
- Validation Accuracy: 0.3679
- Training Loss: 1.7063
- Training Accuracy: 0.4465

#### Customized Architecture

- Test Loss: 0.2268
- Test Accuracy: 0.9682
- Validation Loss: 0.2424
- Validation Accuracy: 0.9497
- Training Loss: 0.0025
- Training Accuracy: 0.9986

### Object Detection

#### Faster R-CNN

- Mean Average Precision (mAP): 50.27%
- Average Recall (AR): 53.89%

#### YOLOv5

- Precision and Recall for various classes (e.g., No-Anomaly, Shadowing, Cell-Multi, Cell, Unclassified)

## Discussion

- **Custom ResNet**: Achieved high validation accuracy (~0.94) with controlled validation loss. Initial large gap between training and validation accuracy reduced with fine-tuning.
- **Faster R-CNN**: Moderate performance with mean AR indicating moderate object detection across different thresholds.
- **YOLOv5**: High precision and recall for No-Anomaly and Shadowing classes, with lower performance for Cell-Multi and Cell classes.

## Conclusion

The experiments demonstrate the efficacy of deep learning, particularly CNNs, in image classification and object detection. Simple architectures provide ease of training and interpretability, while complex architectures like ResNet-50 and YOLOv5 enhance performance, capturing nuanced patterns and leading to higher accuracy and better generalization.

## How to Use

1. **Clone the repository**: `git clone [repository URL]`
2. **Navigate to the directory**: `cd [repository directory]`
3. **Run the scripts**: Follow the instructions in the script files to preprocess data, train models, and evaluate results.
4. **Refer to the report**: For detailed explanations and analysis of the experiments.
