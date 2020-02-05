# Run the test case
#
cd $rundir
+ cd /Users/yang/NEMO_RUN/nemovar34_envar_ORCA1_Z42_20090101_macportsmpi_sahaqiel_2x1
#
if  [[ $debug = "no" ]]; then
  time ${MPIEXEC} -n $nproc $exe
else
  time ${MPIEXEC} -tv -n $nproc $exe
fi

+ [[ no == no ]]
+ mpiexec -n 2 /Users/yang/NEMO_RUN/nemofcm_build/macportsmpi_sahaqiel_default/build-ens/bin/ens_inner_ORCA1_Z42.exe
      file   : namelist.nemovar                                                                 open ok
      unit   =           16
      status = OLD
      form   = FORMATTED
      access = SEQUENTIAL

      file   : namelist.nemovar                                                                 open ok
      unit   =           16
      status = OLD
      form   = FORMATTED
      access = SEQUENTIAL

  nv_mynode : mpi initialisation
  ~~~~~~
     Namelist nammpp
        mpi send type                      cn_mpi_send = I
        size in bytes of exported buffer   nn_buffer   =            0
        processor grid extent in i         jpni        =            2
        processor grid extent in j         jpnj        =            1
        number of local domains            jpnij       =            2
        avoid use of mpi_allgather at the north fold  ln_nnogather =  F
             Immediate non-blocking send (isend)
[SahaqiekProALGO:49376] *** An error occurred in MPI_Recv
[SahaqiekProALGO:49376] *** reported by process [2961965057,1]
[SahaqiekProALGO:49376] *** on communicator MPI COMMUNICATOR 3 DUP FROM 0
[SahaqiekProALGO:49376] *** MPI_ERR_TRUNCATE: message truncated
[SahaqiekProALGO:49376] *** MPI_ERRORS_ARE_FATAL (processes in this communicator will now abort,
[SahaqiekProALGO:49376] ***    and potentially your MPI job)