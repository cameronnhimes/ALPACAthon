Jackie, Cam and Melody

Hackathon 2021 

Organismal Form and Function 

**Background**

This tutorial will describe how to use the ALPACA software to compare and contrast 3D models of bird skulls through the use of landmarks. The example provided here will be studying various skulls of waterfowl. 3 skulls will be used in this tutorial: Anas platyrhynchos, Oxyura jamaicensis, and Anser Anser.
The mallard duck, Anas platyrhynchos, is a generalist, while the other two species of waterfowl have specialized diets. Because of their unique diets, they are ideal for morphological analysis. 
The ALPACA software is available through the SlicerMorph extension available through the 3D slicer application. 

**Download the appropriate software**

Download 3D slicer software https://download.slicer.org 
Get slicermorph extension (ALPACA is part of this)
On 3D slicer, go to extensions manager module to search for and install the SlicerMorph extension


**Searching for good models** 

1. Find species that are phylogenetically related to one other. Ideally you want to find one generalist species and two specialist species
2. Our skulls were chosen with reference to Olsen 2017 paper
3. Choosing a 3D model - use this selection of websites to find models
a) Morphosource.org
b) Openscienceframework  -  Osf.io 
c) https://osf.io/ecmz4/ 
d) https://www.phenome10k.org 
Here is what to search for in a good 3D model:
1. Find intact, unbroken skulls with no fractures or significant damage
2. Search for high resolution models, the higher the better
3. Ideal formats for model (ply, etc)
   a) Convert stl files to ply format. 
4. Want skulls that are not too different from one another, or else it will be difficult to compare landmarks
5. Download your chosen models in a designated folder on your computer

**Here are the models we used **

Anas platyrhynchos (mallard) - most generalist. Eats gastropods and insects, plants
<img width="598" alt="Screen Shot 2021-12-06 at 1 08 39 PM" src="https://user-images.githubusercontent.com/70450909/144898923-78c59279-d6b3-4fce-8694-ce1d9d25ec71.png">



Oxyura jamaicensis (ruddy duck)- diver that eats aquatic vegetation
<img width="592" alt="Screen Shot 2021-12-06 at 1 10 50 PM" src="https://user-images.githubusercontent.com/70450909/144899209-84ddc7ea-a771-41b3-95f2-90e8d8b40e1c.png">



Anser Anser (graylag goose) - herbivores that eat mainly grasses
<img width="597" alt="Screen Shot 2021-12-06 at 1 11 08 PM" src="https://user-images.githubusercontent.com/70450909/144899257-c2d481af-07c5-425e-837b-a21adc455c44.png"> 



**Placing Landmarks on the generalist Anas Platyrhynch**

1. Download 3D models from the data folder- there should be three .ply files. 
2. Open 3D slicer 
3. Drag and drop the Anas Platyrhynch .ply file into 3D slicer
4. Under the drop down menu enter the markups tab
5. Click the three red dots next to create- this will change the cursor to a green marker 
6. Then click the spot on your skull that you would like to make a landmark- this dot will turn pink to show that the landmark was made.
7. You can rename the landmark to something simple like “1”
8. We changed the glyph size to 5% to make the points more visible

<img width="594" alt="Screen Shot 2021-12-06 at 1 12 16 PM" src="https://user-images.githubusercontent.com/70450909/144899416-18360392-e05e-4c38-8831-145993048902.png">

9. Keep adding landmarks until you have reached the desired amount- we added 10 landmarks.
10. Adding landmarks in this manner will create 10 different .fcsv files when you go to save- therefore, we will condense them all into one file. To do this, click on your SECOND landmark and scroll down under the control points tab and copy the coordinate points. 

<img width="627" alt="Screen Shot 2021-12-06 at 1 12 43 PM" src="https://user-images.githubusercontent.com/70450909/144899462-e9d6c2c9-ef2b-4cea-b199-ae2f065fdf77.png">

11. Then, click back to landmark one, and paste the coordinates into the same area. Do this with all of the points, deleting the original fiducial after the coordinates are copied

<img width="716" alt="Screen Shot 2021-12-06 at 1 13 13 PM" src="https://user-images.githubusercontent.com/70450909/144899538-2f64f30b-e33d-43d7-a3ce-10ffd0f80c1b.png">

12. Then click the save button in the top left hand corner and make sure that the file is saved as a .fcsv into the correct working directory. 


**Placing the Generalist Landmarks on Specialists Anser Anser and Oxyura Jamaicen**

1. Make a new 3D slicer workbook
2. Drag and drop all three .ply files (the generalist and two specialists)
3. Open the ALPACA module 

<img width="334" alt="Screen Shot 2021-12-06 at 1 14 05 PM" src="https://user-images.githubusercontent.com/70450909/144899629-94f6a8c6-da03-4b4f-85a6-b35df0249af7.png">

4. Set up correct orientation of folders. Within your working directory set up a folder with the generalist.ply and the generalist landmarks (called generalist). Within the generalist folder create a folder called “specialists” that contains both specialist.ply files. Within the specialist folder create a folder named “out: (keep this empty for now).
5. Make the source mesh the generalist folder. The source landmark is the .fcsv file. Target mesh directory is the specialist file. The Target output landmark directory is the out folder.

<img width="396" alt="Screen Shot 2021-12-06 at 1 14 26 PM" src="https://user-images.githubusercontent.com/70450909/144899675-1e1f719d-bd66-4c87-8632-7dff2ce1b6b0.png">

6. Under advanced parameter settings make point density adjustment 0.5. Point density adjustment is the new subsampling voxel size (for references to old tutorials). 
7. Click run auto-landmarking. It will look like nothing happened, but there should be two new .fscv files in the “out” folder. Make sure they’re there before exiting. 


**Post Processing Analysis and Applying General Procrustes Analysis **

1. Open up a fresh 3D slicer workbook. Drag and drop the .fcsv files from the “out” folder into slicer. Also drag and drop the .ply files of both the specialists. 
2. This will show two sets of landmarks on two skulls. You can view them individually by clicking the “eye” next to their name. 

<img width="551" alt="Screen Shot 2021-12-06 at 1 15 15 PM" src="https://user-images.githubusercontent.com/70450909/144899803-cab54333-7f5f-4a77-ac3f-7d71ab408007.png">

3. Under the drop down menu click slicer morph → Geometric morphometrics → GPA

<img width="456" alt="Screen Shot 2021-12-06 at 1 15 31 PM" src="https://user-images.githubusercontent.com/70450909/144899831-73559fbd-a162-4eeb-aea7-6e2998fa8bc7.png">

4. Make a new folder called “GPA outputs”
5. Under select landmark files add all three landmark .fcsv files (generalist +2 specialists)
6. Under select output directory click your “GPA outputs” folder
7. Click “Execute GPA + PCA” 

<img width="525" alt="Screen Shot 2021-12-06 at 1 15 58 PM" src="https://user-images.githubusercontent.com/70450909/144899893-ca7906f9-6208-4016-8b73-1f3c6137c087.png">

8. This will produce a general procrustes analysis. In the “GPA outputs” folder there will be raw data from the analysis that will tell you information about the landmarks. 


References

SlicerMorph. “Spr_2021/day_4/Alpaca at Main · Slicermorph/spr_2021.” GitHub, https://github.com/SlicerMorph/Spr_2021/tree/main/Day_4/ALPACA. 

Olsen, A. M. (2017). Feeding ecology is the primary driver of beak shape diversification in waterfowl. Functional Ecology, 31(10), 1985-1995.
