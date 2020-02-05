this routine can be used to distrubute submatrix of different row and column to different processors.

      MPI_Alltoallw(globalptr, sendcounts, senddispls, sendtypes,
                  &(local[0][0]), recvcounts, recvdispls, recvtypes, 
                  MPI_COMM_WORLD);

* globalptr:  the send buffer at EACH RANK, here equals NULL except rank 0 
* sendcounts: array of one
* senddispls: array of displacement
* sendtypes:  different for each rank
* recvbuf:    the recv buffer at EACH RANK, here equals local domain 
* recvcounts: array with 0 except at rank 0 of local size
* recvdispls: 0 for all rank
* recvtypes:  defalut type

MPI_Alltoallw is executated at each rank. 
rank=0 -> rank=0,1,2,3
rank=1 -> rank=0,1,2,3
rank=2 -> rank=0,1,2,3
rank=3 -> rank=0,1,2,3

for rank=0 -> rank=0,1,2,3 
   * globalptr contains the global matrix,
   * sendcounts 1,1,1,1 for four ranks
   * senddispls contains the right displacements
   * sendtypes  contains an array of types of different size
   * recvbuf contains the local domain submatrix
   * recvcounts: ［0]=local size, different for each rank
   * recvdispls: 0 for all rank
   * recvtypes:  defalut type
for rank=1 -> rank=0,1,2,3
   * globalptr contains NULL,
   * sendcounts 0,0,0,0 for four ranks
   * senddispls 0,0,0,0 for four ranks
   * sendtypes  basic type for four ranks
   * recvbuf has no space here
   * recvcounts: [1]＝ 0
   * recvdispls: 0 for all rank
   * recvtypes:  defalut type