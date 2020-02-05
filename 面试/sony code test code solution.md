The attached file is the normal vectors of sequences.

(1) Given the normal vector of the plane, calculate the yaw and pitch angle based on the normal vector;

(2) Plot the yaw/pitch angles to show the evolutionary process according to the sequences;

(3) Fit a curve to predict the angles using the least square method.

 Coding using matlab, python and C/C++(with opencv).

 Please submit a video of task (2) to show the process;

 Please submit all the matlab, python, C/C++ versions of task (1) and (3).

 In task (3), do not use the existing function. Please write the code to achieve least square method.

1) With normalized vector [x,y,z] given:
Pitch angle $\beta$：$z=sin \beta$
Yaw angle $\alpha$: $x=cos \beta cos \alpha $ and $y=cos \beta sin \alpha $
So they can be calculated using arcsin/atan functions. Exceptions can be considered for atan/atan2 where the input can not all be zeros. 

2) The yaw plot (yaw.avi) is the projection of vector on xy plane with the angle defined as the angle between the vector projection and the x-axis. The pitch plot (pitch.avi) is the projection on the plane containing both the vector and its projection on xy plane, with the view from its orthogonal, we can see the pitch angle as defined by the angle between the vector and its projection on xy plane (the xy-axis on the figure).

3) The fiting procedure is in two step. Assuming the 3d curve can be parameterized in to form $t\rightarrow(x(t),y(t),z(t))$, I checked the projection on yz plane takes a similar form as quadratic function while the projection on xy plane takes a similar form as cubic fucntion. So I decided to fit the two curve independenly considering $y$ as the independent parameter: $y\rightarrow(x(y),y,z(y))$. The least square method is quite simply with quadratic and cubic function basis and is solved by solving normal equation $\Phi^T\Phi w=\Phi^T z$ directly. With $\Phi^T\Phi$ a $3\times 3$ or $4\times 4$ matrix, its inversion is trivial (or using linear equation basic solver instead). In terms of the code, matlab and python version can be run without any extra libraries. The c++ version, nevertheless, requires the CC,CFLAGS,LDFLAGS to be set in makefile in order to get the opencv lib.

