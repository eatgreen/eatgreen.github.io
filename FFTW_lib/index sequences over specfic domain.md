Given a rectangle domain, one wants to creat a transformation over nx*ny, one must call

pseudo2dM(noise_,ny_,nx_,1,codENS_,codENS_,1,1,ny_,nx_,0);

in which the positions of nx and ny are inversed.

pseudo2dM(noise_,ny_,nx_,nens_,codENS_,codENS_,1,1,ny_,nx_,0);

when use the noise, the positions must be nens, nx, ny.