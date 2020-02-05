# 11/2018 case 1
[//]: # ({{TOC}})
|Observations Configurations | Reduced | Toy |
|:--|:--|:--|
|Synthetic velocity grid | 73x73x6 | 17x17x3 |
|Particle number | 7000, 8500  | 500 |
|Time separation | 0.5 | 0.5
|Image size      | 256x256   | |
|ppp level       | 0.1       ||

|Evaluation grid | | | |
|:--|:--|
|Reconstructed grid |  5x5x2 | 10x10x2 | 19x19x2 |
|Overlapping ratio 0.5 | 9x9x3 | 19x19x3 | 37x37x3 |
|Overlapping ratio 0.25 | 17x17x5 | 37x37x5 | 73x73x5 |

## Evaluation
- Particle images are created by projecting particles in object space transporting by _synthetic velocity grid_.
- We check horizontal velocity for difference **depth z**.
- Reference velocity is obtained by interpolating the synthetic velocity on grid 73x73x6 to reconstructed coarser grid.
## 17x17x3 Toy model with 500 particles
### Results 17x17x5 overlap 75%
- velocity 
	![](/17173_17175_velo.png)
- error
	![](/Users/yin.yang/Dropbox/TechniqueNotes/Slides/17173_17175_err.png)
## 73x73x6 Reduced model
### Results 5x5x2 no overlap. 7000/(5\*5\*2)=140
#### Results 17x17x5 overlap 75%
- velocity
	![](/Users/yin.yang/Dropbox/TechniqueNotes/Slides/73736_17175_velo.png)
- error 
	![](/Users/yin.yang/Dropbox/TechniqueNotes/Slides/73736_17175_err.png)
#### Remarks
1. The result is too coarse to evaluate.	
2. Only one mean velocity is computed for one IB, if IB is too big, accuracy is compromised.
### Results 10x10x2 no overlap. 7000/(10\*10\*2)=35
[//]: # (- velocity)
[//]: # (	![](/Users/yin.yang/Dropbox/TechniqueNotes/Slides/73736_10102_velo.png))
[//]: # (- error)
[//]: # (	![](/Users/yin.yang/Dropbox/TechniqueNotes/Slides/73736_10102_err.png))
	
#### Results 19x19x3 overlap 50%
- velocity
	![](/Users/yin.yang/Dropbox/TechniqueNotes/Slides/73736_19193_velo.png)
- error
	![](/Users/yin.yang/Dropbox/TechniqueNotes/Slides/73736_19193_err.png)
	
#### Results 37x37x5 overlap 75%
- velocity
	![](/Users/yin.yang/Dropbox/TechniqueNotes/Slides/73736_37375_velo.png)
- error
	![](/Users/yin.yang/Dropbox/TechniqueNotes/Slides/73736_37375_err.png)
	
### Results 19x19x2 no overlap, 7000, 7000/(19\*19\*2)=9.69
- velocity
	![](/Users/yin.yang/Dropbox/TechniqueNotes/Slides/73736_19192_velo.png)
- error
	![](/Users/yin.yang/Dropbox/TechniqueNotes/Slides/73736_19192_err.png)
#### Remarks
1. Outliner presented, not enough particles for certain IB.
### Results 19x19x2 no overlap, 8500, 8500/(19\*19\*2)=11.77
- velocity
	![](/Users/yin.yang/Dropbox/TechniqueNotes/Slides/73736_19192_8500_velo.png)
- error
	![](/Users/yin.yang/Dropbox/TechniqueNotes/Slides/73736_19192_8500_err.png)
	
#### Results 37x37x3 overlap 50%, 8500
- velocity
	![](/Users/yin.yang/Dropbox/TechniqueNotes/Slides/73736_37373_8500_velo.png)
- error
	![](/Users/yin.yang/Dropbox/TechniqueNotes/Slides/73736_37373_8500_err.png)
	
#### Results 73x73x5 overlap 75%, 8500
- velocity 
	![](/Users/yin.yang/Dropbox/TechniqueNotes/Slides/73736_73735_8500_velo.png)
- error 
	![](/Users/yin.yang/Dropbox/TechniqueNotes/Slides/73736_73735_8500_err.png)