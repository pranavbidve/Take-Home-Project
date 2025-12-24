# Census Data Analysis - Classification & Segmentation

This project analyzes US Census Bureau data (1994-1995) to build classification and segmentation models for a retail business client.

## Project Overview

**Two Main Objectives:**
1. **Classification**: Predict income levels (<$50K vs >$50K) using demographic and employment variables
2. **Segmentation**: Create customer segments for targeted marketing strategies

## Data Files

- `census-bureau.data` - Main dataset (comma-delimited, 40 variables + weight + label)
- `census-bureau.columns` - Column names for the dataset
- `census_processed.csv` - Preprocessed data (generated during execution)

## Requirements

### Python Version
- Python 3.8 or higher

### Required Libraries
```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost shap
```

Or install all at once:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost shap
```

## How to Run

### Option 1: Run Everything in Jupyter Notebook (Recommended)

1. **Start Jupyter Notebook**
   ```bash
   jupyter notebook
   ```

2. **Open and run the notebooks in order:**
   - First: `Classification.ipynb` - Run all cells (Cell → Run All)
   - Second: `Segmentation.ipynb` - Run all cells (Cell → Run All)

### Option 2: Run in VS Code

1. Open the project folder in VS Code
2. Install the Jupyter extension if you haven't already
3. Open `Classification.ipynb` and click "Run All"
4. Open `Segmentation.ipynb` and click "Run All"



## What Each Notebook Does

### Classification.ipynb
- Loads and explores census data
- Preprocesses features (handles missing values, creates feature engineering)
- Trains two models: Logistic Regression and XGBoost
- Evaluates models with ROC-AUC, Precision, Recall, F1-Score
- Performs SHAP analysis for feature importance
- **Output**: Classification model with ~93% ROC-AUC

### Segmentation.ipynb
- Uses preprocessed data from classification
- Performs K-Means clustering (optimal K=3)
- Creates three customer segments:
  - **Prime Banking Customers** (50% of market)
  - **Future Customers** (30% of market)
  - **Fixed Income Retirees** (20% of market)
- Generates visualizations and marketing recommendations
- **Output**: Customer segments with budget allocation strategy

## Expected Outputs

### Generated Files
- `census_processed.csv` - Preprocessed dataset


### Console Output
- Model performance metrics
- Cluster statistics
- Marketing budget recommendations



## Project Structure

```
TakeHomeProject/
├── README.md                      
├── Classification.ipynb           
├── Segmentation.ipynb           
├── census-bureau.data            
├── census-bureau.columns        
├── census_processed.csv          # Preprocessed data 
├── Client Report.pdf             # final report
└── ML-TakehomeProject.pdf        
```

## Key Results

### Classification Model
- **Best Model**: XGBoost with 0.85 threshold
- **ROC-AUC**: 0.929
- **Precision**: 52.2% (optimized for marketing use case)
- **Top Features**: Age, weeks worked, education, tax filing status

### Segmentation Model
- **3 Distinct Segments** identified using K-Means
- **Recommended Budget Allocation**:
  - Prime Banking Customers: 60%
  - Fixed Income Retirees: 25%
  - Future Customers: 15%

## Notes

- The notebooks are designed to run sequentially (Classification first, then Segmentation)
- Segmentation notebook uses the processed data from Classification
- All visualizations are automatically saved as PNG files
- Cross-validation is included in Classification for model validation
- Sample weights are used throughout to handle class imbalance



---

**Author**: Pranav Bidve  
**Date**: December 2024  


