# Camera-Calibration-and-Fundamental-Matrix-Estimation-with-RANSAC

### Introduction :
In this project, we use the geometric relationships between images taken from multiple views to compute camera positions and estimate fundamental matrices for various scenes.
With RANSAC and the normalized eight-point algorithm, we are able to match corresponding points in both images with ~100% accuracy.

### Fundamental Matrix Estimation
To compute the fundamental matrix given point correspondences $x = (u, v)$ and $x' = (u', v')$ in the left and right images, respectively
$$x'^T F x = 0$$

Then using the 8-points algotithm we start with the next matrix equation.

$$    \begin{pmatrix} u_1'u_1 &  u_1'v_1 & u_1' & v_1'v_1 & v_1' & u_1 & v_1 & 1 \\
                       \vdots &   \vdots & \vdots & \vdots & \vdots & \vdots & \vdots & \vdots \\
                       u_n'u_n &  u_n'v_n & u_n' & v_n'v_n & v_n' & u_n & v_n & 1 
        \end{pmatrix} \begin{pmatrix} f_{11} \\  
                                      f_{12} \\  
                                      f_{13} \\  
                                      f_{21} \\  
                                      f_{22} \\ 
                                      f_{23} \\  
                                      f_{31} \\   
                                      f_{32} \\  
                                      f_{33}  \end{pmatrix} = 0     $$


After solve the equiation behind , and obtein $F_orig$ then we perfom SVD on $F_orig$ to obtain

$$F_{orig} = U_f S_f V_f ^T$$

Por centering of data we are gonna 

$$\bar{u} = \frac{1}{n} \sum_{i=1}^{n} u_i \quad \bar{u}' = \frac{1}{n} \sum_{i=1}^{n} u_i'$ $$

$$\bar{v} = \frac{1}{n} \sum_{i=1}^{n} v_i  \quad \bar{v}' = \frac{1}{n} \sum_{i=1}^{n} v_i'$ $$

and 

$$s = \frac{\sqrt{2}}{\sqrt{\frac{1}{n} \sum_{i=1}^{n} (\sim{u_i^2} + \sim{v_i^2})}}$$

$$s' = \frac{\sqrt{2}}{\sqrt{\frac{1}{n} \sum_{i=1}^{n} (\sim{u_i'^2} + \sim{v_i'^2})}}$$


![89ddd83f-73ff-43fc-9dc8-c54e2b9efeb1](https://github.com/Dan-H-Muniz-Sanchez/Camera-Calibration-and-Fundamental-Matrix-Estimation-with-RANSAC/assets/147218204/927533bc-9420-4b2c-b268-246a0da09e51)
![ec58dc79-b8dc-4d18-8e1b-0747fa401295](https://github.com/Dan-H-Muniz-Sanchez/Camera-Calibration-and-Fundamental-Matrix-Estimation-with-RANSAC/assets/147218204/a88c6f9a-00af-42cd-a8e7-4b6e73e05a88)


