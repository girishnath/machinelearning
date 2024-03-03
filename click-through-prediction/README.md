# Predict whether an online advertisement will be clicked

*Girish Natarajan*

### Executive summary
*To be added later*

### Rationale
Advertising is a 500+ billion dollar industry. Being able to predict the probability of clicks on a given advertisement would enable websites to efficiently use their digital space to place the right ads in front of the right user. The result would be higher profit for websites, and a better user experience for the user. This balance is very important for the sustenance of the free and open internet.

### Research Question
Given a user and the characteristics of a website that they are browsing, determine how likely it is that they will click on an advertisement that they are shown.

### Data Sources
The datasets conidered for this project were available as part of contests in Kaggle. The two datasets that seemed like a good fit were:
* A week worth of data from Criteo Labs, as part of their [Display Advertising Challenge](https://www.kaggle.com/competitions/criteo-display-ad-challenge).
* 11 days worth of data from mobile ads company Avazu as part of their [Click-Through Rate Prediction Challenge](https://www.kaggle.com/competitions/avazu-ctr-prediction/overview)

Of these, the [dataset](https://www.kaggle.com/competitions/avazu-ctr-prediction/overview) from Avazu was chosen for the exercise.

### Methodology
CRISP-DM was leveraged as the structured framework for problem solving. As part of the project, extensive data analysis, understanding and feature engineering were performed. For model training, classification algorithms such as Logistic Regression, KNN, Decision Trees and Support Vector Machines were leveraged. Techniques also involved hyper parameter tuning, and model selection based on performance objectives.

### Results
A major learning was that with high dimensionality (~10K features after one-hot encoding), and large size of dataset (~4MM at 10% sampling), the capablities of a normal runtime was exceeded. For this exercise, GridSearch of various hyperparameters was conducted on 4 models - `LogisticRegression`, `DecisionTreeClassifier`, `KNearestNeighborClassifier` and `SVC`.

Based on the training runs that could be completed, `LogisticRegression` with a `max_iter=10000` yielded the best accuracy of `0.835`. The log loss for this model was `0.397`. The ROC Curve and Confusion Matrix were also analyzed prior to picking `LogisticRegression` as the winning model for this exercise.


![Confusion Matrix](images/Confusion_Matrix_LogisticRegression.png)
![ROC](images/ROC_Curve_LogisticRegression.png)

### Next steps
While the individual models did yield minimally higher accuracy than baseline, other methods such as ensemble techniques specifically Random Forest should be tried. Since the dataset has high dimensionality and size, GPU based training would be required for efficient exploration.

Hence, as a next step, exploration of ensemble techniques using GPU based library such as `cuML` is proposed.

#### Outline of project

- [Notebook 1: Data understanding](1-click-through-prediction-data-understanding.ipynb)
- [Notebook 2: Data Preparation](2-click-through-prediction-data-preparation.ipynb)
- [Notebook 3: Model Training](3-click-through-prediction-modeling)
