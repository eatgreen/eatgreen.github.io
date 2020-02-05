# Proceed Run Davis with Synthetic data
## Step 1, prepare fake project structure as Davis (check example).
## Step 2, prepare synthetic data for Davis
### Choose the right configuration for synthetic image generation.
1. For example, we use 'les3900rect' with 50 it_tot, 1000 particles, 0.5 as dtObs.
2. Run through, 'transexe', 'calibexe' and 'recexe'.
3. Now we should have synthetic images (in im7 format) stored under 'data' directory in the disk.
4. Use python file 'post/writemftodavis.py'. Adjust the parameters so that they are consistent with the case configurations. The produced mapping function in 'xml' format should be stored somewhere in the disk.
## Step 3, Run synthetic data in Davis
1. Take the images and the mapping function file (that's all you need to do it in Davis) to the fake project and put them in the right place. 
2. Re-run Volume self calibration and obtain OTF function.
	- Possible bug in 10.05: when large disparity is found using given mapping function, change the subdomain size from 5x5x2 to 1x1x1 will help reducing the errors. Then we can change it back to 5x5x2 when the errors are reduced. 
	- Or reduce the triangulation error size to 1px
3. Run STB, and eventually VIC# if needed.
4. Export particle positions' data into TECPLOT format.
## Step 4, run ENSPTV using background data produced by Davis.
1. Copy ShakeTheBox.dat file.
2. Load lavision_bkgonly module and adjust configuration file if needed.
3. Run 'lavisionexe'.
## Step 5, Comparison of the quality of reconstruction of particles between STB and ENSPTV
1. Check post/compareRefWithDavis.py