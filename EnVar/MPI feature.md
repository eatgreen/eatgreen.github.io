The principle, each process executes one instance of the code on decomposed domain.

###The mpitest.cpp is used to test mpi features
1. Instantialize mpi_dom of class MpiDom
   accept global domain values (nx,ny,nxobs,nyobs,proc_ni,proc_nj)
2. Call mpi_dom.Init_domain in otder to get local index for each local domain
   we only use four rank for the moment, we need to determine for each domain the size and the index corresponding to the global domain.