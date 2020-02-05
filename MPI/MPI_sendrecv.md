1. use MPI_COORDS and MPI_RANK

2. use MPI_SHIFT
   
   MPI_CART_SHIFT(comm_cart, direction, disp, rank_source, rank_dest, ierror)

   int MPI_Cart_shift(MPI_Comm comm, int direction, int disp,
             int *rank_source, int *rank_dest)
      
   when disp=1, source is from left, dest is the right   
   when disp=-1, source is from right, dest is the left   

3. MPI_sendrecv

   int MPI_Sendrecv(const void *sendbuf, int sendcount, MPI_Datatype sendtype, int dest, int sendtag, void *recvbuf, int recvcount,
   MPI_Datatype recvtype, int source, int recvtag, MPI_Comm comm,
   MPI_Status *status)
   