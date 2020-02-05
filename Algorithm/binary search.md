with an array of n sorted, binary search find the index of T in array.
1. set L=0, and R=n-1
2. if L>R, the search terminates as unsuccesful
3. set m the middle of (L+R)/2, its floor
4. if $A_m$<T, L=m+1 to step 2
5. if $A_m$>T, R=m-1 to step 2
6. when $A_m$=T, search done, return m