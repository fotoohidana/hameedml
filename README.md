# hameedml
```RStudio
- [x] Complete!
# Coding in R in a ml project regarding barbell manner.
## All the required libraries were loaded.
   library (ISLR), library (ElemStatLearn), library (ggplot2), library (Caret), library (dplyr), library (corrplot)

- item1
## The data files: pml-training and pml-testing were introduced.
   set seed (123)
   pml <- read.csv("E:/Course Project/pml-training.csv")
   pml <- read.csv("E:/Course Project/pml-testing.csv")
- item2
## The "classe" in training data set was defined as the outcome of the model.
 
## The figures such as belt, arm, etc. in relation to classe were explained by the use of ggplot2, plot_vars, and dplyr.
   plot_vars <- dplyr:: select(pml-training-cl,-classe)
   
- item3
## Subject selection applied to variables by the evaluation of RMSE.

- item4
## Model selection approach folowed by below algorithm.
### Dividing data to training/test/validation.
### InTrain all competing models on the train data set to pick the best on validation.
    inTrain <- createDataPartition (pml-training-cl$classe, p=0.75, list=F)
    training <- pml-tarining-cl[-inTrain,]
    validation <- pml-tarining-cl[-inTrain,]
### Appropriately assessing performance on new data apply to test data set.

- item5
# Implementing the modFit (train, classe) with selected figures.

- item6
  modFit <- train(classe ~. method="rf", data= training)
  
- item7
# Building variants
##	I built 3 alternative models and compare the training results due to poorly perform of Random Tree
##	All 3 models (Random forest (RF), Gradient boosting (GDM) and Support vector machine (SVM)) perform significantly better in terms of accuracy than the tree model
##	I decide to continue with RF in concern with accuracy 

   model_results <- resamples(list(DT = mod_tree, RF = mod_rf, GBM = mod_gbm, SVM = mod_svm))
   bwplot(model_results)
   
- item8
# Cross-validation test
  options(max.print = 1000)
  pred_rf <- predict(mod_rf, validation)
  pred_svm <- predict(mod_svm, validation)
  confusionMatrix(pred_rf, factor(validation$classe))
## Accuracy : 0.9953        
##            95% CI : (0.993, 0.997)
##            No Information Rate : 0.2845        
##            P-Value [Acc > NIR] : < 2.2e-16     
##                                         
##                   Kappa : 0.9941        
## Statistics by Class:
## 
##                      Class: A Class: B Class: C Class: D Class: E
## Sensitivity            1.0000   0.9958   0.9906   0.9925   0.9945
## Specificity            0.9989   0.9982   0.9978   0.9993   1.0000
## Pos Pred Value         0.9971   0.9926   0.9895   0.9963   1.0000
## Neg Pred Value         1.0000   0.9990   0.9980   0.9985   0.9988
## Prevalence             0.2845   0.1935   0.1743   0.1639   0.1837
## Detection Rate         0.2845   0.1927   0.1727   0.1627   0.1827
## Detection Prevalence   0.2853   0.1941   0.1746   0.1633   0.1827
## Balanced Accuracy      0.9994   0.9970   0.9942   0.9959   0.9972

- item9
## Predicting on test data
## Predict(modFit,testing).
   pred <- predict (modFit, pml-testing)

## Use my prediction model to predict 20 different test cases. 
   qplot(classe, pred, data=pml-testing)
##  [1] B A B A A E B B A A B C B A E E A B B B
## Levels: A B C D E
