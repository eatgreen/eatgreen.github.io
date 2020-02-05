###blob is an N-dimensional array stored in a C-contiguous fashion
* row major
* data & diff
###layer 
* setup
* forward: input -> outptu
* backward: gradient w.r.t output -> gradient w.r.t. input/prameters
###net
* starting with data
* ending with loss function
###model format
plaintext protocol buffer
binary protocal buffer