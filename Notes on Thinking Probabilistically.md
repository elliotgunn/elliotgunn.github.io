*Notes on Thinking Probabilistically*

See: <br/>
Classification vs Prediction: [link](https://www.fharrell.com/post/classification/)

Damage Caused by Classification Accuracy and Other Discontinuous Improper Accuracy Scoring Rules: [link](https://www.fharrell.com/post/class-damage/)

___

ML users often use classifiers instead of risk prediction models, with many committing the error that logistic regression is a classification method.

Classification is a decision, basically a **forced choice**. The post provides some good examples of how this is unhelpful in scenarios like trying to figure out whether to market to customer X (you want to use a lift curve), or deciding when to implement a medical treatment for patients. Classifiers are best used for problems that are mechanistic, situations with high signal:noise ratio, where there is a "correct" answer. An example: patten recognition. 

Probabilistic models are best used for problems that are stochastic (random), situations with a low signal:noise ratio, where there are close calls and random outcomes. The heuristic it provides are risk estimates and confidence intervals. Examples: medical treatment, weather forecasts, credit risk, marketing. 

Highly imbalanced samples makes the inadequacy of ML clear. In brief, ML handles it by subsampling the controls to get classifiers, then adjusts it on account of the biased sample, and retrains the classifier on a new sample. A probabilistic approach, through logistic regression, handles it much more elegantly. 

Hence, when there is little variation in the outcome variable, classifiers should be discarded in favour of probabilities. It is important to choose methods by considering whether the accuracy scoring rule makes sense (i.e. correct statistical properties). This is where AI/ML practitioners without a strong background in statistics can go awry when choosing the wrong method.

This brings us to accuracy scoring rules. Accuracy scores are an essential metric for evaluating model performance. There are improper, proper, and strictly proper. 

-
-Common proper scoring rules are quadratic error measures (e.g. MSE).


Classification accuracy is both a discontinuous and improper scoring rule. 
