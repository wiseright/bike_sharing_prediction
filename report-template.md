# Report: Predict Bike Sharing Demand with AutoGluon Solution
#### SAVINO GIUSTO

## Initial Training
### What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?
TODO: Add your explanation
When I started to analyze the Bike Sharing Demand Dataset I realized the it was a regression problem. I had to predict the number of total rentals per hour.
I noticed that the train dataset had the columns 'casual' and 'registered', instead the test dataset not. So I dropped these two columns before run the fit method of autogluon predictor. The same I did for predict method onto test dataset.
After run the predict method of predictor I noticed that the model predicted 77 bnegative values. Since we are trying to predict the hourly rental number of bike a negative values hasn't no meaning, so I set to zero all these values.


### What was the top ranked model that performed?
TODO: Add your explanation

## Exploratory data analysis and feature creation
### What did the exploratory analysis find and how did you add additional features?
TODO: Add your explanation
I donwloaded the package pandas-profile to assist me in data exploratory (file name: Report_001.html)
From this report I acknowledge that I add new feature:
* year, month, day, hour (I discated minute and second because they are zeros)
* convert with one-hot-encoding the features season and weather

Then I plot the histogram of features in train dataset:
![hist_train.png](img/features_histogram_001.png)

### How much better did your model preform after adding additional features and why do you think that is?
TODO: Add your explanation
After made the changes above-mentioned, the root_mean_squared_error passed from 2.17597 to 0.45968
The better score depends on the new features. Befero these changes the model fitting coudn't exploit the datetime information (it had uniform distribution) and season and wheather encoding.

## Hyper parameter tuning
### How much better did your model preform after trying different hyper parameters?
TODO: Add your explanation
auto_stack = True,
num_bag_folds = 10,
num_bag_sets = 20,

### If you were given more time with this dataset, where do you think you would spend more time?
TODO: Add your explanation

### Create a table with the models you ran, the hyperparameters modified, and the kaggle score.
|model|hpo1|hpo2|hpo3|score|
|--|--|--|--|--|
|initial|?|?|?|?|
|add_features|?|?|?|?|
|hpo|?|?|?|?|

### Create a line plot showing the top model score for the three (or more) training runs during the project.

TODO: Replace the image below with your own.

![model_train_score.png](img/model_train_score.png)

### Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.

TODO: Replace the image below with your own.

![model_test_score.png](img/model_test_score.png)

## Summary
TODO: Add your explanation
