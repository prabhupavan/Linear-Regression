# Support Vector Machine

SVM or Support Vector Machine is a linear model for classification and regression problems. It can solve linear and non-linear problems and work well for many practical problems. The idea of SVM is simple: The algorithm creates a line or a hyperplane which separates the data into classes.

The main concept of SVM is to plot each 
data item as a point in n-dimensional space with the value of each feature being the value 
of a particular coordinate. Here n would be the features we would have.

At first approximation what SVMs do is to find a separating line(or hyperplane) between data of two classes. SVM is an algorithm that takes the data as an input and outputs a line that separates those classes if possible.

![image](https://user-images.githubusercontent.com/87564129/195621612-361c08c0-96cc-4e20-9d91-f85fa7b9fa64.png)

In the above diagram, we have two features. Hence, we first need to plot these two 
variables in two dimensional space where each point has two co-ordinates, called support 
vectors. The line splits the data into two different classified groups. This line would be the 
classifier.

Here, we are going to build an SVM classifier by using scikit-learn. Scikit-learn library has the sklearn.svm module and provides sklearn.svm.svc for classification.

### SVM’s way to find the best line:
According to the SVM algorithm we find the points closest to the line from both the classes.These points are called support vectors. Now, we compute the distance between the line and the support vectors. This distance is called the margin. Our goal is to maximize the margin. The hyperplane for which the margin is maximum is the optimal hyperplane.

![image](https://user-images.githubusercontent.com/87564129/195622815-3cd025a9-c567-42c9-9af3-6b9dcc17790c.png)

### Kernal:
It is a technique used by SVM. Basically these are the functions which take low-dimensional 
input space and transform it to a higher dimensional space. It converts non-separable
problem to separable problem. The kernel function can be any one among linear, 
polynomial, rbf and sigmoid. In this example, we will use the linear kernel.

![image](https://user-images.githubusercontent.com/87564129/195625018-5be7212e-aecc-4f05-ad1d-a80114d2efcc.png)


### Hyperplane:
There can be multiple lines/decision boundaries to segregate the classes in n-dimensional space, but we need to find out the best decision boundary that helps to classify the data points. This best boundary is known as the hyperplane of SVM.

The dimensions of the hyperplane depend on the features present in the dataset, which means if there are 2 features (as shown in image), then hyperplane will be a straight line. And if there are 3 features, then hyperplane will be a 2-dimension plane.

![image](https://user-images.githubusercontent.com/87564129/195624720-d8e3aedc-9a2e-4ca0-a3f5-b1f75f3270bb.png)


### Support Vectors:
The data points or vectors that are the closest to the hyperplane and which affect the position of the hyperplane are termed as Support Vector. Since these vectors support the hyperplane, hence called a Support vector.
