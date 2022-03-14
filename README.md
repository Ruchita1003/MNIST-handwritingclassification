# MNIST-handwritingclassification
 
The project uses the MNIST dataset to train a handwritten digits recognition algorithm.

I attempt at achieving this by using two approaches i.e. building a Naive Bayes model and a Logistic Regression model. I have focused on understanding how both these model perfom and why. Analysis and inferences has been made to comprehend the nature of each model and comparision between them.

Deductions have been made on where a model performs better or makes mistakes. Further analysis explores why these misclassifications might have occurred. 

### Inferences:

• It can be observed that the Naïve Bayes model has the least precision in predicting the number 8 (precision: 0.66) and the number 9 (precision: 0.71). The Logistic Regression model has the least precision in predicting the number 8 (precision 0.88) and number 5 (precision 0.89).
•	Naïve Bayes performs well with the number 7 (precision: 0.94) and number 0 (precision 0.92). Logistic Regression Model performs well with numbers 0 and 1 (precision for both: 0.94)
•	On plotting some random predicted images, it is seen that there are some instances where the Naïve Bayes algorithm wrongly predicts the number 9 as 4, 4 as 6, 2 as 1.
Doing a similar analysis on Logistic Regression, it is seen that this model wrongly predicts the number 6 as 2 and 9 as 3.

### Why did this happen? 

Naïve Bayes calculates the probability for membership of a data-point to each class and assigns the label of the class with the highest probability. On the other hand the approach behind the Logistic Regression classification model is to find the relationship between the features and probabilities. The results can be interpreted as the likelihood that the data in the question belongs to a particular class.
Due to the nature of both these respective algorithm, Logistic Regression performs better at classifying the MNIST dataset, thus inherently having a better accuracy than Naïve Bayes.
Naïve Bayes assumes that probability of each pixel is a Gaussian distribution and the probability of each digit is equal. Another downside of Naïve Bayes is that it assumes that all the dimensions present in the data set are independent of one another i.e. each pixel is independent of other and adjacent pixels. Whereas in reality, this is not true, adjacent pixels are sort of dependent on each other depending on the stroke of the handwriting. To reduce complexity, Naïve Bayes makes an assumption that two random variables X and Y, are 
conditionally independent given a third random variable Z, formally: P(X|Y, Z)  = P(X|Y). These are some of the reasons why Naïve Bayes fails at producing the most accurate results. 
In Logistic Regression we use gradient descent and other hyperparameters which minimize the loss and help attain higher accuracy. Logistic Regression makes a prediction for the probability using a direct functional form whereas Naïve Bayes figures out how the data was generated given the result. The primary reason for this difference in performance is because Naive Bayes is a generative model and Logistic regression is a discriminative model.  Naive Bayes models the joint distribution of the feature X and target Y, and then predicts the posterior probability given as P(y|x). Whereas, Logistic regression directly models the posterior probability of P(y|x) by learning the input to output mapping by minimising the error.
