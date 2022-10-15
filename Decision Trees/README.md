# Decision Tree

A decision tree is a type of supervised machine learning used to categorize or make predictions based on how a previous set of questions were answered.Decision trees can be used for classification as well as regression problems. The name itself suggests that it uses a flowchart like a tree structure to show the predictions that result from a series of feature-based splits.
Decision trees imitate human thinking, so it’s generally easy for data scientists to understand and interpret the results. It starts with a root node and ends with a decision made by leaves.

![image](https://user-images.githubusercontent.com/87564129/195990383-9dd7c9c0-86fa-4537-9737-8ab06e8cd633.png)

### Root Nodes : 
It is the node present at the beginning of a decision tree from this node the population starts dividing according to various features.

### Decision Nodes :
The nodes we get after splitting the root nodes are called Decision Node

### Leaf Nodes :
The nodes where further splitting is not possible are called leaf nodes or terminal nodes

### Sub-tree :
Just like a small portion of a graph is called sub-graph similarly a sub-section of this decision tree is called sub-tree.

### Pruning : 
It is nothing but cutting down some nodes to stop overfitting.


![image](https://user-images.githubusercontent.com/87564129/195990509-96c10ac1-f158-432e-875a-2612c7d5f097.png)

A decision tree resembles, well, a tree. The base of the tree is the root node. From the root node flows a series of decision nodes that depict decisions to be made. From the decision nodes are leaf nodes that represent the consequences of those decisions. Each decision node represents a question or split point, and the leaf nodes that stem from a decision node represent the possible answers. Leaf nodes sprout from decision nodes similar to how a leaf sprouts on a tree branch. This is why we call each subsection of a decision tree a “branch.” 


### Entropy :
Entropy is nothing but the uncertainty in our dataset or measure of disorder. Let me try to explain this with the help of an example.
The Mathematical formula for Entropy is as follows -

![image](https://user-images.githubusercontent.com/87564129/195990847-3419d595-3c5a-4da6-9bf0-0e21174365ff.png)

Where ‘Pi’ is simply the frequentist probability of an element/class ‘i’ in our data. For simplicity’s sake let’s say we only have two classes , a positive class and a negative class. Therefore ‘i’ here could be either + or (-). So if we had a total of 100 data points in our dataset with 30 belonging to the positive class and 70 belonging to the negative class then ‘P+’ would be 3/10 and ‘P-’ would be 7/10. Pretty straightforward.

If we were to calculate the entropy of the classes in the above example using the formula above. Here’s what we would get.

![image](https://user-images.githubusercontent.com/87564129/195990920-74e659f0-b144-4cd2-98cd-b8b589494d47.png)

The entropy here is approximately 0.88. This is considered a high entropy , a high level of disorder ( meaning low level of purity). Entropy is measured between 0 and 1.

![image](https://user-images.githubusercontent.com/87564129/195990957-bb367fab-28f9-4f9f-a7d3-5ea32adf71c0.png)


### Information Gain :
Information gain measures the reduction of uncertainty given some feature and it is also a deciding factor for which attribute should be selected as a decision node or root node.
It is the measure of how much information a feature provides about a class. Information gain helps to determine the order of attributes in the nodes of a decision tree.

![image](https://user-images.githubusercontent.com/87564129/195991065-b5122e93-3594-4c35-bc03-aa726bf1037d.png)

It is just the entropy of the full dataset minus the entropy of the dataset given some feature.

It can help us determine the quality of splitting, as we shall soon see.

### When to stop splitting ?

Usually, real-world datasets have a large number of features, which will result in a large number of splits, which in turn gives a huge tree. Such trees take time to build and can lead to overfitting. That means the tree will give very good accuracy on the training dataset but will give bad accuracy in test data.
This article was published as a part of the Data Science Blogathon

Decision tree algorithm
Introduction
Till now we have learned about linear regression, logistic regression, and they were pretty hard to understand. Let’s now start with Decision tree’s and I assure you this is probably the easiest algorithm in Machine Learning. There’s not much mathematics involved here. Since it is very easy to use and interpret it is one of the most widely used and practical methods used in Machine Learning.

Contents
1. What is a Decision Tree?

2. Example of a Decision Tree

3. Entropy

4. Information Gain

5. When to stop Splitting?

6. How to stop overfitting?

max_depth
min_samples_split
min_samples_leaf
max_features
7. Pruning

Post-pruning
Pre-pruning
8. Endnotes

What is a Decision Tree?
It is a tool that has applications spanning several different areas. Decision trees can be used for classification as well as regression problems. The name itself suggests that it uses a flowchart like a tree structure to show the predictions that result from a series of feature-based splits. It starts with a root node and ends with a decision made by leaves.
what is Decision tree 
Image 1

 

Before learning more about decision trees let’s get familiar with some of the terminologies.
Root Nodes – It is the node present at the beginning of a decision tree from this node the population starts dividing according to various features.

Decision Nodes – the nodes we get after splitting the root nodes are called Decision Node

Leaf Nodes – the nodes where further splitting is not possible are called leaf nodes or terminal nodes

Sub-tree – just like a small portion of a graph is called sub-graph similarly a sub-section of this decision tree is called sub-tree.

Pruning – is nothing but cutting down some nodes to stop overfitting.

branch Decision tree algorithm
Image 2

Example of a decision tree
Let’s understand decision trees with the help of an example.

example data
Image 3

Decision trees are upside down which means the root is at the top and then this root is split into various several nodes. Decision trees are nothing but a bunch of if-else statements in layman terms. It checks if the condition is true and if it is then it goes to the next node attached to that decision.

In the below diagram the tree will first ask what is the weather? Is it sunny, cloudy, or rainy? If yes then it will go to the next feature which is humidity and wind. It will again check if there is a strong wind or weak, if it’s a weak wind and it’s rainy then the person may go and play.

Decision tree example
Image 4

Did you notice anything in the above flowchart? We see that if the weather is cloudy then we must go to play. Why didn’t it split more? Why did it stop there?

To answer this question, we need to know about few more concepts like entropy, information gain, and Gini index. But in simple terms, I can say here that the output for the training dataset is always yes for cloudy weather, since there is no disorderliness here we don’t need to split the node further.

The goal of machine learning is to decrease uncertainty or disorders from the dataset and for this, we use decision trees.

Now you must be thinking how do I know what should be the root node? what should be the decision node? when should I stop splitting? To decide this, there is a metric called “Entropy” which is the amount of uncertainty in the dataset.

 

Entropy
Entropy is nothing but the uncertainty in our dataset or measure of disorder. Let me try to explain this with the help of an example.

Suppose you have a group of friends who decides which movie they can watch together on Sunday. There are 2 choices for movies, one is “Lucy” and the second is “Titanic” and now everyone has to tell their choice. After everyone gives their answer we see that “Lucy” gets 4 votes and “Titanic” gets 5 votes. Which movie do we watch now? Isn’t it hard to choose 1 movie now because the votes for both the movies are somewhat equal.

This is exactly what we call disorderness, there is an equal number of votes for both the movies, and we can’t really decide which movie we should watch. It would have been much easier if the votes for “Lucy” were 8 and for “Titanic” it was 2. Here we could easily say that the majority of votes are for “Lucy” hence everyone will be watching this movie.

In a decision tree, the output is mostly “yes” or “no”

The formula for Entropy is shown below:

entropy Decision tree algorithm
Here p+ is the probability of positive class

p– is the probability of negative class

S is the subset of the training example

 

How do Decision Trees use Entropy?
Now we know what entropy is and what is its formula, Next, we need to know that how exactly does it work in this algorithm.

Entropy basically measures the impurity of a node. Impurity is the degree of randomness; it tells how random our data is. A pure sub-split means that either you should be getting “yes”, or you should be getting “no”.

Suppose a feature has 8 “yes” and 4 “no” initially, after the first split the left node gets 5 ‘yes’ and 2 ‘no’ whereas right node gets 3 ‘yes’ and 2 ‘no’.

We see here the split is not pure, why? Because we can still see some negative classes in both the nodes. In order to make a decision tree, we need to calculate the impurity of each split, and when the purity is 100%, we make it as a leaf node.

To check the impurity of feature 2 and feature 3 we will take the help for Entropy formula.

feature 2
Image Source: Author

entropy calculation
For feature 3,

feature 3 Decision tree algorithm
We can clearly see from the tree itself that left node has low entropy or more purity than right node since left node has a greater number of “yes” and it is easy to decide here.

Always remember that the higher the Entropy, the lower will be the purity and the higher will be the impurity.

As mentioned earlier the goal of machine learning is to decrease the uncertainty or impurity in the dataset, here by using the entropy we are getting the impurity of a particular node, we don’t know if the parent entropy or the entropy of a particular node has decreased or not.

For this, we bring a new metric called “Information gain” which tells us how much the parent entropy has decreased after splitting it with some feature.

Information Gain
Information gain measures the reduction of uncertainty given some feature and it is also a deciding factor for which attribute should be selected as a decision node or root node.

information gain Decision tree algorithm
It is just entropy of the full dataset – entropy of the dataset given some feature.

To understand this better let’s consider an example:
Suppose our entire population has a total of 30 instances. The dataset is to predict whether the person will go to the gym or not. Let’s say 16 people go to the gym and 14 people don’t

Now we have two features to predict whether he/she will go to the gym or not.

Feature 1 is “Energy” which takes two values “high” and “low”

Feature 2 is “Motivation” which takes 3 values “No motivation”, “Neutral” and “Highly motivated”.

Let’s see how our decision tree will be made using these 2 features. We’ll use information gain to decide which feature should be the root node and which feature should be placed after the split.

feature1 energy
Image Source: Author

Let’s calculate the entropy:

calculate the entropy | Decision tree algorithm
To see the weighted average of entropy of each node we will do as follows:

entropy weighted average
Now we have the value of E(Parent) and E(Parent|Energy), information gain will be:

information gain example
Our parent entropy was near 0.99 and after looking at this value of information gain, we can say that the entropy of the dataset will decrease by 0.37 if we make “Energy” as our root node.

Similarly, we will do this with the other feature “Motivation” and calculate its information gain.

feature2 | Decision tree algorithm
Image Source: Author

Let’s calculate the entropy here:

feature 2 entropy
To see the weighted average of entropy of each node we will do as follows:

weighted entropy 
Now we have the value of E(Parent) and E(Parent|Motivation), information gain will be:

feature2 information gain
We now see that the “Energy” feature gives more reduction which is 0.37 than the “Motivation” feature. Hence we will select the feature which has the highest information gain and then split the node based on that feature.

final splitting | Decision tree algorithm
Image Source: Author
In this example “Energy” will be our root node and we’ll do the same for sub-nodes. Here we can see that when the energy is “high” the entropy is low and hence we can say a person will definitely go to the gym if he has high energy, but what if the energy is low? We will again split the node based on the new feature which is “Motivation”.

When to stop splitting?
You must be asking this question to yourself that when do we stop growing our tree? Usually, real-world datasets have a large number of features, which will result in a large number of splits, which in turn gives a huge tree. Such trees take time to build and can lead to overfitting. That means the tree will give very good accuracy on the training dataset but will give bad accuracy in test data.

There are many ways to tackle this problem through hyperparameter tuning.

We can set the maximum depth of our decision tree using the max_depth parameter. Each decision tree has a maximum number of levels permitted. max_depth represents this number.

Another way is to set the minimum number of samples for each spilt. It is denoted by min_samples_split. Here we specify the minimum number of samples required to do a spilt. 

min_samples_leaf – represents the minimum number of samples required to be in the leaf node. The more you increase the number, the more is the possibility of overfitting.

max_features – it helps us decide what number of features to consider when looking for the best split.
