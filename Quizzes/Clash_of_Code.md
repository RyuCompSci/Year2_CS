```.py
import math
a,b=int,input
b(math.ceil(a(b())*4*1.2**a(b())))
```

```.py
n=int(input())
x=n
for i in range(n//2-1):x*=n-(i+1)*2
print(x)
```

```.py
a,b=int,input
n,m,z=a(b()),a(b()),0
for i in range(n):s=b().split();if a(s[1])<=m<a(s[2]):z+=1
b(z)
```

```.py
a,b=int,input
n,l=a(b()),a(b())
b(10**(l-1)//n)
```

```.py
y=0
for i in input():y=y+1 if i in "069" else y+2 if i=="8" else y
print(y)
```

```.py
import java.util.*;
import java.io.*;
import java.math.*;

/**
 * Auto-generated code below aims at helping you parse
 * the standard input according to the problem statement.
 **/
class Solution {

    public static void main(String args[]) {
        Scanner in = new Scanner(System.in);
        int N = in.nextInt();
        int W = 0;
        int X = 1;

        // Write an answer using System.out.println()
        // To debug: System.err.println("Debug messages...");
        for (int i=0;i<N;i++){
            W += i+1;
            X *= (i+1);
        }
        System.out.println(X);
        System.out.println(W);
    }
}
```

```.py
import java.util.*;class Solution {public static void main(String args[]) {Scanner in = new Scanner(System.in);int c = in.nextInt();int n = 0;for (int i = 0; i < c; i++) {n += in.nextInt();}n /= c;System.out.println(n);}}
```

```.py
import sys
import math

# Auto-generated code below aims at helping you parse
# the standard input according to the problem statement.

n = int(input())
x = ""

# Write an answer using print
# To debug: print("Debug messages...", file=sys.stderr, flush=True)

for i in str(n):
    x= i+x
n-=int(x)
print(n)
```

```.py
print(sum([4 if i=="R" else 0 for i in input()]))
```
