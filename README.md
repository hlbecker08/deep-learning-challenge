# deep-learning-challenge
The final analysis can be found below within the readme. Our inital code for creating the neural network model can be found in the file 'Starter_Code.ipynb' with its trained model named 'AlphabetSoupCharity.h5'. The three attempts to make the model more efficient is found under 'AlphabetSoupCharity_Optimization.ipynb' with its trained model called 'AlphabetSoupCharity_Optimization.h5'. This project was done with Conner Dekok. 


## Overview 

* The purpose of this analysis is to predict whether or not a charity is successful or not using a neural network model.
* The information we are given to determine this is	'EIN','NAME','APPLICATION_TYPE', 'AFFILIATION', 'CLASSIFICATION', 'USE_CASE', 'ORGANIZATION', 'STATUS', 'INCOME_AMT', 'SPECIAL_CONSIDERATIONS','ASK_AMT', 'IS_SUCCESSFUL'. The 'IS_SUCCESSFUL' column is what we are looking to predict.


## Results

Data Preprocessing
* What variable(s) are the target(s) for your model?
    * 'IS_SUCCESSFUL' is the only target variable we used.
* What variable(s) are the features for your model?
    * 'APPLICATION_TYPE', 'AFFILIATION', 'CLASSIFICATION', 'USE_CASE', 'ORGANIZATION', 'STATUS', 'INCOME_AMT', 'SPECIAL_CONSIDERATIONS','ASK_AMT'
* What variable(s) should be removed from the input data because they are neither targets nor features?
    * 'EIN','NAME'

Compiling, Training, and Evaluating the Model
* How many neurons, layers, and activation functions did you select for your neural network model, and why?
    * We used two hidden layers, both using ReLU activation functions. The first has 80 neurons and the second has 30. For the output layer we used one sigmoid neuron. 
    * We chose two hidden layers of 80 and 30 nuerons to try and capture enough complexity of the data without being excessive and overfitting the data.
    * For activation functions ReLU is a good starting point for its computationally efficiency and ability to prevent the vanishing gradient problem which can occur in other activation functions. Sigmoid is used in the output layer because we are looking for a binary answer of 0 or 1.
* Were you able to achieve the target model performance?
    * No the best we were able to acheive was 73.01%
* What steps did you take in your attempts to increase model performance?
    * The following attempts were made
        * Using Tanh activation functions in the hidden layers. While Relu passes only positive values Tanh includes negative. Since our data set has negative values we wanted to test to see how it would do with Tanh. It came to an accuarcy of 72.85%
![Test1](https://github.com/user-attachments/assets/7e548e8a-e72e-408c-bb41-272414752a19)

        * Adding a third hidden layer and returning to Relu. We wanted to see if it was possible we were underfitting the model with two layers. This came to an accuarcy of 72.83%
![Test2](https://github.com/user-attachments/assets/7c55fc93-e6b3-4604-9245-2b7940ae2ca5)

        * Returning to two layers and using less hidden layer nuerons (24 and 16) to see if we have overfit the model. This came to an accuarcy of 73.01%
![Test3](https://github.com/user-attachments/assets/298e6083-c1ba-4e94-84a8-ffbc181bc815)


## Summary

Overall, we did not find an optimal method to train our model. Our goal was to achieve an accuracy of 75%, but we only reached 73.01%. It is recommended to try a logistic regression model next to see if it is more accurate. A logistic regression model is a simpler approach, but it can be highly effective for binary classification problems, such as our case of predicting whether a charity is successful or not.
