1. remember to check the dimension of input variable

2. because combine cdf operation is only done at root process, other process is idle. IT IS IMPORTANT TO PUT MPI_BARRIER AFTER COMBINE IN ORDER TO SYNC DIFFERENT PROCESSSES.