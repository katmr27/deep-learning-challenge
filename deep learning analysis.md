# Module 21 Report

## Overview of the Analysis

In this challenge machine learning is used to analyze financial data to determine predictability of successful applicants that received funding from Alphabet Soup Charity.

## Results

### Data Preprocessing
  - **What variable(s) are the target(s) for your model?**
    - For the target, I used the `Is_Successful` column as my `y` variable.
  - **What variable(s) are the features for your model?**
    - For features, I used the rest of the data, including the cleaned `Classifications` and `Application_Types` columns, as my `X` variable.
  - **What variable(s) should be removed from the input data because they are neither targets nor features?**
    - As part of preprocessing, the `EIN` and `NAME` columns were dropped from the DataFrame. During optimization, I also removed the `STATUS` column to improve accuracy.

### Compiling, Training, and Evaluating the Model
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
![image](https://github.com/user-attachments/assets/dbc6c3c6-515f-4fcb-8d7a-8eb7643bf5bc)
![image](https://github.com/user-attachments/assets/2a7a9b93-58d1-462a-a498-9acd5179c74a)

    - I added more neurons to the first and second layers, but this did not result in any increase in accuracy. However, adding a third hidden layer with the same number of neurons as the second layer led to an improvement in accuracy. When I attempted to increase accuracy further by adding a fourth hidden layer, the accuracy actually decreased. I also tried decreasing the number of neurons in the first layer to help with accuracy, but there was little change.

![image](https://github.com/user-attachments/assets/fbe53115-0ef0-4c08-9f08-b4c01ae12fb0)
![image](https://github.com/user-attachments/assets/94becd16-18a7-47f6-83d1-d3bde8a492de)

      
## Summary
The deep learning model implemented achieved a maximum accuracy of around 73%. Despite various attempts to enhance performance, including adjusting the number of neurons and adding multiple hidden layers, the improvements in accuracy were modest. The model showed some sensitivity to these changes, indicating that further optimization of the network architecture alone might have limited potential for significant gains in accuracy.

### Recommendation:
- To address this classification problem more effectively, I recommend exploring ensemble learning methods such as Random Forest or Gradient Boosting. Ensemble models have the advantage of combining the predictions from multiple base models, which often leads to better generalization and improved performance on classification tasks.

- Additionally, implementing techniques like cross-validation can help in selecting the best hyperparameters, thereby enhancing model robustness. Exploring feature engineering to create new, more informative features might also provide a boost in accuracy by offering the model more relevant input data to work with.
Overall, this model performs best given its high accuracy and balanced performance metrics. However, the decision to use this model should depend on the relative importance of correctly predicting healthy versus risky loans. If minimizing false positives in risky loans is critical, additional tuning or alternative models might be warranted.

- Overall, while the deep learning model offers a reasonable starting point, transitioning to ensemble methods and incorporating advanced techniques could provide a more powerful solution for this classification challenge.
