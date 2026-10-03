## MobileNetV3-Large for Fork and Spoon Image Classification

## Overview
This project implements image classification using **MobileNetV3-Large** to distinguish between two object classes: fork and spoon.
The experiment compares three training approaches:
1. Feature Extraction
2. Partial Fine-Tuning
3. Training from Scratch
The project was developed as part of the Computer Vision and Deep Learning coursework.

## Objectives
* Implement image classification using MobileNetV3-Large.
* Compare transfer learning and training from scratch.
* Evaluate model performance using validation accuracy and confusion matrices.
* Analyze the effect of pretrained weights on classification performance.

## Dataset
The dataset contains two classes:
* Fork
* Spoon
The dataset was divided into training and validation sets using an 80:20 split.
| Dataset    | Number of Images |
| ---------- | ---------------: |
| Training   |              279 |
| Validation |               71 |
| Total      |              350 |

### Dataset Distribution
| Class | Training | Validation |
| ----- | -------: | ---------: |
| Fork  |      159 |         40 |
| Spoon |      120 |         31 |

The dataset archive is provided in the `dataset/` directory.

## Model and Experimental Setup
* Architecture: MobileNetV3-Large
* Image classification: 2 classes
* Training epochs: 10
* Batch size: 32
* Optimizer: Adam
* Learning rate scheduler: CosineAnnealingLR
* Random seed: 42

### Experiment Configurations
**1. Feature Extraction**
The pretrained MobileNetV3-Large feature extractor is frozen, while the classification layer is trained for the target classes.

**2. Partial Fine-Tuning**
Selected layers of the pretrained model are unfrozen and trained to adapt the model to the fork and spoon dataset.

**3. Training from Scratch**
The model is trained without pretrained weights to observe performance when learning from the dataset alone.

## Experimental Results
| Training Method       | Validation Accuracy |
| --------------------- | ------------------: |
| Feature Extraction    |              95.77% |
| Partial Fine-Tuning   |             100.00% |
| Training from Scratch |              56.34% |

### Result Analysis
The experimental results show different performance across the three training approaches :
* **Feature Extraction** achieved 95.77% validation accuracy, correctly classifying 68 out of 71 images. This indicates that the pretrained feature representations were effective for distinguishing between fork and spoon images, even without updating the feature extractor.
* **Partial Fine-Tuning** achieved 100% validation accuracy, correctly classifying all 71 validation images. This result indicates that adapting selected pretrained layers helped the model learn features relevant to the target classification task.
* **Training from Scratch** achieved 56.34% validation accuracy. The model predicted all validation images as fork, correctly classifying the 40 fork images but failing to recognize the 31 spoon images. This suggests that the model did not learn sufficient discriminative features for both classes under the current training configuration.

## Conclusion
Based on the experiments, MobileNetV3-Large was evaluated using Feature Extraction, Partial Fine-Tuning, and Training from Scratch for fork and spoon image classification. Feature Extraction achieved 95.77% validation accuracy, Partial Fine-Tuning achieved 100%, and Training from Scratch achieved 56.34%. The results demonstrate that pretrained weights provided useful feature representations for this classification task. Partial Fine-Tuning also showed that adapting selected layers could improve the model's performance on the validation set.
Nevertheless, the 100% validation accuracy does not guarantee perfect performance on new images. Further evaluation using a larger and independent test dataset is needed to assess the model's generalization capability.

## Requirements
Install the required Python libraries using:

```bash
pip install -r requirements.txt
```

## How to Run
1. Clone this repository:
```bash
git clone https://github.com/feriananb-del/MobileNetV3-Fork-and-Spoon-Classification.git
```
2. Navigate to the project directory:
```bash
cd MobileNetV3-Fork-and-Spoon-Classification
```
3. Install dependencies:
```bash
pip install -r requirements.txt
```
4. Extract the dataset archive into the appropriate directory.
5. Open the notebook:
```text
notebooks/MobileNetV3_Transfer_Learning.ipynb
```
6. Run the notebook cells sequentially.

## Author
**Feri Ana (4222401007)**
Computer Vision and Deep Learning Coursework
