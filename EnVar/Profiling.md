case 11x26 nCtl=32\*40

remove assignment operation in sqB and sqBT

Sgl run

with O0 60012/59938/60493 ms

with O2 1800/1817/1807 ms

mpi run

with O0 39647/39760/40651 ms

with O2 2042/2021/2003 ms

the version before optimize sqB and sqBT

sgl run

with O0 70317/70499/71285 ms

with O2 2113/2156/2113 ms

mpi run

with O0 44886/45090/47948 ms

with O2 2161/2266/2496 ms

the version before all profiling changements

Sgl run 

with O0 102745/102934 ms

with O2 4591/4656/4626 ms

mpi run

with O0 67790/66088 ms

with O2 5355/5333/5717 ms

case 41x101 nCtl=9600

the version after all profiling changements

Sgl run

with O2 122782/121570 ms

mpi run

with O2 77281/76653 ms

the version before all profiling changements

Sgl run 

with O2 397063/427916 ms

mpi run

with O2 217186/211500 ms

run1                          mpirun    sglrun
all:                          80424 ms  123305 ms
ensemble initial run model:   23859 ms   36386 ms
ensemble forecast run model:   2134 ms    1865 ms  
decomposition of Corrleation: 18737 ms   15383 ms
optimization Inner_cg       : 34868 ms   68008 ms

run2                          mpirun    sglrun
all:                          77736 ms  120746 ms
ensemble initial run model:   21745 ms   35713 ms
ensemble forecast run model:   1133 ms    1859 ms  
decomposition of Corrleation: 17685 ms   15099 ms
optimization Inner_cg       : 36111 ms   66415 ms

run3                          mpirun    sglrun
all:                          76559 ms  121722 ms
ensemble initial run model:   21562 ms   36490 ms
ensemble forecast run model:   1125 ms    1850 ms  
decomposition of Corrleation: 17532 ms   15164 ms
optimization Inner_cg       : 35302 ms   66551 ms

more detailed results on ensemble run and inner_cg
In ensemble run:         sglrun             mpirun 2 procs        mpirun 4 procs(hyperthread) 
ensemble initial total   35970 ms           21091 ms              21402 ms                             
                         set_BC  Roe_flux   set_Bc    Roe_flux    set_BC    Roe_flux          
ensemble initial         5.263s  23.89s     4.654s    13.52s      5.472s     12.689s             
forecast                 0.0036s 0.0158s    0.0031s   0.009655s   0.0047s    0.008822s         

In inner_cg:
single chip 1            1358 mius          1665 mius             1819 mius                             
MPI_Bcast loop           0                  5793 mius             30071 mius                        
Apply Hessian            64483 ms           34504 ms              32154 ms                             
MPI_Reduce               0                  2067 ms               2000 ms                         
single chip 2            8685 mius          8315 mius             9489 mius                          
Final MPI_Bcast          0                  60 mius               10237 mius                        
all inner_cg             64496 ms           36588 ms              34208 ms                          