# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:
### Gram-Schmidt Method
```
Program to QR decomposition using the Gram-Schmidt method
Developed by: N.lakshmi pranay
RegisterNumber: 25017706
```
import numpy as np
def gram_schmidt_qr(A):

   A=np.array(A,dtype=float)
   
   m,n=A.shape
   
   Q=np.zeros((m,n))
   
   R=np.zeros((n,n))
   
   for j in range(n):
   
        v=A[:,j]
        
        for i in range(j):
        
            R[i,j]=np.dot(Q[:,i],A[:,j])
            
            v=v-R[i,j]*Q[:,i]
            
        R[j,j]=np.linalg.norm(v)
        
        Q[:,j]=v/R[j,j]
      
   return Q,R
   
a = np.array(eval(input()))

Q,R= gram_schmidt_qr(a)

print("The Q Matrix is\n",Q)

print("The R Matrix is\n",R)

## Output
<img width="1885" height="913" alt="Screenshot 2025-12-18 213317" src="https://github.com/user-attachments/assets/46552466-9d6e-4514-b233-92e11f5d1309" />


## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
