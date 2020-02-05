In order to send a 2d matrix to local processor, one need to first define a derived-type containing the right size of local domain, then such type can be send to each processor using MPI_Scatter.

MPI\_TYPE\_VECTOR(count, blocklength, stride, oldtype, newtype)
* count, number of blocks/chunks, 
   * in c, this should be number of rows
   * in fortran/eigen, this should be number of columns
* blocklength, number of value in a chunk
   * in c, element of a row (number of columns)
   * in fortran/eigen, element of a column, number of rows
* stride, number of elements between the start of each block/chunk, 
   * in c, number of columns of global matrix
   * in fortran/eigen, number of rows of global matrix 
* oldtype  mpi_double for usual matrix
* newtype  