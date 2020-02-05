###Online motion model learning

Usually the sensor is stationary or known pose
input, perception measurements
output, locations of moving objects and their motion modes
model learning with state inference

###Formulation
\[p(o_k,s_k|Z_k)\]
$o_k$ true state of the moving object at time k
$s_k$ true motion mode
$Z_k$ perception measurement set along time 0-k
**Bayes' law**
\[p(o_k,s_k|Z_k)=p(o_k|s_k,Z_k)p(s_k|Z_k)\]
* model learning stage, $p(s_k|Z_k)$ get down to a model selection.
* state inference stage, $p(o_k|s_k,Z_k)$.

###Interacting multiple model algorithm
1. Initialization, DBN
2. Prediction. 
3. Data association. 
4. Update.