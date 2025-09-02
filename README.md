# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1.Read the number of equations n and create an n x (n+1) augmented matrix.
Input all coefficients and constants, and initia 

2.Convert the matrix into upper triangular form by eliminating variables below each pivot.
Check for zero pivots to avoid division by zero and update rows using the elimination ratio. 

3.Solve for unknowns starting from the last row upwards.
Subtract contributions of already found variables and divide by the pivot element. 

4.Print the solution vector x with appropriate formatting.
Each unknown X_i is displayed with two decimal places. 

## Program:
```
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: KARTHIK PADMANABAN R 
RegisterNumber: 212224110029
import numpy as np 
import sys 
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range (n):
    if a[i][j]==0.0:
        sys.exit('Divide by zero detected!')
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f ' %(i,x[i]),end='')
```

## Output:
<img width="1352" height="889" alt="Screenshot 2025-09-02 143703" src="https://github.com/user-attachments/assets/b6fa1dea-f696-47a0-8a94-d4b993d36318" />

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

