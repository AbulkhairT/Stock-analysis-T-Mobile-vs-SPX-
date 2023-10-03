# Stock Market Daily Trading Label Predictor using Sliding Window Approach

Discovering patterns in past stock behavior

This project focuses on predicting daily trading labels for stock behavior based on historical data. Using a sliding time window approach, 
the project aims to identify patterns in past stock behavior and predict whether the stock will go up or down on a given day
The project provides a detailed analysis of the stock's behavior and predicts daily trading labels for the fourth and fifth years 
based on the patterns observed in the first three years. The ensemble learning approach combines predictions from different sliding window 
sizes to potentially improve prediction accuracy.

Approach: Used the first three years as training data and the next two years as testing data.

Languages and packages used: Python, Pandas, and other libraries 


Assigning the True Labels to the document to be able to manipulate this variable for both stocks: 
<img width="500" alt="Screenshot 2023-10-03 at 2 33 29 PM" src="https://github.com/AbulkhairT/Stock-analysis-T-Mobile-vs-SPX-/assets/125773898/2fdb333f-efda-4f6d-9088-cf300414121f">

Calculate the probability that tomorrow is going to be positive day, meaning the stock will grow. In case with T-Mobile ( TMUS) it is 52% probability of a positive day
<img width="500" alt="Screenshot 2023-10-03 at 2 34 41 PM" src="https://github.com/AbulkhairT/Stock-analysis-T-Mobile-vs-SPX-/assets/125773898/ba1f4b97-b666-4f89-80cf-8d3dd55b2c38">

Calculates the total outcome of 3 consequetive days, in case 2 days were negative, what is the probability that the 3rd day will be positive? 
<img width="500" alt="Screenshot 2023-10-03 at 2 38 32 PM" src="https://github.com/AbulkhairT/Stock-analysis-T-Mobile-vs-SPX-/assets/125773898/398f224c-722f-4996-ba29-091c12660de4">

Calculates the total outcome of 3 consequetive days, in case 2 days were positive, what is the probability that the 3rd day will be negative? 
<img width="500" alt="Screenshot 2023-10-03 at 2 41 30 PM" src="https://github.com/AbulkhairT/Stock-analysis-T-Mobile-vs-SPX-/assets/125773898/7e6659f9-1cfd-4ff0-9567-a6ab2730e2bc">

This part predicts stock trading labels for the years 2020 to 2022 based on patterns observed in the years 2017 to 2019, different window slides were combined to improve accuracy
<img width="500" alt="Screenshot 2023-10-03 at 2 46 15 PM" src="https://github.com/AbulkhairT/Stock-analysis-T-Mobile-vs-SPX-/assets/125773898/ea640bcf-4772-4d7a-bab2-74b9f677609a">

Calculates accuracy of our W's, The W value (highest) for TMUS is: 3 and The value (highest) for SP500 is: 2
<img width="500" alt="Screenshot 2023-10-03 at 2 47 01 PM" src="https://github.com/AbulkhairT/Stock-analysis-T-Mobile-vs-SPX-/assets/125773898/8e062112-4525-4991-9144-f8a224a2399e">

Then Calculate values such as: TP FP, TN, FN, TPR, TNR to calculate the perfomance of the prediction model. While the model has positive aspects, it also made mistakes. For instance: 
TPR fpr W2 is 65% meaning it was able to correctly predict positive days in 64% of cases, while only 34% for the negative days. In conclusion, the W2 had the best perfromance for the 
TMUS stock. 

Metrics for TMUS:

Metrics for Predict_W2:                                    
TP: 503
FP: 476
TN: 251
FN: 280
TPR: 0.6424010217113666
TNR: 0.3452544704264099

Metrics for Predict_W3:
TP: 0
FP: 0
TN: 727
FN: 783
TPR: 0.0
TNR: 1.0

Metrics for Predict_W4:
TP: 0
FP: 0
TN: 727
FN: 783
TPR: 0.0
TNR: 1.0

Metrics for Predict_Ensemble:
TP: 0
FP: 0
TN: 727
FN: 783
TPR: 0.0
TNR: 1.0

Metrics for SPY:

Metrics for Predict_W2:
TP: 607
FP: 481
TN: 198
FN: 224
TPR: 0.7304452466907341
TNR: 0.2916053019145803

Metrics for Predict_W3:
TP: 0
FP: 0
TN: 679
FN: 831
TPR: 0.0
TNR: 1.0

Metrics for Predict_W4:
TP: 0
FP: 0
TN: 679
FN: 831
TPR: 0.0
TNR: 1.0

Metrics for Predict_Ensemble:
TP: 0
FP: 0
TN: 679
FN: 831
TPR: 0.0
TNR: 1.0

Used buy and hold strategy for both stocks and uses W2 as the hyperparameter since it was the best performing factor. It then visualizes both stocks to show the difference in profits/losses: 
<img width="500" alt="Screenshot 2023-10-03 at 3 01 12 PM" src="https://github.com/AbulkhairT/Stock-analysis-T-Mobile-vs-SPX-/assets/125773898/911db688-3d75-406f-9f69-cb57b9235c97">

Conclusion: 
W2 turned out to be the most balanced predictor for both stocks in this case. For W3, W4 and ensemble strategy the data might have been too homegeneous, perhaps it needed more diverse dataset to be trained on. 
So,  The models with window sizes of 3 and 4 (and the ensemble) are not very useful in their current state since they only predict one class. There's a need for further development or a different approach.
The provided code simulates the growth of a portfolio based on the Predict_W2 strategy and compares it to a "buy-and-hold" strategy. Ensemble method, which is supposed to combine predictions, didn't add value in this case

