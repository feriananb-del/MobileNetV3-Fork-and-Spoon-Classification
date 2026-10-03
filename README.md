\# Fork and Spoon Image Classification Using MobileNetV3-Large



\## Project Overview



This project implements an image classification system to distinguish between two classes of kitchen utensils: fork and spoon.



The experiment uses the MobileNetV3-Large architecture to compare three training strategies:



1\. Feature Extraction

2\. Partial Fine-Tuning

3\. Training from Scratch



The objective is to evaluate the effect of pretrained weights on image classification performance using a relatively small dataset.



\## Dataset



The dataset consists of two classes:



\* Fork

\* Spoon



The dataset is divided into:



\* Training set: 80%

\* Validation set: 20%



Image preprocessing includes resizing, normalization, and data augmentation for training images.



\## Model Architecture



MobileNetV3-Large is used as the backbone architecture.



Three experimental configurations are implemented:



| Method                | Description                                           |

| --------------------- | ----------------------------------------------------- |

| Feature Extraction    | Freeze the backbone and train the classifier          |

| Partial Fine-Tuning   | Unfreeze the final feature layer and classifier       |

| Training from Scratch | Train all model parameters from random initialization |



\## Experimental Configuration



\* Architecture: MobileNetV3-Large

\* Input image size: 224 × 224

\* Number of classes: 2

\* Batch size: 32

\* Epochs: 10

\* Optimizer: Adam

\* Learning rate scheduler: CosineAnnealingLR

\* Random seed: 42



\## Experimental Results



The experiment evaluates model performance using:



\* Training and validation accuracy

\* Training and validation loss

\* Classification report

\* Confusion matrix



Detailed results and visualizations are available in the `results` directory and Jupyter Notebook.



\## Repository Structure



```text

MobileNetV3-Fork-Spoon-Classification/

├── notebooks/

│   └── MobileNetV3\_Transfer\_Learning.ipynb

├── results/

├── models/

├── dataset/

├── README.md

├── requirements.txt

└── .gitignore

```



\## Installation



Clone this repository:



```bash

git clone <YOUR\_REPOSITORY\_URL>

```



Install dependencies:



```bash

pip install -r requirements.txt

```



\## Running the Experiment



Open the notebook:



`notebooks/MobileNetV3\_Transfer\_Learning.ipynb`



The experiment can be executed using Google Colab or a compatible Jupyter environment.



Ensure that the dataset is available and its directory structure matches the notebook configuration.



\## Tools and Technologies



\* Python

\* PyTorch

\* Torchvision

\* NumPy

\* Matplotlib

\* Scikit-learn

\* Google Colab

\* Git and GitHub



\## Author



feriananb-del



Computer Vision and Deep Learning Coursework



