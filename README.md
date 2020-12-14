# Preventing fraud by spotting fake currency.

## Basic Overview:

* **Goal**: Create a model that helps banks in preventing fraud to spot fake currency.

* The cost of counterfit currency circulating in our economy has devastating affects that cab disfigure the economic aparatus. Banks are on the frontlines to help the governemnt in making sure the economy is operating flawlessly. This effort by humans alone is not possible.

* Therefore, this project uses data acquisition, cleaning, and algorithm testing to construct a model that helps banks detect fake currency.



## Resources and code used:

* ***Python Version***: 3.8
* ***Packages***: Pandas, Matplotlib, NumPy, Pickle, Sklearn (Decision Tree, RandomForest, train_test_split), LazyPredict, Flassger
* ***Data Source***: UCI: Bank Note Authentication


## Data Acquisition:

* Used UCI's dataset on Bank Note Authentication.
* Data were extracted from images that were taken from genuine and forged banknote-like specimens. For digitization, an industrial camera usually used for print inspection was used. The final images have 400x 400 pixels. Due to the object lens and distance to the investigated object gray-scale pictures with a resolution of about 660 dpi were gained. Wavelet Transform tool were used to extract features from images.
* Original data consists of about 12500 rows and 5 columns.



## Data Cleaning:

  ### Attribute Selection & data preperation:
    
    * The dataset did not have any outliers when boxplots were constructed (inter-quartile-range presentation).
    * Therefore, the raw dataset was fine to further construct the model.
    

## Model Building:

* Using LazyPredict library we were able to get an overview of how all the algorithms perform with the given dataset. The following is the outcome:
<img src='images/plot_a.png' width='35%' height='35%'>

* Therefore, after the above results the DecisionTree and RandomForest algorithms were further taken for hyper parameter tuning to evaluate their strenghts for model building.
* DecisionTree was able to provide a score of 95%
* RandomForest was able to provide a score of 98%.


## Conclusion:

* Considering the possiblity of overfitting it was decided to select DecisionTree for model construction. 


## Model Deployment:

* With the help of Pickle library the model was exported as an API.
* Further, the project was bundled in a docker to enable portability.
* Using Flask a server was created to onboard the API and Flassger was used to create a front-end deployment of the model.
* Link to the front-end deployment: https://ml-fake-note-detection.herokuapp.com/apidocs/#/default/get_predict

### The file with detailed step-by-step code is [here](/Deploy_Model.ipynb).
