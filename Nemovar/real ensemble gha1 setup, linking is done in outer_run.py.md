###restart\_file:
PATH=$MY\_RESTART\_PATH =  nemov34\_testdata/grid\_date\_outer
NAME=$MY\_RESTART\_FILE ='restart'
ln -sf $rundir/outer\_01/restart.nc -\> restart\_file (gha1\_20150531\_000000\_restart.nc)
###restart ice files: ???
###observations files:
obs\_dir=$MY\_OBSERVATION\_DATA\_PATH= nemov34\_testdata/grid\_date\_outer
obs\_list=['profiles\_01.nc','sla\_01.nc']
  ln -sf $rundir/outer\_01/obs\_list -> obs\_dir/obs\_list
profiles\_01.nc (gha1\_20150531\_20150609\_profb\_01\_fdbk.nc)
sla\_01.nc (gha1\_20150531\_20150609\_slafb\_01\_fdbk.nc)
###feedback files: /opa0/fdbk/
fdbk\_list=['profb\_01\_fdbk\_0000.nc','slafb\_01\_fdbk\_0000.nc']
###forcing files: time_dir
PATH=$MY\_TIME\_DPD\_DATA\_PATH= nemo34\_testdata\_/grid\_date\_outer
NAME=(surface boundary conditions: namsbc\_clio, namsbc\_core)
###bkgnorm\_file: optinoal
###sstnorm\_file: optional