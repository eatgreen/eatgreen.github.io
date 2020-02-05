### #!/bin/bash at the beginning of the file.
### chmod +x file in order to make it an executable

###take command line inputs
 
      while getopts ":a:b:c:" option
      do 
         case $option in 
            a) do sth
            b) do sth
            c) do sth
               \?) exit 1;;
         esac
      done   

###for loop

      for ((j=0; j<=nprocs-1; j++)); do
        if ((j<=9))
        then
                nameproc[$j]=" ${namepre}_000${j}.nc"
                echo ${nameproc[$j]}
        elif ((j<=99)) && ((j>=10))
        then
                nameproc[$j]=" ${namepre}_00${j}.nc"
                echo ${nameproc[$j]}
        elif ((j<=999)) && ((j>=100))
        then
                nameproc[$j]=" ${namepre}_0${j}.nc"
        else
                echo "procs less than 999"
                exit 1
        fi
        mppcmd+=${nameproc[$j]}
      done

(( )) is used to evaluate expression

###eval
evaluate string as command line input