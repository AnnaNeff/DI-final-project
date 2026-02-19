# DI-final-project: Olist E-commerce Delivery Analysis

## Overview

This project analyzes the Olist e-commerce dataset to understand factors influencing delivery delays and customer review scores. The analysis includes data cleaning, exploratory data analysis (EDA), SQL-based data manipulation, and machine learning models to predict delivery delays.

## Objectives

- Identify correlations between delivery times, approval processes, and customer satisfaction (review scores).
- Analyze the impact of seller delays, carrier performance, and geographical distances on delivery outcomes.
- Build predictive models to forecast delivery delays using features like order details, seller risk, and customer information.

## Dataset

The project uses the Brazilian E-commerce Public Dataset by Olist, which includes:

- `olist_customers_dataset.csv`: Customer information
- `olist_geolocation_dataset.csv`: Geographical data
- `olist_order_items_dataset.csv`: Order item details
- `olist_order_payments_dataset.csv`: Payment information
- `olist_order_reviews_dataset.csv`: Customer reviews
- `olist_orders_dataset.csv`: Order timestamps and status
- `olist_products_dataset.csv`: Product details
- `olist_sellers_dataset.csv`: Seller information
- `product_category_name_translation.csv`: Category translations

All data files are located in the `Data/` directory.

## Key Findings

### Delivery Delays and Review Scores
- Longer delivery times correlate with lower review scores.
- Delivery delays significantly impact review scores.
- Carrier delays are more common than seller delays.

### Geographical and Seller Factors
- Distance between seller and customer has minimal impact on delays, except for very long distances.
- Risky sellers (those with high delay rates) can be identified and flagged.

### Other Insights
- No strong correlations found between features like order price, weight, or payment type and delays.
- Carrier information is recommended for better predictions.

## Methodology

1. **Data Export and Cleaning**: Load CSV files, check for duplicates/nulls, fill missing values.
2. **SQL Integration**: Transfer data to SQLite for complex queries.
3. **Exploratory Analysis**:
   - Time-based correlations (approval vs. delivery).
   - Delay analysis by stages (seller to carrier, carrier to customer).
   - Distance calculations using Haversine formula.
   - Seller risk assessment.
4. **Feature Engineering**: Extract features like delivery days, risk flags, order dimensions.
5. **Machine Learning**:
   - Models: Random Forest and Logistic Regression.
   - Target: Binary late delivery flag (>1 day late).
   - Oversampling to handle class imbalance.
   - Evaluation: Accuracy, F1-score, ROC-AUC.

## Files

- `project.ipynb`: Main Jupyter notebook with all code, analysis, and visualizations.
- `Olist analysis.twb`: Tableau workbook for interactive dashboards.
- `Data/`: Directory containing all CSV datasets.
- `README.md`: This file.

## Requirements

- Python 3.x
- Libraries: pandas, numpy, matplotlib, seaborn, scikit-learn, sqlalchemy, sqlite3
- Jupyter Notebook
- Tableau (for viewing the .twb file)

## Installation and Setup

1. Clone the repository:
   ```
   git clone <repository-url>
   cd DI-final-project
   ```

2. Install dependencies:
   ```
   pip install pandas numpy matplotlib seaborn scikit-learn sqlalchemy
   ```

3. Run the notebook:
   ```
   jupyter notebook project.ipynb
   ```

4. For Tableau analysis, open `Olist analysis.twb` in Tableau Desktop.

## Usage

- Execute cells in `project.ipynb` sequentially to reproduce the analysis.
- The notebook includes data loading, cleaning, SQL queries, visualizations, and model training.
- Outputs include plots, correlation matrices, and model performance metrics.

## Results

- **Random Forest**: Achieves good ROC-AUC for predicting delays.
- **Logistic Regression**: Recommended for interpretability and actionable insights (e.g., flagging risky orders).
- Confusion matrices and classification reports are provided for both models.

## Future Improvements

- Incorporate carrier data for better delay predictions.
- Experiment with additional ML models (e.g., XGBoost).
- Deploy models for real-time predictions.

## Authors

- Anna Nefedova

## License

This project is for educational purposes. Dataset sourced from Kaggle (Brazilian E-commerce Public Dataset by Olist).
