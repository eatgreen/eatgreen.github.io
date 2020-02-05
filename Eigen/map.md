double* NoiseMat;

	NoiseMat=EnVar::pseudo2dM(nx,ny,lde,rx,ry,dx,dy,n1,n2,theta);

	Eigen::Map<MatrixXd> NoiseMat_eigen(NoiseMat,nx,ny);