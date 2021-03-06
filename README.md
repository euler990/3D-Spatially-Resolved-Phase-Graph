# 3D-Spatially-Resolved-Phase-Graph 
An open access recursive magnetization evolution algorithm framework is proposed for simulating arbitrary pulse sequences in presence of *time-variant gradients* with *arbitrary orientations* in three dimensions. 
It overcomes the sequence symmetry requirements of the extended phase graph algorithm for solving the Bloch-Torrey equation efficiently, and could present the signal modulation in the 3D spatial domain. 

# Author： 
- Xiang Gao, xiang.gao@uniklinik-freiburg.de
- V. G. Kiselev 
- Maxim Zaitsev

# Demo: Stejskal-Tanner pulse sequence simulation:  
-Input file: *demo_seq_dt.txt*  
-Simulation command: *3D_SR-PG_tensor.exe demo_seq_dt.txt*  
-Output file: *output1.txt* and *output1_Nspins.txt*  

To interpret the output file, one could use *util/KmapSignal2.m* function, which returns:  
-*logData.kvector*,[kx,ky,kz]  
-*logData.signal*,[signal real part,signal imaginary part,0]   

To further transform the signal into spatial domain, one can use function *util/IMG_DFT.m* with additional input parameters, eg:  
-*global FOV; FOV=192;*  
-*global Mat; Mat=64;*  
It returns:  
-*slogData.sig3d*, 2D Image(Mag) of x-y, y-z, x-z plane for each echo. Image can be pre-filtered by setting kfilter in Kspace    
-*slogData.pha3d*, 2D Image(Phas) of x-y, y-z, x-z plane for each echo. Image can be pre-filtered by setting kfilter in Kspace    

# Two illustrative examples are presented in  
-*example_offres_MRF.m*, Fast off-resonance calculation for Pseudo-SSFP dictionary building in magnetic resonance fingerprinting  
-*example_PRESS_MRSI.m*, 3D signal evolution visualization for the PRESS-based magnetic spectroscopic imaging   

The Details of those two examples are reported in the corresponding paper:  
(TBC)  
  
# Updated
Anisotropic diffusion simulation is supported
  
