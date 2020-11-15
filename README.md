# Circles
How to create circles with 2 points + radius or 3 points

![alt text](https://github.com/gaabnuneses/Circles/blob/main/2p%26R.png?raw=true)

1. Find the center O to given (x1,y1), (x2,y2) and R:

```julia
d = sqrt((x2-x1)^2+(y2-y1)^2)

if (d/2)>R
    println("Error: Distance between (x1,y1), (x2,y2) is greater than 2R")
end


s = sqrt(R^2 - (d/2)^2)
n = [-(y1-y2);x1-x2]
N = sqrt(n[1]^2+n[2]^2)
xo = (x1+x2)/2 - sign(R)*n[1]/N*s
yo = (y1+y2)/2 - sign(R)*n[2]/N*s
``` 
2. Find the center O and radius R to given (x1,y1), (x2,y2) and (x3,y3)
```julia
xo =((y2-y3)*y1^2+(-x2^2+x3^2-y2^2+y3^2)*y1+y2^2*y3+(x1^2-x3^2-y3^2)*y2+(-x1^2+x2^2)*y3)
xo = xo/((-2*x2+2*x3)*y1+(2*x1-2*x3)*y2-2*y3*(x1-x2))
yo = ((-x2+x3)*x1^2+(x2^2-x3^2+y2^2-y3^2)*x1-x2^2*x3+(x3^2-y1^2+y3^2)*x2+x3*(y1^2-y2^2))
yo = yo/((2*y2-2*y3)*x1+(-2*y1+2*y3)*x2+2*x3*(y1-y2))
R = (x1^2-2*x1*x3+x3^2+(y1-y3)^2)*(x2^2-2*x3*x2+x3^2+(y2-y3)^2)*(x1^2-2*x1*x2+x2^2+(y1-y2)^2)
R = sqrt(R/(4*((y2-y3)*x1+(-y1+y3)*x2+x3*(y1-y2))^2))
``` 
