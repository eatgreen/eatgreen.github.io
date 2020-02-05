1.	Pointers can be allocated in the main drivers while the array allocation can be done in the subroutines. 

2. Two types of reorthgonalizations, 

3. 	Fortran file rules:
READ and REWIND

Now the ensemble members are written in NAMELIST and they are read by ens_nam when initialization the process. 

4. keyword argument, you do not need to define them before use them.
If one argument is keyword, then the following arguments must all be keywords

5. pointer must be pointed to a pointer or a target

6. syntax like
 TYPE(ctlvec), DIMENSION(:), POINTER :: &
  & z_ctvecs    ! control vectors

 REAL(wp), DIMENSION(:), POINTER :: &
  & z_scal

Actually defines a pointer to an array, rather than an array of pointers.
  
7.	Pointer, after declaration, if want to use them (give values or other usage), must be allocated. But it can be pointed to another already allocated pointer without allocation.

8, In derived type, if a component is derived type, its allocation can be done with
Mother%child

9, undefined reference to `iargc_', add -DNOIARGCPROTO to fcflags

10.  declarations have to precede all executable statements.