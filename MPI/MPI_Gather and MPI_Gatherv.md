each process send ixloc to root, received by ixloc_array

MPI_Gather(&ix_loc, 1, MPI_INT, ix_loc_array, 1, MPI_INT, 0, MPI_COMM_WORLD);

MPI_Gatherv allows a varying count of data from each process.