**Breiman, Leo. Statistical Modeling: The Two Cultures (with comments and a rejoinder by the author). Statist. Sci. 16 (2001), no. 3, 199--231. doi:10.1214/ss/1009213726. https://projecteuclid.org/euclid.ss/1009213726**


It has been nearly two decades since Breiman's article has been published, so it's an interesting POV on machine learning before it entered the mainstream (and hype cycle).

Breiman argues that data modeling is inferior because one can plug in different models (e.g. logistic, linear, Cox etc) and if they are equally "good" (based on standard goodness-of-fit tests, R2), it's nearly impossible to say which model, or underlying mechanism, is most accurate. Just as problematic as using the 5% significance level as a hard cutoff point has been the use of a narrow range of models for social science publication. Cue the replication crisis. 


_Data Modeling Culture (p. 199)_
![data modeling](/assets/img/breiman-1.png)

The need to shift away from data models to algorithmic modeling becomes more urgent in analyzing complex systems and prediction problems present in financial and medical data. The solution is to aim for predictive accuracy rather than model fit. As such, the goal shifts from building a model that fits the data well, to creating one that will generalize; it ought to predict output y well (minimize y and y'). It's another way of getting to the right model by aiming to reproduce the actual outputs, without fussing over whether the particular model reflect's nature's "black box".


_Algorithmic Modeling Culture (p. 199)_
![alg modeling](/assets/img/breiman-2.png)

The algorithmic method comes with its own challenges. Breiman outlines three:
* "Rashomon": there are multiple "good" models (similar min. error rates), each drawing a different conclusion
* Occam Dilemma: accuracy requires more complex prediction methods (random forests are great predictors but hard to interpret)
* (against) Bellman: dimensionality can be a blessing; the more predictor variables, the more information. We can increase it through feature engineering

Machine learning algorithms like neural nets, random forest, and support vectors emulate the equally or more inscrutable black boxes in nature. But Breiman's does not see this as a problem. Statistical analysis should not prioritize interpretability over predictive accuracy. He makes this point vividly clear through comparing various models on UCI toy data. The goal of statstics is to get accurate information, and therefore the focus should be on the problem and data, not the specific model favoured. 
