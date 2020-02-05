MPI_Scatter can only send equal segments to each process.
MPI_Scatterv allows a varying count of data to be sent to each process with identical size.

    MPI_Scatterv(globalptr, sendcounts, displs, subarrtype,  &(local[0][0]),localgridsize_x*localgridsize_y, MPI_CHAR, 0, MPI_COMM_WORLD);
   * globalptr: global matrix at root rank otherwise NULL. it is ignored at non-root rank.
   * sendcounts: 1,1,1,1 is relevant at root but needs to be defined for all ranks.
   * displs: array of displacement
   * sendtype: same subarrtype for each rank
   * recvbuf: 
   * recvcount: local domain size
   * recvtype: basic type