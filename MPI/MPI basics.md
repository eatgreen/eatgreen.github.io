##MPI structure

MPI\_Init
MPI\_Comm\_size
MPI\_COMM\_WORLD

MPI\_Finalize

##Blocking send and receive

MPI\_SEND & MPI\_RECV

int MPI\_Send(void \*buf, int count, MPI\_Datatype dtype, int dest, int tag, MPI\_Comm comm);

MPI\_Recv

int MPI\_Recv(void *buf, int count, MPI\_Datatype dtype, int source, int tag, MPI\_Comm comm, MPI\_Status *status);
 
 The source, tag, and communicator arguments must match those of a pending message in order for the message to be received.

 If the received message has more data than the receiving process is prepared to accept, it is an error and the program will abort.
 
MPI\_ANY\_SOURCE or MPI\_ANY\_TAG for wildcard reception.

int MPI_Get_count(MPI_Status *status, MPI_Datatype dtype, int *count); determine the size of the message received.