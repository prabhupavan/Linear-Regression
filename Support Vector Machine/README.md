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

![image](https://user-images.githubusercontent.com/87564129/195622445-a8b54478-7dd4-4fed-851a-8b91bc1d1ed2.png)
