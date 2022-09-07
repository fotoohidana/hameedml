# hameedml
```RStudio
- [x] Complete!
Coding in R in a ml project regarding barbell manner.
All the required libraries were loaded.
- item1
The data files: pml-training and pml-testing were introduced.
- item2
The "classe" in training data set was defined as the outcome of the model.
The figures such as belt, arm, etc. in relation to classe were explained by the use of ggplot2.
- item3
Subject selection applied to variables by the evaluation of RMSE.
- item4
Model selection approach folowed by below algorithm.
Dividing data to training/test/validation.
InTrain all competing models on the train data set to pick the best on validation.
Appropriately assessing performance on new data apply to test data set.
- item5
Implementing the modFit (train, classe) with selected figures.
- item6
Predict(modFit,testing).
- item7
Use my prediction model to predict 20 different test cases. 
##  [1] B A B A A E B B A A B C B A E E A B B B
## Levels: A B C D E
