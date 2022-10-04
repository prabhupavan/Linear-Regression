# Linear-Regression

In machine learning, linear regression is one of the simplest algorithms that you 
can apply to a dataset to model the relationships between features and labels.


![image](https://user-images.githubusercontent.com/87564129/193787679-c2102afd-8745-4824-acc5-fc87e97c895a.png)

Linear regression performs the task to predict a dependent variable value (y) based on a given independent variable (x). So, this regression technique finds out a linear relationship between x (input) and y(output). Hence, the name is Linear Regression.

Equation of Simple Linear Regression, where bo is the intercept, b1 is coefficient or slope, x is the independent variable and y is the dependent variable.

![image](https://user-images.githubusercontent.com/87564129/193789418-1ae20c58-4543-482d-83dc-e5f5c4abf152.png)


Equation of Multiple Linear Regression, where bo is the intercept, b1,b2,b3,b4…,bn are coefficients or slopes of the independent variables x1,x2,x3,x4…,xn and y is the dependent variable.

![image](https://user-images.githubusercontent.com/87564129/193789551-37a98722-76b2-4fd8-a2d3-97dc6cd48e0c.png)

A Linear Regression model’s main aim is to find the best fit linear line and the optimal values of intercept and coefficients such that the error is minimized.

![image](https://user-images.githubusercontent.com/87564129/193789742-10c6db56-8567-4f9b-b190-7cfa1f34bf21.png)

The vertical distance between the data point and the regression line is known as error or residual. Each data point has one residual and the sum of all the differences is known as the Sum of Residuals/Errors.

## Methods Of model evaluation : 

### 1. R squared or Coefficient of Determination: 
Ratio of variation to the Total Variation. The value of R squared lies between 0 to 1, the value closer to 1 the better the model.

![image](https://user-images.githubusercontent.com/87564129/193790577-1cfe2de1-e5bd-4ad1-b9d1-5b0d53386296.png)


### 2. Adjusted R squared: 
It is the improvement to R squared. The problem/drawback with R2 is that as the features increase, the value of R2 also increases which gives the illusion of a good model. So the Adjusted R2 solves the drawback of R2. It only considers the features which are important for the model and shows the real improvement of the model.

![image](https://user-images.githubusercontent.com/87564129/193790984-0bb4a47b-6d93-41f3-86da-3197262b60b5.png)

### 3. Mean Squared Error (MSE):
Mean Squared Error is the mean of the squared difference of actual vs predicted values.

![image](https://user-images.githubusercontent.com/87564129/193791198-7cbb3e8a-a943-415b-8ea8-b56f51b980e7.png)

### 4. Root Mean Squared Error (RMSE): 
It is the root of MSE i.e Root of the mean difference of Actual and Predicted values. RMSE penalizes the large errors whereas MSE doesn’t.

![image](https://user-images.githubusercontent.com/87564129/193791305-de5c46a2-3250-4fb3-a76d-5720f5e60605.png)

