##Compile

cdb

./fcmnmake.ksh -V -j -4 -g ORCA1_Z42

Note -V flags the compilation for variational system

##Ensemble test

Cdt textscript

./ompi_envar.ksh -x 2 -y 2 -g ORCA1_Z42

##Piano test

Cdp piano

Python piano.py 3DFGAT

In /exp/3DFGAT contains the namelist_nemovar where only changed parameters are stored.

Combining different domains and view results:

Fbcomb: in observation space
Mppcomb: in model space


bge_cov_sdv_nam: ln_ransdv_x_tru must be .FALSE. if ln_Bmod = .FALSE.

Ln_cormod must be set to .TRUE.

Nemovar.F90: if outer loop index >1, ln_enspar_read = .TRUE