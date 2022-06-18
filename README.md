# ML-Task-Tree-based-models

1. What is a Decision Tree ? How does it work ?
Decision tree is a type of supervised learning algorithm (having a predefined target variable) that is mostly used in classification problems. It works for both categorical and continuous input and output variables. We split the sample into two or more homogeneous sets based on most significant splitter / differentiator in input variables.

Example
Let’s say we have a sample of 30 students with three variables Gender (Boy/ Girl), Class( IX/ X) and Height (5 to 6 ft). 15 out of these 30 play cricket in leisure time. Now, I want to create a model to predict who will play cricket during leisure period?
This is where decision tree helps, it will segregate the students based on all values of three variable and identify the variable, which creates the best homogeneous sets of students (which are heterogeneous to each other). 
In the snapshot below, you can see that variable Gender is able to identify best homogeneous sets compared to the other two variables.
![image](https://user-images.githubusercontent.com/96951127/174425976-8141bc35-a04c-468a-a4d1-3bae8fc7167c.png)

