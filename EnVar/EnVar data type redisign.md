~~By profiling the previous version of the code, I found the performance of nested std::vector is quite poor. So I decided to change 
Data2D: vector<vectorXd> -> MatrixXd
Data3D: vector<Data2D>   -> vector<MatrixXd>

I continue use Data2D to differ from some cases using MatrixXd directly. 

Data2D row number = state dimension
Data2D col number = itobs number~~

No longer need the change by setting return reference.