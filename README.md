### Features
1. Harris corner
2. Region based Harris
3. Compute Homography

### Need to be completed:
4. Homography with Selected Image i.e
	i) Show both display and camera coodinate
	ii) Map image in the selected coordinate of the display
5. Implementation of multi-display for projection mapping by homography. 

### Advancement upto now:
##### Python:
1. Harris Corner : completed
2. Regions Based: completed
3. Homography with manual functionality: completed
4.  Homography with Selected Image: completed
5. Implementation of multi-display for projection mapping by homography: Not yet.

##### Unity:
1. Harris Corner : completed
2. Regions Based: completed
3. Homography with manual functionality: completed
4.  Homography with Selected Image: Partially done, i.e all functions are available, need to do the transformation of the coordinates of the pixels in the texture then a mouse event tracking. 
5. Implementation of multi-display for projection mapping by homography: Not yet.


### Unity Folder structure: 
![Screenshot from 2024-09-24 23-28-31](https://github.com/user-attachments/assets/bd0c3108-cf20-40c2-9b52-c940b7e164c6)

#### Important Things:
1. Appcanvas(Canvas): The root component for rendering all UI objects in Unity. Tutorial: https://www.youtube.com/watch?v=OD-p1eMsyrU&ab_channel=Unity
2. Panel: Image element added for the background
3. **harris_response**: A button for which is triggering calculation for the harris response
4. **regional_harris**: Button for selecting region for the harris response for that region
5. **home_c_p**: Button to trigger calculation for the camera to projector homography and do the number-4(see above)
6. _DisplayImage_: Raw Image for your view(same view will be on projector/display)
7. _display_names_: A dropDown UI(legacy) to select the display for projection(attached to the gameObject Image Process)
8. Exit: A button for exit the app
9. Editor window to Step 5 are only the text for the display
10. **logger**: It's a Scroll View UI object for displaying the log(cominf from Debug.Log())
11. Game object: **ImageProcess**: For Harris Corner detection Script
12. Game object:**ExitProcess**: For Exit Button Script
13. Game object: **RegionalHarris**: For Regional Harris Script
14. Game object: **Logger**: Attached the debugging script
15. Game object: **HomographyCameraToProjector**: for doing homography stuff
    

#### Folder overview
Currently I maintained 3 folder: harrisCorner, homography and necessary

Descriptions for the folders and it's assets:
1. hasrrisCorner -> (Sub folders)

     i) _Prefab_ : https://www.youtube.com/watch?v=pv30sE_Vsis&ab_channel=toficofi

   	1. **CoordinateTextPrefab** : Printing ccordinate on Display
        
     ii) _Shader_: **harris** : To compute the harris response (it also works with video/live video source)
     
    iii) _utily-file_: Everytime you run the Regional Harris response, file in here store the selected coodinate
    
    iv) _utility script_: **DisplayManager**: It's basically the outputScript for other display
   
(Scripts)

   i) **HarrisCornerDetector**: for harris corner detection main script attached to the gameObject ImageProcess

   ii) **RegionalHarris**: For regional Harris corner and it is attached to the gameObject RegionalHarris

2) homgraphy : (Scripts):HomographyCameraToProjector: calculate homography(upto now), takes points from RegionalHarris and also the input image from harrisCorner. In this scripts some other functions are also available for later work, like: fileBrowser etc.

3) necessary: (Scripts)

   i) **ExitButtion**: Scripts for the exit button

   ii) **LoggerTemplate**: Scripts for the Debug printing on the app.


### Used Third-Party Plugins:
1. SFB fileBrowser(Included on the app) - https://github.com/gkngkc/UnityStandaloneFileBrowser
2. NuGet:
	
	i) Numsharp: for using numpy
	
	ii) **MathNet.Numerics.LinearAlgebra**: it also comes from NuGet and it has been used for calculating SVD in a faster way.

Other Scripts: (project CameraOpenFresh)
 1. **CameraSelector**(Script)(didn't used in main Project): It's basically for camera detection and take the camera feed. You just need to click(Implement the method) maybe couple of pictures and stored it(file storing script: can be found in RegionalHarris) for using it on the project.
 2. Make Sure You enable **2d viewer** on the window and **PLEASE SELECT /Assets/Scenes/CameraOpen** for displaying the scene on the window. 



















