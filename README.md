# Text-Classification-using-LSTM


We have around 18k emails , which are classified into one of 20 classes each. Our task is to predict which class a particular file belongs to.
We used 1d Conv Neural Nets for this task. 


This is a classification of emails received on a mass distribution group based on subject and hand labelled categories (supervised). The solution includes preprocessing (stopwords removal, lemmatization using nltk), features using count vectorizer and tfidf transformer. The solution is a vanilla implementation that can be used to extend from here to various text classification problems.

Things that can be tweaked to improve accuracy...

Add more parameter configurations to GridSearchCV
Increase number of K Folds used with GridSearchCV, default is 3.
Increase the dataset (current dataset is only 500 emails)
The classes in the dataset are skewed with varying proportions, the dataset can either be balanced by oversampling or the weights for each class can be adjusted if the classifier allows.
Try different classifiers or use model stacking with meta classifier
Quick Info...
Dataset: Dataset is a csv with columns 'Subject' and 'Categroy' (target variable) for about 500 emails. I'm not sharing dataset as it is from real emails taken from my inbox. Replace the dataset with your own dataset that has these two columns.

Features: Features matrix is created using a sklearn.feature_extraction.text.CountVectorizer, to get a counts matrix of all tokens and sklearn.feature_extraction.text.TfidfTransformer to normalize the count matrix.

Classifier: sklearn.linear_model.SGDClassifier

Pipeline and GridSearchCV: sklearn.pipeline.Pipeline and sklearn.model_selection.GridSearchCV are one of the best things in sklearn. Pipelines let you perform a series of steps on data without individually creating objects, handling parameters/return values and data hand off between steps. GridSearchCV helps with parameter tuning. It also performs cross validation with default 3 fold validation. Pipelines and GridSearchCV together reduce a lot of code complexity and improve readability of a solution.
