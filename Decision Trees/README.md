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

There are many ways to tackle this problem through hyperparameter tuning.

We can set the maximum depth of our decision tree using the max_depth parameter. Each decision tree has a maximum number of levels permitted. max_depth represents this number.

Another way is to set the minimum number of samples for each spilt. It is denoted by min_samples_split. Here we specify the minimum number of samples required to do a spilt. 

min_samples_leaf – represents the minimum number of samples required to be in the leaf node. The more you increase the number, the more is the possibility of overfitting.

max_features – it helps us decide what number of features to consider when looking for the best split. There are many ways to tackle this problem through hyperparameter tuning.


### Pruning :
It is another method that can help us avoid overfitting. It helps in improving the performance of the tree by cutting the nodes or sub-nodes which are not significant. It removes the branches which have very low importance.

There are mainly 2 ways for pruning:

(i) Pre-pruning – we can stop growing the tree earlier, which means we can prune/remove/cut a node if it has low importance while growing the tree.

(ii) Post-pruning – once our tree is built to its depth, we can start pruning the nodes based on their significance.
