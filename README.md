# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import the required libraries and read the order of the matrix along with the augmented matrix elements from the user
2. Check whether the diagonal element is zero. If not, apply forward elimination to convert the matrix into upper triangular form.
3. Perform back substitution starting from the last equation to calculate the values of unknown variables.
4. Display the solution vector X.

## Program:
```
#Program to solve a matrix using Gaussian elimination without partial pivoting.
#Developed by: K.Sanjeev Kumar
#RegisterNumber: 212225230246
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][i]==0.0:
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
    print('X%d = %0.2f '%(i,x[i]),end='')
```

## Output:
<img width="1156" height="528" alt="Screenshot 2026-05-16 123929" src="https://github.com/user-attachments/assets/ded9e624-0be0-4333-a298-01b29e7361dd" />
<img width="1158" height="568" alt="Screenshot 2026-05-16 123952" src="https://github.com/user-attachments/assets/0972faf2-89a0-48b4-97aa-33078ab006ed" />
<img width="1160" height="506" alt="Screenshot 2026-05-16 124010" src="https://github.com/user-attachments/assets/f4b51838-97a0-4e1d-b007-03bf0825c30e" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

