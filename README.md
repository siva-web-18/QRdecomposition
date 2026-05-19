# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
Intialize the matrix Q and u

The vector u and e is given by

eqn1

eqn2

eqn3

Obtain the Q matrix
eqn4

Construct the upper triangular matrix R eqn5




## Program:
### Gram-Schmidt Method
```
Program to QR decomposition using the Gram-Schmidt method
Developed by: your name: SIVA R
RegisterNumber: 212225100050
'''
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
def QR_Decomposition(A):
    a = np.array(A,dtype=float)
    m,n=A.shape
    Q=np.zeros((m,n))
    R=np.zeros((n,m))
    for j in range(n):
        v=A[:,j]
        for  i in range(j):
            R[i,j]=np.dot(Q[:,i],A[:,j])
            v=v-R[i,j]*Q[:,i]
        R[j,j]=np.linalg.norm(v)
        Q[:,j]=v/R[j,j]
    return Q,R
a=np.array(eval(input()))
Q,R=QR_Decomposition(a) 
print("The Q Matrix is\n",Q)
print("The R Matrix is\n",R) 







```

## Output
```
<img width="872" height="392" alt="math ex 8" src="https://github.com/user-attachments/assets/5b4088a2-6178-4243-ba09-014058bf146d" />

```

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
