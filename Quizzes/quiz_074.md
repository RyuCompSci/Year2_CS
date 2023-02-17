```.py
x=0
for i in range(int(input())):
    n=int(input())
    x+=n*3 if n%2==0 else n*5
print(x)

j=lambda:int(input())
print(j()+j()*(j()-1))

i,j=int,input
j(i(j())+i(j())*(i(j())-1))
```
