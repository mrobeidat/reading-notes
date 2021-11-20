# Machine Learning Intro 

## Data Science Primer 

### Bird's Eye View 

> Machine Learning ≠ Algorithms 
**Machine learning is not about algorithms.**

**Machine learning is a comprehensive approach to solving problems...** 

> What makes machine learning so special ?
**Machine learning is the practice of teaching computers how to learn patterns from data, often for making decisions or predictions.**

**For true machine learning, the computer must be able to learn patterns that it's not explicitly programmed to identify.**

> Key Terminology 
* Model : 

*a set of patterns learned from data.*

* Algorithm :

*a specific ML process used to train a model.* 

* Training data : 

*the dataset from which the algorithm learns the model.*

* Test data :
 
*a new dataset for reliably evaluating model performance.*

* Features : 

*Variables (columns) in the dataset used to train the model.*

* Target variable : 

*A specific variable you're trying to predict.*

* Observations : 

*Data points (rows) in the dataset.* 

> Machine Learning Tasks 
* A task is a specific objective for your algorithms.
    
* Algorithms can be swapped in and out, as long as you pick the right task.
    
* In fact, you should always try multiple algorithms because you most likely won't know which one will perform best for your dataset.

**Supervised Learning :** 

1. In practice, it's often used as an advanced form of predictive modeling.
2. Each observation must be labeled with a "correct answer."
3. Only then can you build a predictive model because you must tell the algorithm what's "correct" while training it (hence, "supervising" it).
4. Regression is the task for modeling continuous target variables.
5. Classification is the task for modeling categorical (a.k.a. "class") target variables.

![Supervised Learning](https://elitedatascience.com/wp-content/uploads/2017/05/weaker-penalty-noisy-conditional.png) 

**Unsupervised Learning :** 

1. In practice, it's often used either as a form of automated data analysis or automated signal extraction.
2. Unlabeled data has no predetermined "correct answer."
3. You'll allow the algorithm to directly learn patterns from the data (without "supervision").
4. Clustering is the most common unsupervised learning task, and it's for finding groups within your data.

![Unsupervised Learning](https://elitedatascience.com/wp-content/uploads/2017/03/mlmc-cluster-analysis.png)

> The 3 Elements of Great Machine Learning
* A skilled chef (human guidance)

* Fresh ingredients (clean, relevant data)

* Don't overcook it (avoid overfitting)

> The Blueprint 
**There are 5 core steps:**

* Exploratory Analysis : 

*First, "get to know" the data. This step should be quick, efficient, and decisive.*

* Data Cleaning : 

*Then, clean your data to avoid many common pitfalls. Better data beats fancier algorithms.*

* Feature Engineering :

*Next, help your algorithms "focus" on what's important by creating new features.*

* Algorithm Selection :

*Choose the best, most appropriate algorithms without wasting your time.*

* Model Training : 

*Finally, train your models. This step is pretty formulaic once you've done the first 4.*

![Bird's Eye View](https://elitedatascience.com/wp-content/uploads/2018/05/What-Goes-Into-a-Successful-Model.jpg) 

### Exploratory Analysis

> Why explore your dataset upfront ?
**The purpose of exploratory analysis is to "get to know" the dataset. Doing so upfront will make the rest of the project much smoother** 

> Plot Numerical Distributions
**a quick and dirty grid of histograms is enough to understand the distributions.** 

> Plot Categorical Distributions 
**Categorical features cannot be visualized through histograms. Instead, you can use bar plots.** 

**In particular, you'll want to look out for sparse classes, which are classes that have a very small number of observations.** 

**By the way, a "class" is simply a unique value for a categorical feature. For example, the following bar plot shows the distribution for a feature called 'exterior_walls'. So Wood Siding, Brick, and Stucco are each classes for that feature.** 

![plot](https://elitedatascience.com/wp-content/uploads/2017/06/grouping-sparse-classes-before.png)

**They tend to be problematic when building models.**

* In the best case, they don't influence the model much.
* In the worse case, they can cause the model to be overfit.

> Plot Segmentations 
**The median transaction price (middle vertical bar in the box) for Single-Family homes was much higher than that for Apartments / Condos / Townhomes.** 

**The min and max transaction prices are comparable between the two classes.** 

> Study Correlations 
**Correlation is a value between -1 and 1 that represents how closely two features move in unison. You don't need to remember the math to calculate them. Just know the following intuition:** 

* Positive correlation means that as one feature increases, the other increases. E.g. a child’s age and her height.
    
* Negative correlation means that as one feature increases, the other decreases. E.g. hours spent studying and number of parties attended.
    
* Correlations near -1 or 1 indicate a strong relationship.
    
* Those closer to 0 indicate a weak relationship.
    
* 0 indicates no relationship. 

**Correlation heatmaps help you visualize this information. Here's an example (note: all correlations were multiplied by 100):** 

![example](https://elitedatascience.com/wp-content/uploads/2017/06/correlations-heatmap-example.png) 

### Data Cleaning 

> Remove Unwanted observations
 
**Duplicate observations** 

1. Combine datasets from multiple places
2. Scrape data
3. Receive data from clients/other departments

**Irrelevant observations** 

1. if you were building a model for Single-Family homes only, you wouldn't want observations for Apartments in there.
2. This is also a great time to review your charts from Exploratory Analysis. You can look at the distribution charts for categorical features to see if there are any classes that shouldn’t be there.
3. Checking for irrelevant observations before engineering features can save you many headaches down the road.

> Fix Structural Errors 
**Structural errors are those that arise during measurement, data transfer, or other types of "poor housekeeping."** 

**For instance, you can check for typos or inconsistent capitalization. This is mostly a concern for categorical features, and you can look at your bar plots to check.** 

![example1](https://elitedatascience.com/wp-content/uploads/2017/06/typos-example-before.png) 

**As you can see:**

* 'composition' is the same as 'Composition'
* 'asphalt' should be 'Asphalt'
* 'shake-shingle' should be 'Shake Shingle'
* 'asphalt,shake-shingle' could probably just be 'Shake Shingle' as well 

**After we replace the typos and inconsistent capitalization, the class distribution becomes much cleaner:** 

![example2](https://elitedatascience.com/wp-content/uploads/2017/06/typos-example-after.png)
 
> Filter Unwanted Outliers
**Outliers can cause problems with certain types of models. For example, linear regression models are less robust to outliers than decision tree models.** 

> Handle Missing Data 
**Missing data is a deceptively tricky issue in applied machine learning.** 

**just to be clear, you cannot simply ignore missing values in your dataset. You must handle them in some way for the very practical reason that most algorithms do not accept missing values.** 

***"Common sense" is not sensible here***

**the 2 most commonly recommended ways of dealing with missing data actually suck:**

1. Dropping observations that have missing values
2. Imputing the missing values based on other observations

**Missing categorical data**

*The best way to handle missing data for categorical features is to simply label them as ’Missing’!*

1. You’re essentially adding a new class for the feature.
2. This tells the algorithm that the value was missing.
3. This also gets around the technical requirement for no missing values.

**Missing numeric data** 

*For missing numeric data, you should flag and fill the values.*

1. Flag the observation with an indicator variable of missingness.
2. Then, fill the original missing value with 0 just to meet the technical requirement of no missing values.

### Feature Engineering 

> What is Feature Engineering ? 
**Feature engineering is about creating new input features from your existing ones.**

> Infuse Domain Knowledge
**You can often engineer informative features by tapping into your expertise about the domain.** 

![example3](https://elitedatascience.com/wp-content/uploads/2017/02/zillow-housing-prices.png) 

> Create Interaction Features 
**The first of these heuristics is checking to see if you can create any interaction features that make sense. These are combinations of two or more features.**

**By the way, in some contexts, "interaction terms" must be products between two variables. In our context, interaction features can be products, sums, or differences between two features.**

> Combine Sparse Classes 
**Sparse classes (in categorical features) are those that have very few total observations. They can be problematic for certain machine learning algorithms, causing models to be overfit.**

* There's no formal rule of how many each class needs.
    
* It also depends on the size of your dataset and the number of other features you have.

* As a rule of thumb, we recommend combining classes until each one has at least ~50 observations. As with any "rule" of thumb, use this as a guideline (not actually as a rule). 

> Add Dummy Variables 
**Dummy variables are a set of binary (0 or 1) variables that each represent a single class from a categorical feature.**

**The information you represent is exactly the same, but this numeric representation allows you to pass the technical requirements for algorithms.** 

> Remove Unused Features
**Unused features are those that don’t make sense to pass into our machine learning algorithms.**

* ID columns
* Features that wouldn't be available at the time of prediction
* Other text descriptions

**Redundant features would typically be those that have been replaced by other features that you’ve added during feature engineering.** 

**After completing Data Cleaning and Feature Engineering, you'll have transformed your raw dataset into an analytical base table (ABT). We call it an "ABT" because it's what you'll be building your models on.**

**As a final tip: Not all of the features you engineer need to be winners. In fact, you’ll often find that many of them don’t improve your model. That’s fine because one highly predictive feature makes up for 10 duds.**

**The key is choosing machine learning algorithms that can automatically select the best features among many options (built-in feature selection).**

### Algorithm Selection 

> Why Linear Regression is Flawed
 
**To introduce the reasoning for some of the advanced algorithms, let's start by discussing basic linear regression. Linear regression models are very common, yet deeply flawed.** 

![example5](https://elitedatascience.com/wp-content/uploads/2017/02/noisy-sine-linear-regression.png)

**simple linear regression suffers from two major flaws:** 

1. It's prone to overfit with many input features.
2. It cannot easily express non-linear relationships.

> Regularized Regression Algos 
**Lasso Regression** 

*Lasso, or LASSO, stands for Least Absolute Shrinkage and Selection Operator.* 

* Lasso regression penalizes the absolute size of coefficients.
    
* Practically, this leads to coefficients that can be exactly 0.
    
* Thus, Lasso offers automatic feature selection because it can completely remove some features.
    
* the "strength" of the penalty should be tuned.

* A stronger penalty leads to more coefficients pushed to zero.

**Ridge Regression** 

*Ridge stands Really Intense Dangerous Grapefruit Eating (just kidding... it's just ridge).* 

* Ridge regression penalizes the squared size of coefficients.
    
* Practically, this leads to smaller coefficients, but it doesn't force them to 0.
    
* In other words, Ridge offers feature shrinkage.

* Again, the "strength" of the penalty should be tuned.
    
* A stronger penalty leads to coefficients pushed closer to zero.

**Elastic-Net** 

*Elastic-Net is a compromise between Lasso and Ridge.* 

* Elastic-Net penalizes a mix of both absolute and squared size.
    
* The ratio of the two penalty types should be tuned.
    
* The overall strength should also be tuned.

> Decision Tree Algos 
**Decision trees model data as a "tree" of hierarchical branches. They make branches until they reach "leaves" that represent predictions.** 

![example6](https://elitedatascience.com/wp-content/uploads/2017/06/Decision-Tree-Example.jpg) 

> Tree Ensembles 
**Bagging** 

*Bagging attempts to reduce the chance overfitting complex models.* 

* It trains a large number of "strong" learners in parallel.
    
* A strong learner is a model that's relatively unconstrained.
    
* Bagging then combines all the strong learners together in order to "smooth out" their predictions.

**Boosting** 

*Boosting attempts to improve the predictive flexibility of simple models.* 

* It trains a large number of "weak" learners in sequence.
    
* A weak learner is a constrained model (i.e. you could limit the max depth of each decision tree).
    
* Each one in the sequence focuses on learning from the mistakes of the one before it.
    
* Boosting then combines all the weak learners into a single strong learner.

***Key takeaway: The most effective algorithms typically offer a combination of regularization, automatic feature selection, ability to express nonlinear relationships, and/or ensembling. Those algorithms include:***

1. Lasso regression
2. Ridge regression
3. Elastic-Net
4. Random forest
5. Boosted tree

### Model Training 

> How to Train ML Models 
**professional data scientists actually spend the bulk of their time on the steps leading up to this one:** 

1. Exploring the data.
2. Cleaning the data.
3. Engineering new features.

> Split Dataset 
**data as a limited resource.**

* You can spend some of it to train your model.

* You can spend some of it to evaluate your model.
    
* But you can’t reuse the same data for both!

**If you evaluate your model on the same data you used to train it, your model could be very overfit and you wouldn’t even know! A model should be judged on its ability to predict new, unseen data.** 

**Training sets are used to fit and tune your models. Test sets are put aside as "unseen" data to evaluate your models.**

* You should always split your data before doing anything else.
    
* This is the best way to get reliable estimates of your models’ performance.
    
* After splitting your data, don’t touch your test set until you’re ready to choose your final model!

> What are Hyperparameters ?
**Model parameters**

*Model parameters are learned attributes that define individual models.*

* regression coefficients
    
* decision tree split locations
    
* They can be learned directly from the training data

**Hyperparameters** 

*Hyperparameters express "higher-level" structural settings for algorithms.*

* strength of the penalty used in regularized regression
    
* the number of trees to include in a random forest
    
* They are decided before fitting the model because they can't be learned from the data 

> What is Cross-Validation ?
***is a method for getting a reliable estimate of model performance using only your training data.*** 

**These are the steps for 10-fold cross-validation:**

1. Split your data into 10 equal parts, or "folds".
2. Train your model on 9 folds (e.g. the first 9 folds).
3. Evaluate it on the 1 remaining "hold-out" fold.
4. Perform steps (2) and (3) 10 times, each time holding out a different fold.
5. Average the performance across all 10 hold-out folds.

**The average performance across the 10 hold-out folds is your final performance estimate, also called your cross-validated score. Because you created 10 mini train/test splits, this score is usually pretty reliable.**

