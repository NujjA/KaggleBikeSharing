# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### Najla Ahmad

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?

I had to make sure all predicted values were positive. In some cases they were and in some cases they were not. I loaded in the sample submission and then replaced the count with the predictions that were saved. 

### What was the top ranked model that performed?
WeightedEnsemble_L3 consistently performed well across my project. 

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?

Some of the features that should be categorical were treated as numeric. Datetime was not separated into parts.  

### How much better did your model preform after adding additional features and why do you think that is?

Since the categorical features were treated as numeric, it was probably finding false relationships between the values and seeing some values as "closer" to other values instead of separate categories. Once they were changed to categorical, the model had the proper semantics to train on the data. 
Similiarly, the datetime as one value as one field gives less information than breaking out the data into day, month, year, and time. Using these new features, the model can find trends and patterns that would otherwise not be able to be separated out. 

The using rt mean sq error, the score before doing EDA was -53.121407 and the score after separating out the new features was -38.370172. This is a 27.77 percent improvement, which is quite significant. 

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
My biggest improvement was during EDA, hyperparameter helped but not as much. At first, I was afraid that the models were actually worse because I got -41.724163 for the score. However, when I submitted to kaggle, my score actually improved from 0.49623 to 0.4383. Since this was running on a limited amount of time, I believe this could be improved further. 

### If you were given more time with this dataset, where do you think you would spend more time?
I think the EDA gave a huge boost in information and accuracy and doesn't need to be revisited. I would spend much more time on hyperparameter tuning, because that is where I will be able to find improvement still. I would want to increase the range in the learning rate choices for both NN and CAT. I would also like to do HPO with other models as well. 

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.


![model_train_score.png](img/hpo_table.PNG)

### Create a line plot showing the top model score for the three (or more) training runs during the project.

![model_train_score.png](img/model_train_score_new.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

![model_test_score.png](img/model_test_score_new.png)

## Summary
I first ran the dataset as it was given and as expected the results weren't great. Doing EDA by changing values to categorical that should be and also parsing out numeric information from the datetime field gave the biggest boost in performance. I added year, month, day, and time as values. EDA was very successful. Hyperparameter tuning was the hardest part for me as some combinations of the parameters would not run properly in the given amount of time. While I found some improvement, I think this is where I would spend the most time if I were to come back to this dataset. 
