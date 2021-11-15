## Definition 

- Titanic sank after colliding with an iceberg, killing 1502 out of 2224 passengers and crew. 
- some groups of people were more likely to survive than others, such as women, children, and the upper-class.
- dataset https://www.kaggle.com/c/titanic/data

## Distribution of numerical feature values across the training dataset

- Total samples are 891 or 40% of the actual number of passengers on board the Titanic (2,224).
- Survived is a categorical feature with 0 or 1 values.
- Around 38% samples survived representative of the actual survival rate at 32%.
- Most passengers (> 75%) did not travel with parents or children.
- Nearly 30% of the passengers had siblings and/or spouse aboard.
- Fares varied significantly with few passengers (<1%) paying as high as $512.
- Few elderly passengers (<1%) within age range 65-80.

## Distribution of categorical feature values

- Names are unique across the dataset (count=unique=891)
- Sex variable as two possible values with 65% male (top=male, freq=577/count=891).
- Cabin values have several dupicates across samples. Alternatively several passengers shared a cabin.
- Embarked takes three possible values. S port used by most passengers (top=S)
- Ticket feature has high ratio (22%) of duplicate values (unique=681).


### Assumtions based on data analysis

Correlating each features with Survival.

- Age, Pclass, Sex and Embarked feature correlate with Survival.
- Ticket, Cabin, PassengerId freatures don't relate with Survival so can be dropped.
- We need to create a new feature, Family based on Parch and SibSp to get total count of family members on board.
- Engineer the Name feature to extract Title as a new feature.
- Derive a feature or a set of features from SibSp and Parch as they have zero correlation for certain values.
- Extract Titles from Names and test correlation between Titles and Survival, before dropping Names and PassengerId features.

### Missing null values

- Fill Age values using median for Age across sets of Pclass and Gender feature combinations. So, median Age for Pclass=1 and Gender=0, Pclass=1 and Gender=1, and so on...
- Embarked feature takes S, Q, C values based on port of embarkation. Our training dataset has two missing values. We simply fill these with the most common occurance.(mode)
- Fare feature for single missing value in test dataset using mode.


### Supervised learning algorithms that includes classification and regression are

- Logistic Regression
- KNN or k-Nearest Neighbors
- Support Vector Machines
- Naive Bayes classifier
- Decision Tree
- Random Forrest
- Perceptron
- Artificial neural network
- RVM or Relevance Vector Machine


### Modelling

-  Our problem is a classification and regression problem. We want to identify relationship between output with other variables or features.
- Logistic regression measures the relationship between the categorical dependent variable and one or more independent variables by estimating probabilities using a logistic function, which is the cumulative logistic distribution.
- Positive coefficients increase the log-odds of the response (and thus increase the probability), and negative coefficients decrease the log-odds of the response (and thus decrease the probability).
- (SVM)Given a set of training samples, each marked as belonging to one or the other of two categories, an SVM training algorithm builds a model that assigns new test samples to one category or the other, making it a non-probabilistic binary linear classifier.
-  (KNN, a non-parametric method) A sample is classified by a majority vote of its neighbors, with the sample being assigned to the class most common among its k nearest neighbors. If k = 1, then the object is simply assigned to the class of that single nearest neighbor.
- Naive Bayes classifiers are a family of simple probabilistic classifiers based on applying Bayes' theorem with strong (naive) independence assumptions between the features. 
- Perceptron is a type of linear classifier that makes its predictions based on a linear predictor function combining a set of weights with the feature vector. The algorithm allows for online learning, in that it processes elements in the training set one at a time.
- Desicion Tree models where the target variable can take a finite set of values are called classification trees; in these tree structures, leaves represent class labels and branches represent conjunctions of features that lead to those class labels.
- Random forests or random decision forests are an ensemble learning method for classification, regression and other tasks, that operate by constructing a multitude of decision trees (n_estimators=100) at training time and outputting the class that is the mode of the classes (classification) or mean prediction (regression) of the individual trees.

