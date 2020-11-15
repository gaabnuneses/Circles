# Circles
How to create circles with 2 points + radius or 3 points

1. Find the center to given (x1,y1), (x2,y2) and R:

```julia
d = sqrt((x2-x1)^2+(y2-y1)^2)

if (d/2)>R
    println("Error: Distance between (x1,y1), (x2,y2) is greater than 2R")
end


s = sqrt(R^2 - (d/2)^2)
n = [-(y1-y2);x1-x2]
N = sqrt(n[1]^2+n[2]^2)
xo = (x1+x2)/2 - sign(ρ)*n[1]/N*s
yo = (y1+y2)/2 - sign(ρ)*n[2]/N*s
``` 
