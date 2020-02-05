ihor: ns, horizontal locations of sampling points
jhor: nl,nc,ns. level, class, sample
vipt contains values cells after masking
at zero separation, ihor is filled with random points resided in vipt

```js
while horitonal sampling:
   for each level:
      for each sampling point:
         assign values to jhor
      assign vipt containing valid index at current level
      while valid and ir<irmax
         ir+=1
         generate random i
         get jpt from correpsonding vipt(i)
         for each sampling points:
            assign zero seperation random point index to ipt, there is a possibility that the zero seperation random point index ihor(is) is not a valid point on level il, this condition is controled by slog containning the mask info at level il
            compute distance between the random sampling ipt and another random point jpt
            find the class, fill jhor with jpt to correponding ic
               e.g. if jpt is located with ic=10 out of nc=20, then jhor(il,ic,is)=jpt
               ideally, the number of slog should equal nc*ns, for each ns, we have nc valid points
```

