Part 1:  What is overfitting? Why is it a special problem when working with machine learning (data-adaptive) models? How can we protect against overfitting?

Overfitting is the tendency of a model to become too specialized on the training data so that it does not generalize well. I think of overfitting as a fixation on noise, rather than a reasonable representation of the underlying predictive structure. It’s especially relevant in machine learning because we often have the goal of predicting new outcomes based on some learned structure from past examples. If our model does not do a good job of predicting new outcomes, but exceptionally well at remembering past examples... it is a glorified, buzz-wordy, database. I’d like to comment here about the antithesis to overfitting: underfitting. Underfitting is less of a special problem in machine learning tasks as I believe it shows in both training and test sets. It at least shows that your model is poor from the get-go, rather than dupe a false reality for the model builder like overfitting can do. Protecting against overfitting has a couple of strategies outlined by Geron:
1.	Simplify the model 
2.	Increase any regularization parameters
a.	I think of regularization as friction to the level of model parameter specification (almost like a learning rate). 
3.	Reduce attributes the training data (if many of the attributes contribute no predictive power, only noise)
4.	Gather more training data (if there are too few samples, the model can be overfit due to sampling bias)
5.	Reduce noise in training data (remove outliers, fix errors, etc)
To see an example of overfitting, you can run my code on the titanic dataset using a DecisionTreeClassifier with no parameters. It will achieve a train accuracy of 1.0!! AMAZING!! But if you run the cross validation, you can see that there is ~30% disparagement between the incredible 100% accuracy on the training set, and the measly 68% on the test set. Generally, we want the performance on the train set to be close to the test set. Without grid search, the best parameters for the DecisionTreeClassifer I found were: (max_features = 5, max_depth = 4). Try that out to get a 10% boost in performance and reduce overfitting by >25%.

For my shared graphic, it looks like the richer guys and gals got to the lifeboats first…
 
