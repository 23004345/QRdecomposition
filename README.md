    # Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![Screenshot 2023-12-31 140750](https://github.com/23004345/QRdecomposition/assets/138849203/3e236c3a-10a9-4fd4-9162-20a3253247b3)

    

3.	Obtain the Q matrix   
    ![Screenshot 2023-12-31 140758](https://github.com/23004345/QRdecomposition/assets/138849203/ac12d874-4aeb-4792-af34-656716d5d745)

4.	Construct the upper triangular matrix R
    ![Screenshot 2023-12-31 140805](https://github.com/23004345/QRdecomposition/assets/138849203/c71bb202-6bb6-4bcd-9859-9bf8899bcb15)




## Program:
### Gram-Schmidt Method
'''

Program to QR decomposition using the Gram-schmidt method

Developed by: Devesh s

register number:23004345

import numpy as np

def QR_Decomposition(A):

    n,m=A.shape
    
    
    Q=np.empty((n,n))
    
    u=np.empty((n,n))
    
    
    u[:, 0]=A[:, 0]
    
    Q[:, 0]=u[:, 0] / np.linalg.norm(u[:, 0])
    
    
    for i in range(1,n):
    
        
        u[:,i]=A[:, i] 
        
        for j in range(i):
        
            u[:, i] -= (A[:, i] @ Q[:, j])*Q[:, j]
            
        Q[:, i]=u[:, i] / np.linalg.norm(u[:, i])
        
        
    R=np.zeros((n,m))
    
    for i in range(n):
    
        for j in range(i,m):
        
            R[i, j]=A[:, j] @ Q[:,i]
            
    print(Q)
    
    print(R)
    
a = np.array(eval(input()))

QR_Decomposition(a)



## Output
![Screenshot 2023-12-31 141106](https://github.com/23004345/QRdecomposition/assets/138849203/7020bb92-5aec-478b-9f4d-057fd784327c)



## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
