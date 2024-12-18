# Classification of Animal Supergroups

**Group Leader**: Zaid Fada  
**Group Members**: Malek Thabet, Chris Woods
**Course**: DS 4002  
**Date**: 22 November 2024

## Project Overview

This repository contains the code, data, and documentation for our project focused on classifying animal supergroups from the CIFAR-100 dataset. By training a Convolutional Neural Network (CNN), we aim to achieve an accuracy of at least 80% on image classification tasks within animal-related categories. Our results will contribute to understanding the effectiveness of CNNs in identifying animal species based solely on image data and their potential application in wildlife conservation and education.

## Repository Structure

- **README.md**: Provides an overview and instructions for reproducing the results.
- **LICENSE.md**: License for the project (MIT License).
- **requirements.txt**: Python packages needed for the project
- **SCRIPTS/**: Contains the Python scripts for data processing, feature engineering, and model training.
- **DATA/**: Contains the dataset used for training and testing.
- **OUTPUT/**: Stores the results, including figures and tables from the analysis.

```bash
.
├── README.md                # Project overview and instructions along with results at the bottom
├── LICENSE.md               # License information (MIT)
├── requirements.txt         # Python packages needed for the project
├── SCRIPTS/
│   ├── 1-preprocessing.ipynb         # script to combine data over the years
│   └── 2-analysis.ipynb     # Detailed step-by-step analysis performed
├── DATA/
│   └── Data.md              # Steps to download dataset
├── OUTPUT/             # Figures generated during prelim data discovery
```

## Software and Platform

- **Programming Language**: Python
- **Packages Required**:

  - `pandas`
  - `numpy`
  - `scikit-learn`
  - `matplotlib`
  - `tensorflow`
  - `seaborn`

- **Platform**: Windows, macOS, or Linux

## Data

The dataset for this project is the CIFAR-100, a well-known image dataset sourced from the University of Toronto. It consists of 100 classes organized into 20 superclasses, each containing 600 images. For this project, we focus on the animal-related superclasses, such as "aquatic mammals" and "large carnivores." The dataset includes 50,000 training images and 10,000 test images, with labels stored as fine (specific group) and coarse (superclass) categories.

## Instructions for Reproducing Results

1. Clone this repository:

   ```bash
   git clone [repository link]
   cd [repository directory]
   ```

2. Install the required Python packages: Ensure that Python 3.x is installed. Then, install the necessary packages by running:
   ```bash
   pip install -r requirements.txt
   ```
3. Download and prepare the data:

   - Go to `/SCRIPTS/1-preproccesing.ipynb` and run the cells in there to see our preprocessing steps, such as mapping the images to the super group names
   - Follow the comments in the cells and run each cell to see our exploratory-plots, or go to outputs to see them directly

4. Run the analysis:

   - Go to `/SCRIPTS/2-analysis.ipynb`, follow the comments in the cells and run each cell to perform our analysis!

5. Review our results:
   - The model’s accuracy, precision, recall, and other performance metrics will be saved down below in this read me!
   - Visualizations will be saved in the `OUTPUTS/plots/` directory.

# Classification of Animal Supergroup Results

This document provides a summary of the training and validation results of our CNN model built to classify animal species using the CIFAR-100 dataset.

# **Model Training and Testing Summary**

## **Overview**

This document provides a summary of the training and validation results of our CNN model built to classify animal species using the CIFAR-100 dataset.

## **Training Metrics**

| **Epoch** | **Accuracy** | **Loss** | **Validation Accuracy** | **Validation Loss** |
| --------- | ------------ | -------- | ----------------------- | ------------------- |
| 1         | 20.80%       | 2.6052   | 25.22%                  | 1.9971              |
| 2         | 31.45%       | 1.9603   | 40.18%                  | 1.6913              |
| 3         | 35.64%       | 1.7937   | 38.04%                  | 1.7883              |
| 10        | 51.21%       | 1.4005   | 45.11%                  | 1.5742              |
| 20        | 61.67%       | 1.1078   | 51.76%                  | 1.4410              |
| 30        | 68.06%       | 0.9121   | 57.20%                  | 1.3041              |
| 50        | 75.75%       | 0.7098   | 59.24%                  | 1.3046              |
| 70        | 79.21%       | 0.6032   | 61.20%                  | 1.3496              |
| 100       | 83.10%       | 0.4909   | 60.44%                  | 1.4398              |

## **Testing Metrics**

| **Metric**    | **Value** |
| ------------- | --------- |
| Test Accuracy | 61.22%    |
| Test Loss     | 1.4135    |

## **Observations**

- Training accuracy improved steadily, achieving 83.10% by the 100th epoch.
- Validation accuracy fluctuated, peaking at around 62%.
- Testing results showed a **test accuracy** of **61.22%** and a **test loss** of **1.4135**, aligning with the validation performance.

## **Key Takeaways**

- The model demonstrated strong improvements in training accuracy, indicating effective learning.
- Validation performance suggests potential overfitting after certain epochs, highlighting areas for hyperparameter tuning.
- Further optimization of the architecture or dataset augmentation may enhance generalization and improve test results.

![Model Accuracy Plot](./Outputs/training-validation-accuracy.jpg "Training and Validation Accuracy")

# Results Analysis

## Classification Performance by Supergroup

This section provides a breakdown of the model's performance in classifying animal supergroups. The metrics include precision, recall, F1-score, and support for each supergroup.

| **Supergroup**                 | **Precision** | **Recall** | **F1-Score** | **Support** |
|--------------------------------|---------------|------------|--------------|-------------|
| Aquatic Mammals                | 0.57          | 0.64       | 0.60         | 484         |
| Fish                           | 0.70          | 0.67       | 0.69         | 508         |
| Insects                        | 0.78          | 0.72       | 0.75         | 516         |
| Large Carnivores               | 0.69          | 0.56       | 0.62         | 486         |
| Large Omnivores and Herbivores | 0.67          | 0.66       | 0.67         | 471         |
| Medium Mammals                 | 0.66          | 0.66       | 0.66         | 509         |
| Non-Insect Invertebrates       | 0.66          | 0.62       | 0.64         | 500         |
| Reptiles                       | 0.43          | 0.69       | 0.53         | 510         |
| Small Mammals                  | 0.73          | 0.49       | 0.59         | 516         |

### **Overall Metrics**
- **Accuracy**: 0.63
- **Macro Average**:
  - Precision: 0.66
  - Recall: 0.63
  - F1-Score: 0.64
- **Weighted Average**:
  - Precision: 0.66
  - Recall: 0.63
  - F1-Score: 0.64

## Key Insights

### Strengths
1. **High Performance on Distinct Classes**: 
   - The model performed best on **Insects** with an F1-score of **0.75**, meaning it excel at distinguishing what I would assume are the most unique classes.
   - **Fish** also showed strong classification with an F1-score of **0.69**.

2. **Balanced Performances in Medium Mammals and Large Omnivores and Herbivores**:
   - Classes like **Medium Mammals** and **Large Omnivores and Herbivores** showed consistent precision, recall, and F1-scores, indicating balanced performance.

### Weaknesses
1. **Low Performance on Reptiles**:
   - **Reptiles** exhibited the lowest F1-score of **0.53**.
   
2. **Misclassification in Small Mammals**:
   - A lower recall of **0.49** in **Small Mammals** indicates challenges in correctly identifying all samples of this class, possible mis labelling other mammal groups for this one.

## Conclusion
While the model achieved an overall accuracy of **63%**, it fell short of the target hypothesis of **80%** accuracy. The class-wise evaluation highlights the model's strengths in identifying distinct classes but reveals challenges with visually similar categories. 

# References

[1] CIFAR-100 Dataset: https://www.cs.toronto.edu/~kriz/cifar.html

[2] "Convolutional Neural Networks (CNNs)": https://www.analyticsvidhya.com/

[3] "Developing CNN Models for Image Classification": https://machinelearningmastery.com/
