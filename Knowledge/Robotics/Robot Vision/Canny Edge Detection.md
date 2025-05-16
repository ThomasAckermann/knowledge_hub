#ComputerVision #Robotics 

The Canny edge detector is widely used and superior to other edge detectors in terms of performance. Goal was:
- Good detection
- Good localization
- Minimal response

Canny edge detector calculates binary response.
Principles:
1. Low error rate
2. Edge point should be well detected
3. Uniqueness

## Algorithm

1. [[Gaussian Filter]]
2. Calculate of intensity gradients
3. Non-maximum suppression
4. Double threshold
5. Edge tracking with hysteresis

Calculate gradients in horizontal and vertical direction (Prewitt or Sobel)
Determine the orientation $\theta = \text{atan}(g_y, g_x)$  and the magnitude of the gradient  $M=\sqrt{g_x^2 + g_y^2}$  
Non-maximum edge thinning. All pixels that do not represent a maximum are suppressed.
-> Gradient must be local maximum. This is done with a double threshold. 
Classification of pixels into strong, weak and no edges using two thresholds $M_\text{weak}$, $M_\text{strong}$

The Canny detector uses edge tracking with hysteresis.

