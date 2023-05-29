# Neural_Network_Charity_Analysis

## Overview of the Analysis
The purpose of this analysis was to develop a deep learning model using a neural network to predict whether applicants to AlphabetSoup would be successful if funded. The goal was to optimize the model's performance and achieve a predictive accuracy higher than 75%.

## Results

### Preprocessing Data for a Neural Network Model
- **What variable(s) are considered the target(s) for your model?**: "IS_SUCCESSFUL"
- **What variable(s) are considered to be the features for your model?**: "APPLICATION_TYPE," "AFFILIATION," "CLASSIFICATION," "USE_CASE," "ORGANIZATION," "STATUS," "INCOME_AMT," "SPECIAL_CONSIDERATOINS," and "ASK_AMT"; the optimized model includes "NAME" as a feature as well.
- **What variable(s) are neither targets nor features, and should be removed from the input data?**: - Original model: "EIN" and "NAME", Optimized model: "EIN"

### Compiling, Training, and Evaluating the Model
- **AlphabetSoupCharity**
  - Number of neurons: Layer 1 - 80, Layer 2 - 30
  - Activation Functions: All layers - relu
    - The model contains 2 hidden node layers, with 80 neurons in layer 1 and 30 neurons in layer 2. This configuration was chosen based on the initial output example in the file, as a starting point to assess the model's performance.
  - Target Model Performance: 72.71%
    - The target model performance of 75% was not achieved in this model. Moving forward, I made adjustments to the model to improve its accuracy.

  ![AlphabetSoupCharity_ModelAccuracy](Screenshots/AlphabetSoupCharity_EvaluateTheModel.png)

### Optimize the Model
- **Attempt 1**
  - Number of Neurons: Layer 1 - 80, Layer 2 - 40, Layer 3 - 20
  - Activation Functions: Layer 1 - ReLU, Layer 2 - tanh, Layer 3 - sigmoid
    - In this attempt, an additional hidden layer with 20 neurons (Layer 3) was added, the number of neurons in Layer 2 was increased to 40, and the activation functions were adjusted to ReLU, tanh, and sigmoid for Layers 1, 2, and 3, respectively. With the additional hidden layer and new activation functions I aimed to increase the accuracy of the model.
  - Accuracy: 72.91%
    - In this attempt, the model's accuracy slightly improved compared to the original model, but it still did not meet the target performance of 75%.

  ![AlphabetSoupCharity_Optimization_Try1_ModelAccuracy](Screenshots/AlphabetSoupCharity_Optimization_Try1_EvaluateTheModel.png)

- **Attempt 2**
  - Number of Neurons: Layer 1 - 200, Layer 2 - 150, Layer 3 - 100, Layer 4 - 50
  - Activation Functions: All layers - tanh
    - This attempt involved increasing the number of neurons in each hidden layer, adding an additional hidden layer, and changing the activation function to tanh for all layers. The model had 200 neurons in Layer 1, 150 neurons in Layer 2, 100 neurons in Layer 3, and 50 neurons in Layer 4. Adding an additional hidden layer again and changeing the activation functions as well as a larger number of epochs I aimed to increase the accuracy of the model and give a longer time for the model to learn.
  - Accuracy: 72.9%
    - In this attempt, the model's accuracy did not improve significantly compared to the original model.

  ![AlphabetSoupCharity_Optimization_Try2_ModelAccuracy](Screenshots/AlphabetSoupCharity_Optimization_Try2_EvaluateTheModel.png)

- **Final Attempt (3)**
  - Number of Neurons: Layer 1 - 125, Layer 2 - 50, Layer 3 - 20, Layer 4 - 10
  - Activation Functions: All layers - tanh
    - The final attempt introduced another adjustment to the model by changing the number of neurons in each hidden layer. Layer 1 had 125 neurons, layer 2 had 50 neurons, layer 3 had 20 neurons, and layer 4 had 10 neurons. I reduced the number of epochs because the previous attempt did not see benefits and lowered the number of neurons to increase the accuracy of the model and aim for it to be more efficient. The largest change was keeeping the NAME feature in the assessment and adding it to the variables being binned. This change had a large change in the accuracy, unlike the previous adjustments.
  - Accuracy: 77.82%
    - In the final attempt, the model's accuracy significantly improved, surpassing the target performance of 75%.

  ![AlphabetSoupCharity_Optimization_ModelAccuracy](Screenshots/AlphabetSoupCharity_Optimization_EvaluateTheModel.png)

## Summary
In summary, the deep learning model using a neural network showed improvements in performance through optimization attempts. The best model achieved an accuracy of 77.82%, surpassing the target of 75% accuracy. Several modifications were made to the model architecture, including adjusting the input data, adding more neurons and hidden layers, and changing the activation functions.

## Recommendation
Considering the results and the classification problem at hand, an alternative model that could potentially provide better performance is the Random Forest classifier. Random Forest is an ensemble learning method that combines multiple decision trees to make predictions. It can handle high-dimensional data, capture complex interactions, and handle both numerical and categorical features effectively.

By utilizing Random Forest, we can benefit from its ability to handle feature interactions and provide feature importances, allowing for better interpretability. Additionally, Random Forest is less prone to overfitting and can handle imbalanced datasets. With further experimentation and tuning, the Random Forest model may yield higher accuracy and better performance for the loan prediction risk analysis.
