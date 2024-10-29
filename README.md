# linear-regression-performance-analysis

--Project Goal--
This was my TripleTen bootcamp Sprint 12 project. The objective of the project is to evaluate and compare the training and prediction times and evaluation scores of multiple linear regression models and choose the best one.

--Project Description--
Rusty Bargain used car sales service is developing an app to attract new customers. In that app, you can quickly find out the market value of your car. You have access to historical data: technical specifications, trim versions, and prices. You need to build the model to determine the value.

Rusty Bargain is interested in:

the quality of the prediction;
the speed of the prediction;
the time required for training

--Dataset Summary--
The dataset contains information about the used cars, most notably useful for predictions:

1. Price
2. Vehicle Type
3. Year
4. Gearbox
5. Mileage
6. Model
7. Brand
8. Repaired (boolean for if the vehicle has been repaired)
9. Postal Code
10. Feature engineered 'created_to_crawled' date column using the dates crawled and date created columns



--Techniques and Process--
1. Data download and preprocessing
   a. Feature engineering
   b. One Hot Encoding
   c. Converted columns to category type to be used in encoding
   d. Standard Scaler
**This project goal was not focused on Exploratory Data Analysis, so even though that would be a standard step, it was omitted to focus on the objectives**
2. Model training
   a. Linear Regression base model
   b. Decision Tree
   c. Random Forest
   d. LightGBM
   e. CatBoost
   d. Hyperparameter tuning
3. Model Evaluation
   a. RMSE
   b. Training time
   c. Prediction time

--Results--
I was able to improve the models enough to have better RMSE and Test RMSE scores than the baseline linear regression model.
**The most significant improvement was the CatBoost model w/ an RMSE of 2071 compared to 3370 baseline and a Test RMSE of 2064 compared to 6281 baseline.**
The worst training and prediction time performance: CatBoost also had the longest training time compared to the other models. It was about double that of Random Forest and LightGBM.

Baseline Linear Regression:
RMSE: 3370.619291921021
Test RMSE: 6281.211347513317

Decision Tree:
RMSE: 2516.4901436058767
Test RMSE: 2495.5551406899185
Training time: 0.23401117324829102
Prediction time: 0.003443479537963867

Random Forest:
RMSE: 2389.4091770580676
Test RMSE: 2366.2767131549053
Training time: 1.4818060398101807
Prediction time: 0.01737833023071289

LightGBM:
RMSE: 2143.8576132850567
Test RMSE: 2121.5609175572217
Training time: 1.5945460796356201
Prediction time: 0.20604872703552246

CatBoost:
RMSE: 2071.405636547941
Test RMSE: 2064.30355961189
Training time: 2.9004037380218506
Prediction time: 0.018863201141357422

I had to decrease the parameter grid metrics a few times on a few of the models to get them to train in an acceptable timeframe.
