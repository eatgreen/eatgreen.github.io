input, various measurements
output, robot pose and stationary object map

###compounding
**head-to-tail** relationship
sensor w.r.t the coordinate
moving object w.r.t the sensor  => moving object w.r.t the coordinate

**the inverse relationship** 
the coordinate w.r.t the robot pose

**tail-to-tail** relationship
location of moving object in the robot frame
Given sensor w.r.t coordinate
      moving object w.r.t coordinate => moving object w.r.t sensor

###SLAM
\[p(x_k, M| u_{1,k},z_{0,k})\]
$x_k$ true pose at k
$u_k$ motion sensor measurements, evaluate the sensor's motion information
$z_k$ perception sensor measurements, evaluate the sensor's location information
M stochastic stationary object map
\[p(x_k, M| u_{1,k},z_{0,k}) 
= p(z_k|x_k,M) \int p(x_k|x_{k-1},u_k)p(x_{k-1},M|u_{1,k-1},z_{0,k-1})dx_{k-1}
\]
$p(x_k, M| u_{1,k},z_{0,k})$ the posterior at k
$p(z_k|x_k,M)$ update, perception model
$p(x_k|x_{k-1},u_k)$ motion model
$\int p(x_k|x_{k-1},u_k)p(x_{k-1},M|u_{1,k-1},z_{0,k-1})dx_{k-1}$ prior model

**calculation procedures**
1. initialization
   state vector: $x_k^S=[x_k, M]^T$
   perception model: $z_k=h(x_k,M)+w_k$ h is tail-to-tail relationship of the robot and the map.
   compound measurements to the robot pose state yielding the mean and its covariance, 

   \[\Sigma_{x^S}=\pmatrix{\Sigma_{xx} & \Sigma_{xm} \\
   \Sigma^T_{xm} & \Sigma_{mm}}
   \]
   is the location uncertainty matrix associated with the robot ans the landmarks.

   Here we resolve $p(x_{k-1},M|u_{1,k-1},z_{0,k-1})$
2. prediction
   resolve motion model $p(x_k|x_{k-1},u_k)$ based on the motion obs $u_k$.
   The covariance matrix is propagated as well.
3. data association
   associate new location measurements to the stationary object map. One needs to define if a new observation belong to some landmarks.
4. update
   state and state covariance are updated through kalman filter.
   \[x^S=x^S+K(z-\hat{z})\]
where $\hat{z}$ is measurement location and $z$ is obtained through compound tail-to-tail relationship.
   \[z=\oplus(\ominus(\mu_x),\mu_m)\]
suggesting the relative location of x and m which is consistent with the observed value $\hat{z}$.

   The covariance $\Sigma_{x^S}$ is updated by
   \[\Sigma_{x^S}=\Sigma_{x^S}-K\nabla_h\Sigma_{x^S}
   \]