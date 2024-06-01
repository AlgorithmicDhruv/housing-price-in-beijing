# Housing Price Analysis in Beijing

## Overview

This project provides an in-depth analysis of housing prices in Beijing from 2011 to 2017. The dataset, sourced from [Lianjia.com](https://www.lianjia.com), undergoes extensive cleaning and filtering, culminating in the creation of a predictive model using a Random Forest algorithm.

## Data Files

- **new.csv**: Original dataset containing raw housing price data.
- **cleaned.csv**: Dataset post-initial cleaning, including handling missing values and translating Chinese characters.
- **filtered.csv**: Final dataset after feature selection, used for training the predictive model.

## Project Workflow

### Step 1: Data Collection

The raw data, encoded in `GB2312`, was read and loaded into a DataFrame for processing.

### Step 2: Data Cleaning

1. **Encoding Detection**: The file encoding was identified using the `chardet` library.
2. **Column Removal**: Unnecessary columns such as `url`, `id`, and `communityId (Cid)` were removed.
3. **Handling Chinese Characters**: Translated and parsed Chinese characters in columns like `livingRoom`, `drawingRoom`, and `floor`.
4. **Handling Missing Values**:
   - `DOM` (Days on Market): Filled missing values with the median.
   - `buildingType`: Filled missing values with the median.
   - `constructionTime`: Filled missing values with the most frequent value.
5. **Data Type Adjustment**: Ensured all columns had appropriate data types.

### Step 3: Data Filtering and Feature Selection

The cleaned dataset was further refined to focus on the most relevant features:
- Selected features: `totalPrice`, `square`, `livingRoom`, `floor`.

### Step 4: Model Creation

A Random Forest model was developed using the `filtered.csv` dataset:
1. **Feature Selection**: Chose four key features for model input.
2. **Model Training**: Trained a Random Forest model with 10 estimators.
3. **Model Evaluation**: Evaluated the model using metrics such as MSE, RMSE, and R² to ensure optimal performance.

### Step 5: Model Export

The trained Random Forest model was exported using `pickle` for future use.

## Instructions for Use

1. **Clone the Repository**:


    git clone https://github.com/yourusername/housing-price-in-beijing.git
    cd housing-price-in-beijing


2. **Install Dependencies**:

Install the required Python libraries:




    pip install -r requirements.txt

3. **Run the Notebook**:

Open and execute the Jupyter Notebook to view the data processing steps and analysis:




    jupyter notebook Housing_price_in_Beijing.ipynb

## Repository Structure: 

- `Housing_price_in_Beijing.ipynb`: Jupyter Notebook containing all data processing steps.
- `new.csv`: Original raw data file.
- `cleaned.csv`: Cleaned data after initial processing.
- `filtered.csv`: Final data after filtering.
- `README.md`: Project overview and instructions (this file).

## Conclusion:

This project provides a comprehensive analysis of housing prices in Beijing, utilizing data cleaning and filtering techniques to prepare the dataset for further analysis. Follow the instructions above to explore the dataset and the processing steps in detail.