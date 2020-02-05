## Goals of internship
- Implementing 3D PTV algorithm in ENS-PTV (LAPIV) code. The code should be able to produce autonomously the Lagrangian data from particle images.
- Combining the Lagrangian data into the data assimilation system.
### March
- General Goal: Getting familiar with the working context and objects, getting to know and understand the code, finishing the peak finding algorithm.
- **Risks and remedies**: overlapping issues.
#### Week 1
- Start literature review work on general PIV, PTV stuff.
- Getting to know relevant computer vision technique and algorithm.
- Start to understand the logic of the code.
#### Week 2
- Understand peak finding problem and be able to express the strategy into algorithm. 
- Start implementing peak finding scheme into code, two methods: weighted average and gaussian fit.
#### Week 3
- Synthesis results, plot errors.
- Start coding the algorithm in C++.
- Implementing validation module (in matlab).
#### Week 4
- Apply the algorithm to real images.
- Deal with overlapping issues.
- Continue implementing peak-finding algorithms in C++ and validation algorithm in C++ is possible.
### April
- General goal: depending on the progress of peak finding algorithm, gradually focusing on the stereo matching and triangulation schemes.
-  **Risks and remedies**: ghost particles and selection criteria.
#### Week 5
- Continue implementing and testing peak finding scheme.
- Start reading about stereo matching and triangulation.
- Understand the needs and the logic of stereo matching and triangulation.
- Express them into algorithms and start implementing.
#### Week 6
- Implementing the stereo matching and triangulation module
- Implementing the validation modules.
#### Week 7&8 
- If the module works fine according to the validation routine, run the whole thing using STB or ENS.
- Some redundancy here because running the whole process can get messy.
### May
- General goal: the stereo matching and triangulation should be finished before end of may. Knowing more about stochastic dynamic model and data assimilation. 
- **Risks and remedies**: Running the whole program can result in unexpected bugs, to be resolved.
#### Week 9&10
- TBD
#### Week 11&12
- TBD
### June
- General goal: Focusing working on the code regarding the stochastic dynamic model and data assimilation (VAR). Implementing required function that is able to assimilate the Lagrangian data yielded by the ENS-PTV code. Start writing master thesis regarding the 3DPTV part.
- **Risks and remedies**: Transport equation (with help from Laurence), Stochastic turbulence model.
### July
- General goal: Finish the master thesis, depending on the request, the deadline should be the end of July or end of August; 
- **Risks and remedies**: Computational time about the data assimilation system, need to produce useable results.