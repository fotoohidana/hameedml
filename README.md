# hameedml
Coding in R in a ml project regarding barbell manner.
All the required libraries were loaded.
The data files: pml-training and pml-testing were introduced.
The "classe" in training data set was defined as the outcome of the model.
The figures such as belt, arm, etc. in relation to classe were explained by the use of ggplot2.
Subject selection applied to variables by the evaluation of RMSE.
Model selection approach folowed by below algorithm.
Dividing data to training/test/validation.
InTrain all competing models on the train data set to pick the best on validation.
Appropriately assessing performance on new data apply to test data set.
Implementing the modFit (train, classe) with selected figures.
Predict(modFit,testing). 
Use my prediction model to predict 20 different test cases. 
