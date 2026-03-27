# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.Read number of unknowns<br>
2.Initialize augmented matrix 'a' and solution vector 'x'<br>
3.Read coefficients into matrix 'a'<br>
4.Forward Elimination<br>
5.Convert augmented matrix into upper triangular form<br>
6.Back Substitution<br>
7.Solve variables starting from last equation<br>
8.Substitute known values to find remaining unknowns<br>


## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: SANTHOSH KUMAR SS 
RegisterNumber: 212225230251



import numpy as np
import sys

# Reading number of unknowns
n = int(input())

# Making numpy array of n x n+1 size and initializing 
# to zero for storing augmented matrix
a = np.zeros((n,n+1))

# Making numpy array of n size and initializing 
# to zero for storing solution vector
x = np.zeros(n)

# Reading augmented matrix coefficients
for i in range(n):
    for j in range(n+1):
        a[i][j] = float(input())

# Applying Gauss Elimination
for i in range(n):
    if a[i][i] == 0.0:
        sys.exit('Divide by zero detected!')
        
    for j in range(i+1, n):
        ratio = a[j][i]/a[i][i]
        
        for k in range(n+1):
            a[j][k] = a[j][k] - ratio * a[i][k]

# Back Substitution
x[n-1] = a[n-1][n]/a[n-1][n-1]

for i in range(n-2,-1,-1):
    x[i] = a[i][n]
    
    for j in range(i+1,n):
        x[i] = x[i] - a[i][j]*x[j]
    
    x[i] = x[i]/a[i][i]

# Displaying solution
for i in range(n):
    print('X%d = %0.2f' %(i,x[i]), end = ' ')

*/
```

## Output:
![gaussian elimination]()
<img width="1898" height="922" alt="image" src="https://github.com/user-attachments/assets/f099190b-aaa0-4a9c-a8b2-38c36cd1967c" />
<img width="1821" height="564" alt="image" src="https://github.com/user-attachments/assets/a4714370-0645-42cd-90e2-67556f7e0e20" />




## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

