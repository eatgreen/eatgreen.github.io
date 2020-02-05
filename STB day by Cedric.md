# VSC-STB day by Cedric
## 3d, Calibration plate use two sides.
- 1 view has two planes
## 2d, equidistant.
- polynomial, plate cover all. 3-5 planes, four or five marks in each direction
- pinhole
## size
- 90x110x50 mm^3
- image dewarping ???
## Error of 0.1 px level must attained
- before each processing
## VSC: Disparity maps

## triangulation
- pinhole model
- apply polynomial function to particle matching

## Ghost particle suppression/VSC-GPS, 2018
Correlation map

## Software tutorial
- check the perspective correction and distortion function and determine the the real size 
- triangulation error no more than 10 pixel
- increase the Z direction
- make sure all sub volumes has disparity maps
- more images with large increment 
## Preprocessing
- subtract time filter
- image preprocessing
	1. Normalize local image when image has different particle density, or different intensity.
	2. Smaller than 16bit image maximum
- make sure the particles are everywhere
- black background, not too much noises 
# Shake-the-Box
- larger domain than VSC domain
- threshold for 2d particle detection
	* try high threshold
- error of triangulation
	* 1 or 2
## OTF
- OTF estimated is a bit bigger in terms of particle radius
- RC increase particle intensity, when intensity is small that the corresponding particle image can not be cancelled
- RC OTF radius
- Tracking length 4 to 10
- homogenous, no big discontinuity (big acceleration) 
## LCS
- 