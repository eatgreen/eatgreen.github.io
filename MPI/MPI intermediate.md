decomp_main is an instance of type DECOMP_INFO

     integer, dimension(3) :: xst, xen, xsz  ! x-pencil
                              starting/end index, size of current rank0
                              
decomp_2d_init(nx,ny,nz,p_row,p_col,periodic_bc)
               global data dimension/2D processor grid

   call MPI_COMM_RANK and MPI_COMM_SIZE
   
   call best_2d_grid for 0,0 processor
   
   create 2d catersian topology
   
   call decomp_info_init(nx,ny,nz,decomp_main)