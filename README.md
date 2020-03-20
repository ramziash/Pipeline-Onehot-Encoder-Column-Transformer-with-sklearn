# Pipeline-Onehot-Encoder-Column-Transformer-with-sklearn

Previously OneHotEncoder was used in Pandas because it was super complicated with sklearn. until the new update, it is now easier and prevents data leakage if added within a pipeline.

Why is this better. 1- You do not have to make a big DF made out of get dummies in Pandas for the training of the model.

2- When new data comes Test Data, you do not need to make get dummies on it before predicting. Also if the test data has different values, it will mix the onehotencoder values they were trained on. e.g. for the below. if training data had S,C,Q in Embarked, but the test data had only S,C. It will not create the correct shape for the data column.

3- you can do grid search with both the model parameters and preprocessing.

4- in some cases, preprocessing outside Sklearn can make CV scores less reliable. e.g standardscaler, missing value imputation, or text data if you do the preprocessing before Sklearn the CV scores are possibly going to be unreliable.
