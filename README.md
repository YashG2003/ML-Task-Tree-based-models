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

2)Continuous Variable Decision Tree: Decision Tree has continuous target variable then it is called as Continuous Variable Decision Tree.

Important Terminology related to Tree based Algorithms

Root Node: It represents entire population or sample and this further gets divided into two or more homogeneous sets.

Splitting: It is a process of dividing a node into two or more sub-nodes.

Decision Node: When a sub-node splits into further sub-nodes, then it is called decision node.

Leaf/ Terminal Node: Nodes do not split is called Leaf or Terminal node.
![image](https://user-images.githubusercontent.com/96951127/174450238-87297ec5-0639-4de4-90fb-7920565d5ba8.png)

Pruning: When we remove sub-nodes of a decision node, this process is called pruning. You can say opposite process of splitting.

Branch / Sub-Tree: A sub section of entire tree is called branch or sub-tree.

Parent and Child Node: A node, which is divided into sub-nodes is called parent node of sub-nodes where as sub-nodes are the child of parent node.
