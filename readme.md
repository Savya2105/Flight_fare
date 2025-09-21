# Flight Fare Prediction

A comprehensive machine learning project for predicting airline ticket prices using various flight and booking parameters. The project analyzes over 452,000 flight records and implements multiple ML algorithms to achieve accurate fare predictions.

## Project Overview

This project analyzes flight booking data to predict ticket fares based on various factors including airline, route, departure/arrival times, booking timing, and flight characteristics. The analysis includes extensive exploratory data analysis (EDA) and implements three different machine learning models for comparison.

## Dataset Information

The dataset contains **452,088 flight records** with the following features:

### Key Features
- **Date_of_journey**: Date of the flight
- **Journey_day**: Day of the week for the journey
- **Airline**: Flight carrier (Air India, AirAsia, AkasaAir, AllianceAir, GO FIRST, Indigo, SpiceJet)
- **Flight_code**: Unique flight identifier
- **Class**: Travel class (Economy, Business, etc.)
- **Source**: Departure city
- **Departure**: Departure time slot
- **Total_stops**: Number of stops (non-stop, 1-stop, 2+-stop)
- **Arrival**: Arrival time slot
- **Destination**: Arrival city
- **Duration_in_hours**: Flight duration in decimal hours
- **Days_left**: Days between booking and departure
- **Fare**: Target variable - ticket price in INR

### Dataset Statistics
- **Average Fare**: ₹22,840
- **Price Range**: ₹1,307 - ₹143,019
- **Average Duration**: 12.35 hours
- **Booking Window**: 1-50 days in advance

## Exploratory Data Analysis

The project includes comprehensive EDA with multiple visualizations:

### Key Insights
1. **Day of Week Analysis**: Fare variations across different days, with Wednesday showing highest average fares (₹23,144)
2. **Airline Comparison**: Price distribution analysis across different carriers
3. **Route Analysis**: Source-destination pair frequency and average fare analysis
4. **Timing Impact**: Departure and arrival time effects on pricing
5. **Booking Timing**: Relationship between days left and fare prices
6. **Duration vs Price**: Correlation analysis between flight duration and cost

### Statistical Analysis
- **Chi-square tests** for categorical variable associations
- **Pearson correlation** for numerical variables
- All major features showed significant correlation with fare prices

## Data Preprocessing

### Feature Engineering
- **Date Processing**: Converted journey dates to datetime format
- **Day Extraction**: Created day_of_week feature from journey dates
- **Route Creation**: Combined source-destination pairs for route analysis

### Data Preparation
- **Feature Selection**: Removed non-correlated features (Date_of_journey, Journey_day, Flight_code, Source, Destination)
- **One-Hot Encoding**: Applied to categorical variables (Airline, Class, Departure, Arrival, day_of_week, route, Total_stops)
- **Final Dataset**: 76 features after encoding

## Machine Learning Models

The project implements and compares three regression models:

### 1. Linear Regression
- **R-squared Score**: 0.855
- Basic linear model for baseline comparison

### 2. Gradient Boosting Regressor
- **R-squared Score**: 0.894
- Improved performance with ensemble methods

### 3. XGBoost Regressor
- **R-squared Score**: 0.935** (Best Performance)
- Advanced gradient boosting with optimal results

### Model Validation
- **Train-Test Split**: 80-20 ratio
- **Random State**: 42 for reproducibility
- **Baseline Comparison**: Random predictions scored -9.25, confirming model effectiveness

## Key Visualizations

1. **Box Plots**: Distribution analysis for duration, days left, and fare
2. **Airline Comparison**: Interactive Plotly box plots for fare by airline
3. **Route Analysis**: Bar charts for flight frequency and average fares
4. **Time Series**: Fare trends based on booking timing
5. **Correlation Heatmaps**: Feature relationship analysis

## Requirements

### Libraries Used
```python
pandas
numpy
matplotlib
seaborn
plotly
scipy
scikit-learn
xgboost
```

## Usage

1. **Data Loading**: Load the cleaned dataset (`Cleaned_dataset.csv`)
2. **EDA Execution**: Run exploratory analysis cells for insights
3. **Preprocessing**: Apply feature engineering and encoding
4. **Model Training**: Train and compare different ML models
5. **Prediction**: Use the best model (XGBoost) for fare predictions

## Model Performance Summary

| Model | R-squared Score | Performance |
|-------|----------------|------------|
| Linear Regression | 0.855 | Good |
| Gradient Boosting | 0.894 | Better |
| **XGBoost** | **0.935** | **Best** |

## Business Applications

This model can be used for:
- **Dynamic Pricing**: Airlines can optimize ticket pricing strategies
- **Customer Insights**: Understanding price sensitivity and booking patterns
- **Revenue Management**: Maximizing revenue through data-driven pricing
- **Market Analysis**: Competitive pricing analysis across routes and airlines

## Future Enhancements

- Feature importance analysis for XGBoost model
- Hyperparameter tuning for improved performance
- Cross-validation for robust model evaluation
- Integration of external factors (seasonality, holidays, fuel prices)
- Real-time prediction API development

## Project Structure

```
flight_fare_prediction/
├── flight_fare.ipynb          # Main Jupyter notebook
├── Cleaned_dataset.csv        # Dataset (not included in repo)
├── README.md                  # This file
└── requirements.txt           # Dependencies
```

---

**Note**: This project demonstrates the complete machine learning pipeline from data exploration to model deployment, achieving 93.5% accuracy in flight fare prediction using advanced ML techniques.