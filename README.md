Harshad 
SEL69
Date:-19/03/2025

"Program for Newton Forward Interpolation Method"

import numpy as np

n=int(input("Enter no. of elements/observations=\t"))

NF=np.array([[0 for i in range(n+1)]for j in range(n)])

for i in range (n):
    print("Enter the value of x%d="%i)
    NF[i][0]=float(input())
    print("Enter the value of x%d="%i)
    NF[i][1]=float(input())

nn=n-1    
j=2
while(j<=n):
    i=0
    while(i<nn):
        NF[i][j]=NF[i+1][j-1]-NF[i][j-1]
        i=i+1
    nn=nn-1
    j=j+1
    
h=NF[1][0]-NF[0][0]

x=float(input("Enter the value of x for which the y is calculated=\t"))

u=(x-NF[0][0])/h

r=0
for i in range(n):  
    if (x>NF[i][0]):
        r=i

y=NF[r][1]+u*NF[r][2]+(u)*(u-1)/2*NF[r][3]+u*(u-1)*(u-2)/6*NF[r][4]+u*(u-1)*(u-2)*(u-3)/24*NF[r][5]+u*(u-1)*(u-2)*(u-3)*(u-4)/120*NF[r][6]  

print("The value of y is =",y)       
        

OUTPUT:-
Enter no. of elements/observations(Not more than 6)=	6
Enter the value of x0=
0
Enter the value of y0=
0
Enter the value of x1=
2
Enter the value of y1=
33
Enter the value of x2=
4
Enter the value of y2=
55
Enter the value of x3=
6
Enter the value of y3=
70
Enter the value of x4=
8
Enter the value of y4=
80
Enter the value of x5=
10
Enter the value of y5=
85
Enter the value of x for which the y is calculated=	1
The value of y is = 18.203125
