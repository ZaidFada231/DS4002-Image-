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
│   ├── 1-data.ipynb         # script to combine data over the years
│   ├── 2-exploratory.ipynb  # Prelim data discobvery
│   ├── 3-analysis.ipynb     # Detailed step-by-step analysis performed
│   └── 4-stats.ipynb        # Detailed step-by-step takeaways and stats performed
├── DATA/
│   └── Data.md              # Steps to download dataset
├── OUTPUT/
│   └── plots/              # Figures generated during prelim data discovery
```

## Software and Platform

- **Programming Language**: Python
- **Packages Required**:

  - `pandas`
  - `numpy`
  - `scikit-learn`
  - `matplotlib`
  - `tensorflow`
  - `keras`
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

   - Go to the `1-data.ipynb` and run the cell to create the combined-df that we use across this github
   - The dataset will be in the `DATA/` folder

4. Run the exploratory plots:

   - Go to `/SCRIPTS/2-exploratory.ipynb`, follow the comments in the cells and run each cell to see our exploratory-plots, or go to outputs to see them directly!

5. Run the analysis:

   - Go to `/SCRIPTS/3-analysis.ipynb`, follow the comments in the cells and run each cell to perform our analysis!

6. Run the stats:

   - Go to `/SCRIPTS/5-stats.ipynb`, follow the comments in the cells and run each cell to see where we got our takeaways from!

7. Review the results:
   - The model’s accuracy, precision, recall, and other performance metrics will be saved in the [results.md](OUTPUTS/results.md) file
   - Visualizations will be saved in the `OUTPUTS/plots/` directory.

# Tornado Analysis Results

This document presents the findings of various statistical analyses conducted on tornado data, focusing on trends over time, differences in tornado severity, and changes in injury-causing tornadoes. The analyses compare the first 5 years of data to the last 5 years, using z-tests and chi-square tests to assess significant differences.

## Proportion of Severe Tornadoes (F3 and Above)

| Period  | Total Tornadoes | Violent Tornado Count |
| ------- | --------------- | --------------------- |
| First 5 | 6609            | 262                   |
| Last 5  | 7436            | 972                   |

**Two-sided z-test results**:

- **Z-score**: 19.0299
- **P-value**: 0.0000

**Conclusion**: The proportion of tornadoes that are F3 or higher is significantly greater in the last 5 years compared to the first 5 years. The low p-value indicates that the difference is statistically significant.

## Proportion of Injury-Causing Tornadoes

| Period  | Total Tornadoes | Injury-causing Tornadoes |
| ------- | --------------- | ------------------------ |
| First 5 | 6609            | 609                      |
| Last 5  | 7436            | 402                      |

**Two-sided z-test results**:

- **Z-score**: -8.7166
- **P-value**: 0.0000

**Conclusion**: The proportion of tornadoes that caused injuries is significantly higher in the first 5 years compared to the last 5 years. The p-value of 0.0000 confirms that this difference is statistically significant.

## Tornado Counts by F-Scale

| F_SCALE | First_5_Count | Last_5_Count |
| ------- | ------------- | ------------ |
| F0      | 4094          | 15909        |
| F1      | 1657          | 8389         |
| F2      | 596           | 2547         |
| F3      | 213           | 782          |
| F4      | 44            | 171          |
| F5      | 5             | 19           |

**Chi-square Test**:

- **Chi-square statistic**: 71.616
- **Degrees of freedom**: 5
- **P-value**: 4.7215e-14

**Conclusion**: The differences in the distribution of tornado counts by F-Scale between the first and last 5 years are statistically significant, indicating a shift in the frequency of different tornado intensities over time.

## Trends in Tornado Frequency

| YEAR | First_5_Count | YEAR | Last_5_Count |
| ---- | ------------- | ---- | ------------ |
| 1998 | 1529          | 2019 | 1734         |
| 1999 | 1520          | 2020 | 1251         |
| 2000 | 1169          | 2021 | 1545         |
| 2001 | 1351          | 2022 | 1383         |
| 2002 | 1040          | 2023 | 1523         |

**Two-sided z-test for Mean Frequency**:

- **Z-score**: -1.3117
- **P-value**: 0.2260

**Conclusion**: The mean tornado frequency between the first 5 years and the last 5 years is not significantly different, as indicated by the p-value greater than 0.05.

## Summary

The analyses reveal significant changes in the nature of tornado occurrences over time. While the overall frequency of tornadoes has not shown a statistically significant difference, the proportion of severe (F3 and above) and injury-causing tornadoes has decreased significantly over the years. Additionally, there has been a significant change in the distribution of tornado intensities, as evidenced by the chi-square test results.

  # References
  
[1] National Centers for Environmental Information, “Storm Events Database CSV Files.” [Online]. Available: https://www.ncei.noaa.gov/pub/data/swdi/stormevents/csvfiles/. [Accessed: Oct. 31, 2024].

[2] Yennhi95zz, “A Guide to Time Series Models in Machine Learning: Usage, Pros, and Cons,” Medium, Jul. 28, 2019. [Online]. Available: https://medium.com/@yennhi95zz/a-guide-to-time-series-models-in-machine-learning-usage-pros-and-cons-ac590a75e8b3. [Accessed: Oct. 31, 2024].

[3] S. Berdiales, *Forecasting Models: ARIMA*, bookdown.org, 2020. [Online]. Available: https://bookdown.org/sergioberdiales/tfm-kschool_gijon_air_pollution/forecasting-models-arima.html. [Accessed: Oct. 31, 2024].

