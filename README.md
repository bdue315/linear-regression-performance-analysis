# linear-regression-performance-analysis

--Project Goal--<br>
This was my TripleTen bootcamp Sprint 12 project. The objective of the project is to evaluate and compare the training and prediction times and evaluation scores of multiple linear regression models and choose the best one.

--Project Description--<br>
Rusty Bargain used car sales service is developing an app to attract new customers. In that app, you can quickly find out the market value of your car. You have access to historical data: technical specifications, trim versions, and prices. You need to build the model to determine the value.

Rusty Bargain is interested in:

the quality of the prediction;
the speed of the prediction;
the time required for training

--Dataset Summary--<br>
The dataset contains information about the used cars, most notably useful for predictions:

1. Price<br>
2. Vehicle Type<br>
3. Year<br>
4. Gearbox<br>
5. Mileage<br>
6. Model<br>
7. Brand<br>
8. Repaired (boolean for if the vehicle has been repaired)<br>
9. Postal Code<br>
10. Feature engineered 'created_to_crawled' date column using the dates crawled and date created columns<br>


--Techniques and Process--<br>
1. Data download and preprocessing<br>
   a. Feature engineering<br>
   b. One Hot Encoding<br>
   c. Converted columns to category type to be used in encoding<br>
   d. Standard Scaler<br>
**This project goal was not focused on Exploratory Data Analysis, so even though that would be a standard step, it was omitted to focus on the objectives**<br>
2. Model training<br>
   a. Linear Regression base model<br>
   b. Decision Tree<br>
   c. Random Forest<br>
   d. LightGBM<br>
   e. CatBoost<br>
   d. Hyperparameter tuning<br>
3. Model Evaluation<br>
   a. RMSE<br>
   b. Training time<br>
   c. Prediction time<br>

--Results--<br>
I was able to improve the models enough to have better RMSE and Test RMSE scores than the baseline linear regression model.<br>
**The most significant improvement was the CatBoost model w/ an RMSE of 2071 compared to 3370 baseline and a Test RMSE of 2064 compared to 6281 baseline.**<br>
The worst training and prediction time performance: CatBoost also had the longest training time compared to the other models. It was about double that of Random Forest and LightGBM.<br>

Baseline Linear Regression:<br>
RMSE: 3370.619291921021<br>
Test RMSE: 6281.211347513317<br>

Decision Tree:<br>
RMSE: 2516.4901436058767<br>
Test RMSE: 2495.5551406899185<br>
Training time: 0.23401117324829102<br>
Prediction time: 0.003443479537963867<br>

Random Forest:<br>
RMSE: 2389.4091770580676<br>
Test RMSE: 2366.2767131549053<br>
Training time: 1.4818060398101807<br>
Prediction time: 0.01737833023071289<br>

LightGBM:<br>
RMSE: 2143.8576132850567<br>
Test RMSE: 2121.5609175572217<br>
Training time: 1.5945460796356201<br>
Prediction time: 0.20604872703552246<br>

CatBoost:<br>
RMSE: 2071.405636547941<br>
Test RMSE: 2064.30355961189<br>
Training time: 2.9004037380218506<br>
Prediction time: 0.018863201141357422<br>

I had to decrease the parameter grid metrics a few times on a few of the models to get them to train in an acceptable timeframe.
