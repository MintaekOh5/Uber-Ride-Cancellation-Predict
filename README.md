# Uber-Ride-Cancellation-Prediction
Analyze ride-sharing data from Uber operations for the year 2024 and predict which customer would cancel their ride.

## Overview
This project uses machine learning algorithm (LightGBM) to predict ride cancellations basedn on ratings, distance, average time for driver to reach pickup location (in minutes), average trip duration from pickup to destination (in minutes), etc. Workflow of this project includes EDA, data preprocessing, modeling, evaluation and predict. Also, this project compares logistic regression classifier and LGBM classifier to observe better prediction.

## Dataset
The dataset contains the following.
| Column | Description |
|:-------|:-------------|
| **Date** | Date of the booking |
| **Time** | Time of the booking |
| **Booking ID** | Unique identifier for each ride booking |
| **Booking Status** | Status of booking (Completed, Cancelled by Customer, etc.) |
| **Customer ID** | Unique identifier for customers |
| **Vehicle Type** | Type of vehicle (Go Mini, Go Sedan, Auto, etc.) |
| **Pickup Location** | Starting location of the ride |
| **Drop Location** | Destination location of the ride |
| **Avg VTAT** | Average time for driver to reach pickup location (minutes) |
| **Avg CTAT** | Average trip duration from pickup to destination (minutes) |
| **Booking Value** | Total fare amount |
| **Ride Distance** | Distance covered (km) |
| **Driver Ratings** | Rating given to driver (1-5 scale) |
| **Customer Rating** | Rating given by customer (1-5 scale) |
| **Payment Method** | Payment type (UPI, Cash, Credit Card, etc.) |

## EDA highlights
- Cancellation peaks during 10 A.M. and 6:00 P.M.
- Customer cancel their ride due to wrong address.
- Driver cancel the ride due to capacity issue.

## Preprocessing
- Target of this dataset is 'Cancelled Rides by customer'.
- Missing values handled by SimpleImputer.
- OneHotEncoder was used for categorical columns.

## Models
| Model | ROC-AUC | F1 | Accuracy |
|:-------------------|:-------:|:----:|:----------:|
| **Logistic Regression** | 0.0.87 | 0.30 | 0.74 |
| **LightGBM** | 0.96 | 0.53 | 0.89 |

## Cross validation
Cross-validation: Stratified K-fold (k = 7)

## Prediction Example using LGBM

- 'Vehicle Type': 'Auto',
- 'Pickup Location': 'Khandsa',
- 'Drop Location': 'Vasant Kunj',
- 'Avg VTAT': 15.1,
- 'Avg CTAT': 25.8,
- 'Booking Value': 6662,
- 'Ride Distance': 17,
- 'Driver Ratings': 1.7, 
- 'Customer Rating': 4.2, 
- 'Payment Method': 'UPI', 
- 'Month': 8, 
- 'Hour': 18  


This passenger will not cancel the ride with probability.
