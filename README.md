# Python-Case-Studies-2



## Task 1. Plot your data.


𝑥  is a variable defined in the limits between 0<𝑥<6𝜋. Define an array of 𝑥 values to span this range, and produce two data sets, 𝑦(𝑥) and 𝑧(𝑥), which are given by



![equation](https://latex.codecogs.com/gif.latex?%24%24y%28x%29%20%3D%2010%20%28x-1%29%5E4%20%5Cexp%5B-%20x%5D%24%24)

![equation](https://latex.codecogs.com/gif.latex?%24%24z%28x%29%20%3D%20%5Cxi%20%5Csin%5E2%28x%29%20%24%24)



here  𝜉  is a uniform random number between 0 and 1. Plot  𝑦(𝑥)  and  𝑧(𝑥)  versus  𝑥  (together, in one panel), making sure your plot looks professional.




## Task 2. A vector ratio function.

Define a Python function 'ratio' of two arrays  𝑔  and  ℎ :


![equation](https://latex.codecogs.com/gif.latex?%24%24%20%7B%5Crm%20ratio%7D_i%20%3D%20%7Bg_%7Bi&plus;1%7D%20-%20g_i%20%5Cover%20h_%7Bi&plus;1%7D%20-%20h_i%7D%20%24%24) 



where  𝑖=0,1,2...,𝑁−1  and  𝑁  is the number of points in the arrays. Write your function in the best Python practice, e.g., with a docstring, and also such that it prints an error but does not crash when the function cannot be executed.




## Task 3. Conditional area calculation


Write a code that performs the following tasks:

* (1) Defines a function  𝑓(𝑥,𝑦)  for  0≤𝑥≤1  and  0≤𝑦≤1 .
* (2) Method 1. Using the general python programming approach (Workshop sections 1 to 5), write a piece of code that calculates the area,  𝐴1 , inside the square  0≤𝑥,𝑦≤1  within which  𝑓(𝑥,𝑦)>0 . To do this, create a grid of  𝑥  and  𝑦  values with number of points  𝑁>1 , and use 'for' or 'while' loops to calculate the area. Your code should be general to work with any function  𝑓(𝑥,𝑦).  
* (3) Method 2. Now write another piece of code that uses Numpy for the same task. Do not use for or while loops in this case. Hint: work with a  𝑁×𝑁  matrix representing your  (𝑥,𝑦)  coordinate grid.
* (4) Calculate the execution times  𝑡1  and  𝑡2  that it takes the two codes to obtain the result. Print the results (values of both  𝐴  and  𝑡  for both tasks). Use '.format' statement. 
* (5) Now repeat the task for a range of values for N from  𝑁=3  to some very large value, such as  𝑁=10,000 . Make a plot showing how the execution times  𝑡1  and  𝑡2  depend on  𝑁 . Note: consult Section 8 of the workshop for Matplot library use, if needed. 
* (6) Based on the plots, describe approximately how the execution times depend on  𝑁  for  𝑁≫1  for method 1 and method 2. Give simple arguments that explain the obtained scaling with  𝑁.


Note that both Methods 1 and 2 should work for any function  𝑓(𝑥,𝑦).


Hints:

The following meausures the execution time:

```python
import time

start_time = time.clock()
main()
Execution_time =  time.clock() - start_time
```
where ```main()``` is the piece of the code which execution time you are measuring.
