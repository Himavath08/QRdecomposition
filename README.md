# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

3.	Obtain the Q matrix   
4.	Construct the upper triangular matrix R
    



## Program:
### Gram-Schmidt Method
```
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by:M HIMAVATH
RegisterNumber: 23010121
'''
import numpy as np
def QR_Decomposition(A):
    n,m=A.shape
    Q=np.empty((n,n))
    u=np.empty((n,n))
    u[:,0]=A[:,0]
    Q[:,0]=u[:,0]/np.linalg.norm(u[:,0])
    for i in range(1,n):
        u[:,i]=A[:,i]
        for j in range(i):
            u[:,i]-=(A[:,i]@Q[:,j])*Q[:,j]
        Q[:,i]=u[:,i]/np.linalg.norm(u[:,i])
    R=np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            R[i,j]=A[:,j]@Q[:,i]
            
    print(Q)
    print(R)
    
a = np.array(eval(input()))
QR_Decomposition(a)


```

## Output

![Screenshot 2023-12-25 063449](https://github.com/Himavath08/QRdecomposition/assets/139110631/6e3dba0a-e406-4762-8d01-179e91a6cc80)



## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
