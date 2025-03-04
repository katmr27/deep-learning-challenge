# Module 21 Report

## Overview of the Analysis

In this challenge machine learning is used to analyze financial data to determine predictability of successful applicants that received funding from Alphabet Soup Charity.

### Results

- **Data Preprocessing**
  - **What variable(s) are the target(s) for your model?**
    - For the target, I used the `Is_Successful` column as my `y` variable.
  - **What variable(s) are the features for your model?**
    - For features, I used the rest of the data, including the cleaned `Classifications` and `Application_Types` columns, as my `X` variable.
  - **What variable(s) should be removed from the input data because they are neither targets nor features?**
    - As part of preprocessing, the `EIN` and `NAME` columns were dropped from the DataFrame. During optimization, I also removed the `STATUS` column to improve accuracy.

- **Compiling, Training, and Evaluating the Model**
  - **How many neurons, layers, and activation functions did you select for your neural network model, and why?**
    - The model has 3 layers:
      - The first layer has 6 neurons.
      - The second layer has 3 neurons.
      - The third layer has 3 neurons.
      - The output layer has 1 neuron.
  - **Were you able to achieve the target model performance?**
    - No, the closest I was able to get was 73% accuracy.
  - **What steps did you take in your attempts to increase model performance?**
    - I initially started with fewer neurons, achieving around 71-72% accuracy.
    - I added more neurons to the first and second layers but did not see an increase in accuracy.
    - I added a third hidden layer with the same number of neurons as the second layer, which improved accuracy.
    - I attempted to increase accuracy by adding a fourth hidden layer, but the accuracy actually decreased.
    - I also attempted to decrease the number of neurons in the first layer to help with accuracy, but there was little change.

      
## Summary

Recommendation:
The machine learning model demonstrates high overall performance, with an accuracy of 0.99. However, the evaluation depends on the specific problem at hand:

	1. Predicting Class 0 (Healthy Loans):
		○ The model achieves perfect precision and recall for Class 0, indicating it is excellent at identifying healthy loans without false negatives or false positives.
	2. Predicting Class 1 (Risky Loans):
		○ While the recall for Class 1 is quite high at 0.95, the precision is lower at 0.87. This means the model is fairly good at identifying risky loans but has a slightly higher rate of false positives (predicting a loan as risky when it is not).
  
Considerations:

	• Importance of Class Prediction: If the primary goal is to ensure that all risky loans are correctly identified (minimizing false negatives), then the model's high recall for Class 1 is beneficial.
	• Trade-offs: If false positives are costly and it's crucial to minimize them, the precision for Class 1 should be improved, or different models/thresholds should be considered.
 
Overall, this model performs best given its high accuracy and balanced performance metrics. However, the decision to use this model should depend on the relative importance of correctly predicting healthy versus risky loans. If minimizing false positives in risky loans is critical, additional tuning or alternative models might be warranted.

