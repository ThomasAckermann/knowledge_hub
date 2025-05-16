#Robotics #ComputerVision 


Previous classic [[Pinhole camera model]] is too simple for applications (lens distortion, imperfect calibration, or complex imaging conditions)
Extension of the model needed:
- Independent focal lengths $f_x$ and $f_y$ in $u$ and $y$ direction
- Main point ($c_x, c_y$) is not identical to the origin of the [[Camera coordinate system]]
- Projection from camera to [[Image]] coordinates can now be extended to the affine transformation $(u,v) = (c_x, c_y) + \frac{1}{z} (f_x \cdot x, f_y \cdot y)$ 
- One can also write this as a matrix product.
- $\begin{pmatrix} u \cdot z \\ v \cdot z \\ z \end{pmatrix} =\begin{pmatrix} f_x & 0 & c_x \\ 0 & f_y & c_y \\ 0 & 0 & 1 \end{pmatrix}\begin{pmatrix} x \\ y \\ z \end{pmatrix}$  
This matrix $K$ is called the [[Calibration Matrix]] of the camera.