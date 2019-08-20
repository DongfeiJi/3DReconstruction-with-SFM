# 3DReconstruction-with-SFM
3D reconstruction for multi-angle image input with VisualSFM+CMVS+MeshLab.  

## Introduction  
There are two key steps in the reconstruction of multi-view stereo vision:   
Restoring Structure from Motion (SFM) and Multi-View Stereo (MVS) from Motion Information.  
The general steps are as follows:  
Feature extraction and matching - > sparse reconstruction - > dense reconstruction - > surface reconstruction.  
This repo uses Visual SFM + MeshLab tool to go through the above process.  

## Environment
OS：win10/win8  

Software versiopn：ViusalSFM 5.24  

CMVS+genOption+PMVS2: http://francemapping.free.fr/Portfolio/Prog3D/CMVS.html  

MeshLab 1.3.2 x64（Note that if the reconstruction scenario is large, 32-bit software will be prompted to use 64-bit version.）  

## How to use?
### VisualSFM
1. Open the VisualSFM.exe  
2. Add the images in ./data/dog  
3. Feature extraction and feature matching  
4. Sparse reconstruction and dense reconstruction  

### MeshLab
1. Open the MeshLab.exe
2. Open ./data/mydog.nvm.cmvs/00/bundle.rd.out, then the list.txt(this is the sparse reconstruction source)  
3. Import ./data/optim_dog.ply(this is the 3D object dense reconstruction mesh)  
now, u have your 3D source.

## Improve
1. Show the position of camera by Render->ShowCamera.    
2. Clear up the clutter.    
That is to remove the points that are far apart, the points that are not the targets we want,  
and the points that are obviously wrong (e.g. not on the original plane).      
3. Gridding by Filter -> Point Set -> Surface Reconstruction:Poisson.    
4. Delete redundant parts by Filter-> Slection -> Slect Face With edges longer than...  
5. Repair Manifold Edge by Filter-> Selction ->Slect non Manifold Edges.  
6. Parameterization by Filter–> Texture –> Parameterization from registered rasters.  
7. Texture projection by Filter–> Texture –> Project active rasters color to current mesh, filling thetexture.  
8. Save the mesh.
