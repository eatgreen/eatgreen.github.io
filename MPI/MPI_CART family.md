   call MPI_CART_CREATE(MPI_COMM_WORLD,2,dims,periodic,.false.,DECOMP_2D_COMM_CART_X,ierror)
   
      all processes make an identical call to MPI_CART_CREATE
      
      arrange the existing communicator MPI_COMM_WORLD to DECOMP_2D_COMM_CART_X like distributing the processors on the domain 
   
   call MPI_CART_COORDS(DECOMP_2D_COMM_CART_X,nrank,2,coord,ierror)
   
      my coords in the grid, NOTE THIS GRID COORESPONDS TO THE GRIDS OF PROCESS
      
   call MPI_CART_GET
   
   call MPI_CART_RANK(comm_cart,r_corrd,r_rank,ierror)
      note that **periodic condition** must be true if one wants to access the right rank of the rightest rank
      
   call MPI_CART_SUB(DECOMP_2D_COMM_CART_X,(/.true.,.false./), &
         DECOMP_2D_COMM_COL,ierror)
   call MPI_CART_SUB(DECOMP_2D_COMM_CART_X,(/.false.,.true./), &
         DECOMP_2D_COMM_ROW,ierror)