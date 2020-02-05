Iterative ensemble kalman filter: Sakov et al, 2012
And Iterative ensemble kalmal smoother: Bocquet and Sakov, 2013

	• Cost function in ensemble-spanned space.
	• The iterative Gauss-Newton algorithm can be obtained from the incremental variation formulation if the control vector is spanned on the ensemble space.
	• In both IEnKF and IEnKS, the background is not changed in one cycle. If in model spaced representation (Sakov et al. 2012), analysis covariance matrix is obtained using Hessian inverse.
	• Ensemble propagation is needed in order to calculate the evolution of the sensitivity matrix, namely the evolution of the ensemble anomaly matrix. This term is projected into the observation space.
	• Nevertheless, here only the ensemble mean is updated.
	• Thus in order to obtain the analysis ensemble, in IEnKF/IEnKS, observation is not perturbed. The ensemble analysis is obtained through ensemble transform methods. 

An iterative ensemble kalman filter for multiphase fluid flow data assimilation: Gu et Oliver 2007

Here the authors used the perturbed observation approach, the repropagation of the ensemble is necessary between the iteration process in order to not only calculate the sensitivity matrix, but also calculate the innovation vector in terms of different ensemble members. The background state and its associated error covariance matrix remains unchanged.

RIP scheme: Kalnay and S.-C. Yang 2009

An iterative  procedure is included here. It is a derivation of the no cost EnKS which used the ensemble transformation matrix valid at the analysis time t2 to update the background ensemble at time t1. This is equivalent to the IEnKF with rescaling by ETM.

Basically, the RML and the IEnKF/IEnKS are similar to the methods proposed in my thesis. The former requires the whole ensemble being assimilated with different observation ensemble (with observation perturbed), two things must be calculated through the ensemble:
	1. The ensemble innovation vector must be calculated.
	2. The calculation of the propagation of ensemble perturbation matrix projected into the observation space.