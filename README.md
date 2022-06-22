# ML-Task-Tree-based-models

  What is a Decision Tree ? How does it work ?

Decision tree is a type of supervised learning algorithm (having a predefined target variable) that is mostly used in classification problems. It works for both categorical and continuous input and output variables. We split the sample into two or more homogeneous sets based on most significant splitter / differentiator in input variables.

Example
Let’s say we have a sample of 30 students with three variables Gender (Boy/ Girl), Class( IX/ X) and Height (5 to 6 ft). 15 out of these 30 play cricket in leisure time. Now, I want to create a model to predict who will play cricket during leisure period?

This is where decision tree helps, it will segregate the students based on all values of three variable and identify the variable, which creates the best homogeneous sets of students (which are heterogeneous to each other).

In the snapshot below, you can see that variable Gender is able to identify best homogeneous sets compared to the other two variables.
![image](https://user-images.githubusercontent.com/96951127/174425976-8141bc35-a04c-468a-a4d1-3bae8fc7167c.png)

  Types of Decision Trees

Types of decision tree is based on the type of target variable we have. It can be of two types:

1)Categorical Variable Decision Tree: Decision Tree which has categorical target variable then it called as categorical variable decision tree. Example:- In    above scenario of student problem, where the target variable was “Student will play cricket or not” i.e. YES or NO.

2)Continuous Variable Decision Tree: Decision Tree has continuous target variable then it is called as Continuous Variable Decision Tree. For example income of a person can be predicted based on their age, occupation and other information.

  IMPORTANT Terminology related to Tree based Algorithms

Root Node: It represents entire population or sample and this further gets divided into two or more homogeneous sets.

Splitting: It is a process of dividing a node into two or more sub-nodes.

Decision Node: When a sub-node splits into further sub-nodes, then it is called decision node.

Leaf/ Terminal Node: Nodes do not split is called Leaf or Terminal node.
![image](https://user-images.githubusercontent.com/96951127/174450238-87297ec5-0639-4de4-90fb-7920565d5ba8.png)

Pruning: When we remove sub-nodes of a decision node, this process is called pruning. You can say opposite process of splitting.

Branch / Sub-Tree: A sub section of entire tree is called branch or sub-tree.

Parent and Child Node: A node, which is divided into sub-nodes is called parent node of sub-nodes where as sub-nodes are the child of parent node.

  How does a tree based algorithms decide where to split?

The decision of making strategic splits heavily affects a tree’s accuracy. Decision tree splits the nodes on all available variables and then selects the split which results in most homogeneous sub-nodes.

The algorithm selection is also based on type of target variables. Let’s look at the four most commonly used algorithms in decision tree:

1. GINI
  
  It works with categorical target variable “Success” or “Failure”. It performs only Binary splits. Higher the value of Gini higher the homogeneity.
  
  Example: Referring to example where we segregate students based on whether they play cricket or not. We split population using two input variables Gender     and Class.
  
  ![image](https://user-images.githubusercontent.com/96951127/174466789-8ab6e71f-5537-4b1b-9086-b49a9148171e.png)
  
  Steps to Calculate Gini for a split

  Calculate Gini for sub-nodes, using formula sum of square of probability for success and failure (p^2+q^2).
  
  Calculate Gini for split using weighted Gini score of each node of that split.
  
  Split on Gender:

  Calculate, Gini for sub-node Female = (0.2)*(0.2)+(0.8)*(0.8)=0.68
  
  Gini for sub-node Male = (0.65)*(0.65)+(0.35)*(0.35)=0.55
  
  Calculate weighted Gini for Split Gender = (10/30)*0.68+(20/30)*0.55 = 0.59
  
  Split on Class:

  Gini for sub-node Class IX = (0.43)*(0.43)+(0.57)*(0.57)=0.51
  
  Gini for sub-node Class X = (0.56)*(0.56)+(0.44)*(0.44)=0.51
  
  Calculate weighted Gini for Split Class = (14/30)*0.51+(16/30)*0.51 = 0.51
  
  Above, you can see that Gini score for Split on Gender is higher than Split on Class, hence the node split will take place on Gender.
  
  Gini Impurity = 1 - Gini
  
2. CHI-SQUARE

It works with categorical target variable “Success” or “Failure”.

It can perform two or more splits.

Higher the value of Chi-Square higher the statistical significance of differences between sub-node and Parent node.

Chi-Square of each node is calculated using formula,  " Chi-square = ((Actual – Expected)^2 / Expected)^1/2 "
 
Steps to Calculate Chi-square for a split:

Calculate Chi-square for individual node by calculating the deviation for Success and Failure both.

Calculated Chi-square of Split using Sum of all Chi-square of success and Failure of each node of the split.

Split on Gender:

![image](https://user-images.githubusercontent.com/96951127/174467025-8e4d8d58-3bd5-4a77-8b59-0ba630de5905.png)

Split on Class:

![image](https://user-images.githubusercontent.com/96951127/174467035-0697b0ea-3735-4075-bbd7-ac8517b83e38.png)

Above, you can see that Chi-square also identify the Gender split is more significant compare to Class.

3. INFORMATION GAIN:

Which node can be described easily in the below image ?

![image](https://user-images.githubusercontent.com/96951127/174467234-dab5c891-1df0-4b8d-8eda-376e494f7482.png)

Node C requires least information as all values are similar. On the other hand, node B requires more and node A requires maximum information.

The measure of degree of disorder in sample is known as entropy. Thus, C is the most pure(homogeneous) sample and has Entropy = 0. Lesser the Entropy better it is.

Steps to calculate entropy for a split:

a)Calculate entropy of parent node

  ![image](https://user-images.githubusercontent.com/96951127/174468932-2e629d0d-a29f-4088-abac-7b04c69f6b4b.png)

  Here p and q is probability of success and failure respectively in that node.

b)Calculate entropy of each individual node of split and calculate weighted average of all sub-nodes available in split.

Example: Let’s use this method to identify best split for student example.

Entropy for parent node = -(15/30) log2 (15/30) – (15/30) log2 (15/30) = 1. Here 1 shows that it is a impure node.

Entropy for Female node = -(2/10) log2 (2/10) – (8/10) log2 (8/10) = 0.72 and for male node,  -(13/20) log2 (13/20) – (7/20) log2 (7/20) = 0.93

Entropy for split Gender = Weighted entropy of sub-nodes = (10/30)*0.72 + (20/30)*0.93 = 0.86

Entropy for Class IX node, -(6/14) log2 (6/14) – (8/14) log2 (8/14) = 0.99 and for Class X node,  -(9/16) log2 (9/16) – (7/16) log2 (7/16) = 0.99.

Entropy for split Class =  (14/30)*0.99 + (16/30)*0.99 = 0.99

Above, entropy for Split on Gender is the lowest among all, so the tree will split on Gender.

Information Gain = 1 - Entropy

4. REDUCTION IN VARIANCE

Reduction in variance is an algorithm used for continuous target variables. This algorithm uses the standard formula of variance to choose the best split. The split with lower variance is selected as the criteria to split the population.

![image](https://user-images.githubusercontent.com/96951127/174469237-f227415a-f7ca-448c-8c7a-37fc7a174d37.png)

Above X-bar is mean of the values, X is actual and n is number of values.

Steps to calculate Variance:

a)Calculate variance for each node.
b)Calculate variance for each split as weighted average of each node variance.

Example: Assign numerical value 1 for play cricket and 0 for not playing cricket. It is again observed that Gender split has least Variance, hence it will be used for splitting.

CART refers to Classification and Regression Trees.

1) CLASSIFICATION TREES
   
   A classification tree is an algorithm where the target variable is fixed or categorical. An example of a classification-type problem would be determining    who will or will not subscribe to a digital platform.
   
   Measures of impurity like entropy or Gini index are used to quantify the homogeneity of the data when it comes to classification trees.
   
2) REGRESSION TREES
   
   A regression tree refers to an algorithm where the target variable is and the algorithm is used to predict its value. As an example of a regression type problem, predicting the selling prices of a residential house, which is a continuous dependent variable.
   
When to use Classification and Regression Trees

Classification trees are used when the dataset needs to be split into classes that belong to the response variable. In many cases, the classes Yes or No. In other words, they are just two and mutually exclusive.

Regression trees, on the other hand, are used when the response variable is continuous. For instance, if the response variable is something like the price of a property or the temperature of the day, a regression tree is used.

ADVANTAGES OF DECISION TREES

a) Easy to understand.

b) Useful in data exploration. For example, we are working on a problem where we have information available in hundreds of variables, there decision tree will help to identify most significant variable.

c) It can handle both numerical and categorical variables.

DISADVANTAGES

Over fitting: Over fitting is one of the most practical difficulty for decision tree models. This problem gets solved by setting constraints on model parameters and pruning.

Not fit for continuous variables: While working with continuous numerical variables, decision tree looses information when it categorizes variables in different categories.

Overfitting can be prevented in following 2 ways:

a) Setting constraints on Tree size
b) Tree Pruning

SETTING CONSTRAINTS ON TREE BASED ALGORITHMS

![image](https://user-images.githubusercontent.com/96951127/174470428-1249193f-c866-49f6-b7de-a96598594a83.png)

1. Minimum samples for a node split

   Higher values prevent a model from learning relations which might be highly specific to the particular sample selected for a  tree.Too high values can lead to under-fitting.
   
2. Minimum samples for a terminal node (leaf)
   
   Similar to the previous constraint, too high values can lead to underfitting.
   
3. Maximum depth of tree (vertical depth)

4. Maximum number of terminal nodes

5. Maximum features to consider for split

PRUNING

In Pruning we look at a few steps ahead and make a choice.

We first make the decision tree to a large depth.

Then we start at the bottom and start removing leaves which are giving us negative returns when compared from the top.

Suppose a split is giving us a gain of say -10 (loss of 10) and then the next split on that gives us a gain of 20. 

A simple decision tree will stop at step 1 but in pruning, we will see that the overall gain is +10 and keep both leaves.

Hence, Pruning is a good technique.

If you need to build a model which is easy to explain to people, a decision tree model will always do better than a linear model. Decision tree models are even simpler to interpret than linear regression !!




