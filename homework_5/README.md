In this patch, I grabbed different functions from the Hydra site and experimented with what worked. I layered different functions, starting with a gradient, then later adding a kaleidescope and spinning noise.

code:
```
gradient([2,4,6,2,4,68]).repeat(50,50).kaleid([3,5,7,9].fast(5))
  .modulateKaleid(osc(11,0.5,0),50)
  .modulateScale(osc(4,-0.5,0).kaleid(50).scale(0.5),15,0)
  .out(o0)
  .modulate(noise(5,0.1))
  .mult(solid(1,1,0.3))
  .out(o0)
voronoi(100,3,5)
  .modulateRotate(osc(1,0.5,0).kaleid(50).scale(0.5),15,0)
  .mult(osc(50,-0.1,8).kaleid(9))
  .out(o0)
  ```