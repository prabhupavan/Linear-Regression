# Logisic Regression

Logistic regression is an example of supervised learning. It is used to calculate or predict the probability of a binary (yes/no) event occurring.
Logistic Regression is much similar to the Linear Regression except that how they are used. Linear Regression is used for solving Regression problems, whereas Logistic regression is used for solving the classification problems.

![image](https://user-images.githubusercontent.com/87564129/193796714-792747aa-9b5f-43d1-b78f-fb605058322c.png)


### sigmoid function

Logistic regression is named for the function used at the core of the method, the logistic function.

The logistic function, also called the sigmoid function was developed by statisticians to describe properties of population growth in ecology, rising quickly and maxing out at the carrying capacity of the environment. It’s an S-shaped curve that can take any real-valued number and map it into a value between 0 and 1, but never exactly at those limits.

![image](https://user-images.githubusercontent.com/87564129/193797218-95b4b458-e16f-4443-b2f9-9089a4fa015a.png)

![image](https://user-images.githubusercontent.com/87564129/193797295-5092f5cf-4cac-4cf4-98d4-ac6c5b97ea95.png)

### Decision Boundary

We expect our classifier to give us a set of outputs or classes based on probability when we pass the inputs through a prediction function and returns a probability score between 0 and 1.

![image](https://user-images.githubusercontent.com/87564129/193797731-dff77991-b02b-4237-b693-695b7f54cc93.png)

As shown in the above graph we have chosen the threshold as 0.5, if the prediction function returned a value of 0.7 then we would classify this observation as Class 1. If our prediction returned a value of 0.2 then we would classify the observation as Class 2.

### Cost Function

The cost function represents optimization objective i.e. we create a cost function and minimize it so that we can develop an accurate model with minimum error.
If we try to use the cost function of the linear regression in ‘Logistic Regression’ then it would be of no use as it would end up being a non-convex function with many local minimums, in which it would be very difficult to minimize the cost value and find the global minimum.

![image](https://user-images.githubusercontent.com/87564129/193798326-a3a205c0-d0ff-4516-8db7-acc2a36358a7.png)
