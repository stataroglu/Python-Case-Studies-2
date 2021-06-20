```python

import numpy as np

# Defining the function "ratio"
def ratio(g,h,i):
    
    """

According to the given index value, takes the difference of the next 
index value and the given index value for each array. As a result, 
returns the ratio of the calculated two differences. 

Parameters
----------
g : array
    Contains the elements of first array.
h : array
    Contains the elements of second array.
i : integer
    The given index number which is used for specifying the place of 
    subtraction of the next index value and the 'i' index value.

Returns
-------
ratio_g_over_h : float
    Returns the ratio of the two array which is the subtraction of 
    the next index value and the given index value.

Calculation Steps:
-------
* Subtraction of the next index value and the given index value
of g array.
* Subtraction of the next index value and the given index value
of h array.
* Division of the g subtraction to the h subtraction.

See Also
--------
array, integer, float, index

Notes
-----
If the numbers of the elements of the arrays are different, the number 
of the elements of the shortest array is considered for the calculation.

Due to the given index value plus 1 (x[i+1]) is used for the next index 
value which is used for the calculation, the user only can enter maximum 
index number as greatest as the number of the elements of the shorter 
array minus 2.

If the given index value is greater than the number of elements of the 
shorter array minus 2, an error is returned with following message:
"Given index number doesn't match with the length of the arrays. 
 Please try to enter a smaller index number."

Examples
--------
g = [150, 250, 375, 485, 525]
h = [100, 200, 300, 400, 500]
i = 2
>>> ratio(g,h,i)
1.1

g = [150, 250, 375, 485, 525]
h = [100, 200, 300, 400, 500]
i = 0
>>> ratio(g,h,i)
1.0

g = [150, 250, 375, 485, 525]
h = [100, 200, 300, 400, 500]
i = 4
>>> ratio(g,h,i)
"Given index number doesn't match with the length of the arrays. 
 Please try to enter a smaller index number."

g = [150, 250, 375, 485, 525, 600, 700, 800]
h = [100, 200, 300, 400, 500]
i = 4
>>> ratio(g,h,i)
"Given index number doesn't match with the lenght of the arrays. 
 Please try to enter a smaller index number."
 
g = [150, 250, 375, 485, 525, 600, 700, 800]
h = [100, 200, 300, 400, 500]
i = 3
>>> ratio(g,h,i)
0.4
    
    """
    g = g
    h = h
    err0 = "g or h is not array. Please check the inputs..."
    err1 = "The given index value (i) should be integer type. Please check your input"
    #if isinstance(g,list) == False or isinstance(h,list) == False:
    #    return err0
    if i.isdigit() == False:
        return err1
    
    i = int(i)
    maxLenght = min(len(g),len(h))
    err2 = "Given index number doesn't match with the lenght of the arrays.\n The maximum index value can be entered is {}\n\n".format(maxLenght-2)
  
    if i >= maxLenght - 1:
        return err2
    
    ratio_g_over_h = (g[i+1] - g[i])/(h[i+1] - h[i])
    return ratio_g_over_h



try:
    # Assigning the number of points in the arrays of 'g' and 'h'
    gN = input("How many points would like to have in array 'g':")
    g = np.random.randint(0, high=1000,size=int(gN))
    
    print("g array is:",g,"\n")

    
    hN = input("How many points would like to have in array 'h':")
    h = np.random.randint(0, high=1000,size=int(hN))

    print("h array is:",h,"\n")

    
    exiting = "Program has been ended."
    while True:
        # Specifying the index place with the given value by the user
        i = input("Please enter an index value to calculate of the ratio of 'g' and 'h' arrays on the given index value:")
        if i == "exit":
            print(exiting)
            break
        result = ratio(g,h,i)
        
        # If the function doesn't return the ratio, it returns an error in type of string. 
        if isinstance(result,float) == False:
            print(result)
        
        # Eventually, the ratio
        if isinstance(result,float) == True:
            print("The ratio is {}.".format(result))
            print(exiting)
            break

except:
    print("\n All the paramaters should be numeric...\n The program has been ended...")

# Docstring of the function
ratio?
