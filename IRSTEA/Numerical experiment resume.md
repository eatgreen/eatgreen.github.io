# Numerical experiment resume

## case 1: Gaussian noise 
- Reference = Interpolated synthetic velocity
- Background = Reference + Noise
- Conclusion, works well
	  - very good for small synthetic velocity grid ($err\approx 0.002$)
	  - quite good for medium size synthetic velocity grid ($err\approx 0.02$ )
## case 2: AGW interpolation
- Reference = Interpolated synthetic velocity
- Background = Adaptive Gaussian Window Interpolation of Scattered particle velocity
- Conclusion: not so effective because the background field is already quite good with $err\approx [0.01,0.02]$ for medium size and $err\approx 0.002$ for small size.
## case 3: Constant mean value
- Reference = Interpolated synthetic velocity
- Background = Constant mean value
- Conclusion, works well
	- unlike case 1, the ensemble velocity mimic quite well the Background, here the errors are unknown beforehand.
	- for medium size grid, we obtain $err\approx 0.013$ reduced from 0.12.
