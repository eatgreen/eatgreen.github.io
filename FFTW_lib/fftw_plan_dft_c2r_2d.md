###fftw\_plan fftw\_plan\_dft\_r2c\_2d
(int n0, int n1, double *in, fftw_complex *out, unsigned flags);

n is the logical size of the array, and the consequences of this on the the format
of the complex arrays deserve careful attention. Suppose that the real data has dimensions
n0 × n1 × n2 × · · · × nd−1 (in row-major order). Then, after an r2c transform, the output
is an n0 × n1 × n2 × · · · × (nd−1/2 + 1) array of fftw_complex values in row-major order,
corresponding to slightly over half of the output of the corresponding complex DFT. (The
division is rounded down.) The ordering of the data is otherwise exactly the same as in the
complex-DFT case.