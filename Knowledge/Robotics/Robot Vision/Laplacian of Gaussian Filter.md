#Robotics #ComputerVision 

## Definition

$LoG(f(x,y)) = \Delta (f(x,y) * g(x,y))$ Where $g$ denoted the [[Filter]] function of a [[Gaussian Filter]].

The gaussian part of the operator is a [[Low-pass filter]] that smother the [[Image]] and thus reduces the intensity of structures to scale much smaller than $\sigma$.
The lapalce operator is rotation-invariant and thus responds equally to intensity changes in any mask direction. This way we can avoid using multiple masks to calculate teh strongest response at each point of the [[Image]].