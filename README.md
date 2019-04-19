
# Solving Systems of Linear Equations with NumPy - Lab

## Introduction 

Now we have gathered all the required skills needed to solve systems of linear equations. We saw why need to calculate inverses of matrices, followed by matrix multiplication to figure the values of unknown variables. 

Following exercises present some problems that can be converted into a system of linear equations. Solve the problems for the values of unknown variables. 

## Objectives
You will be able to:

* Build a system of equations from given problem by creating matrix and vectors in NumPy
* Calculate the inverse and dot-product to get the values for unknown variables
* Solve linear equations using `numpy.linalg.solve()`


## Exercise 1

A coffee shop is having a sale on coffee and tea. 

On day 1, 29 bags of coffee and 41 bags of tea was sold, giving a total of 490 dollars.

On day 2, they sold 23 bags of coffee and 41 bags of tea, for which customers paid a total of 448 dollars.  

How much does each bag cost?


```python
# Solution:

# Create Equations:

# Let x be the price of a bag of coffee and y be the price of a bag of tea. 

# 29x + 41y = 490

# 23x + 41y = 448

#  Create numpy matrices from above equations
import numpy as np
A = np.matrix([[29,41], [23,41]])
B = np.matrix([[490,448]])

# Calculate inverse of A and take the dot product
A_inv = np.linalg.inv(A)
X = A_inv.dot(B.T)
print (X)

# Verify the answer linalg.solve()
np.linalg.solve(A,B.T)

```

    [[7.]
     [7.]]





    matrix([[7.],
            [7.]])




```python
# Explain your answer in terms of prices
# bag of coffee = $7 , bag of tea = $7
```

## Exercise 2:

The cost of admission to a popular music concert was 162 dollars for 12 children and 3 adults. 

The admission was 122 dollars for 8 children and 3 adults in another music concert. 

How much was the admission for each child and adult?


```python
# Create a system of equations

# Let x be the price per child and y be the price per adult

# 12x + 3y = 162 
# 
# 8x + 3y = 122 

# Create matrices in numpy 
A = np.matrix([[12,3],[8,3]])
B = np.matrix([162,122])

# Calculate inverse of A and take the dot product
A_inv = np.linalg.inv(A)
X = A_inv.dot(B.T)
print (X)

# Verify the answer linalg.solve()
np.linalg.solve(A,B.T)
```

    [[10.]
     [14.]]





    matrix([[10.],
            [14.]])




```python
# Describe your result
# price per child = $10, price per adult = $14
```

## Exercise 3:

You want to make a certain kind of tropical punch, using bananas, oranges, and papayas. 

Suppose you don't know how many of each to put in the punch, but you know that there are seven pieces of fruit in the mix, and there are twice as many oranges as bananas. 

You also know that the seven pieces of fruit cost \$5.25, 

where bananas cost \$.50 each, oranges cost \$.75 each, and papayas cost \$1.25 each.

How many bananas, oranges and papayas would you need to make this punch ?


```python
# Create a system of equations

# Let b represent bananas, o - oranges and p - papayas. 

# b + o + p = 7

# .5b + .75o + 1.25p = 5.25

# -2b + o + p = 0

# Create matrices in numpy 
A = np.matrix([[1,1,1],[0.5, 0.75, 1.25], [-2,1,0]])
B = np.matrix([[7, 5.25, 0]])

# Calculate inverse of A and take the dot product
A_inv = np.linalg.inv(A)
X = A_inv.dot(B.T)
print (X)

# Verify the answer linalg.solve()
np.linalg.solve(A,B.T)
```

    [[2.]
     [4.]
     [1.]]





    matrix([[2.],
            [4.],
            [1.]])




```python
# Explain your answer
# bananas = 2, oranges = 4, papapayas = 1 , needed to make the punch
```

## Exercise 4

A landlord owns 3 houses, a 1-bedroom, a 2-bedroom , and a 3-bedroom house. 

The total rent he receives is 1240 dollars. 

He needs to make some repairs, where it costs 10% of the 1-bedroom house’s rent for its repairs, 20% of the 2-bedroom for its repairs, and 30% of the 3-bedroom house's rent for its repairs.  The total repair bill for all three houses was $276. 

The 3-bedroom house's rent is twice the 1-bedroom house’s rent. 

How much is the individual rent for three houses?


```python
# Create a system of equations

# Let x,y,z represent rent value for house 1,2 and 3 respectively

# x + y + z = 1240

# .1x + .2y + .3z = 276

# 2x +0y -z = 0

# Create matrices in numpy 
A = np.matrix([[1,1,1],[0.1, 0.2, 0.3], [2,0,-1]])
B = np.matrix([[1240, 276, 0]])

# Calculate inverse of A and take the dot product
A_inv = np.linalg.inv(A)
X = A_inv.dot(B.T)
print (X)

# Verify the answer linalg.solve()
np.linalg.solve(A,B.T)
```

    [[280.]
     [400.]
     [560.]]





    matrix([[280.],
            [400.],
            [560.]])




```python
# Explain your answer
# Rent: house1 = 280, house2 = 400, house3 = 560
```

## Summary
In this lab, we saw how to use Numpy to solve linear equations by taking inverses and matrix multiplication and also using numpy's `.solve()`. We shall now take these skills forward and see how we can define a simple regression problem using linear algebra and solve it with numpy, only using the skills that we have learnt so far. 
