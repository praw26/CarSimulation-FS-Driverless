# CarSimulation-FS-Driverless
This is a Car Simulation Game made on Unity to collect Labelled data for Haar Cascade Algorithm to run a Formula Student Driverless Prototype (Competition link : https://www.formulastudent.de/pr/news/details/article/autonomous-driving-at-formula-student-germany-2017/)

Pre-requisites: 
Required Software: Unity 3D
For first time users: Unity 3D is an open source GameEngine and runs on C# Scripting. 
You can download the latest version at https://unity3d.com/get-unity/download for free. 

If you are experienced with Unity, create a new project, and import standard assets(Environmental, Utility)
Log in to Unity's Asset Store(It can be assessed from the Unity itself) and download 'Traffic Cones'. You can download it from here: https://www.assetstore.unity3d.com/en/#!/content/34912 . This is a free asset in the asset store. 

We will require a Running Car (3D Model) with Car Physics (Scripting) to run the game. There are many free and paid assets in the Asset Store. I have used 'Realistic Car Controller' from BoneCracker Games for its good car-physics accuracy. This is a paid asset and can be imported from here: https://www.assetstore.unity3d.com/en/#!/content/16296. 

For building the track, we can either do it by adding them manually by downloading assets for making roads on the Asset Store. Another easier and less time-consuming way is to use the package 'RoadArchitect' made by MicroGSD(https://github.com/MicroGSD/RoadArchitect). I used this and it scales the process of buiding the track without writing any script for it. You can donwload the latest release of RoadArchitect from here: https://github.com/MicroGSD/RoadArchitect/releases(Download both the unity package and the source code). It also has DIY tutorials to learn how to use this package. 

Building the Game: 
Once you have the prerequisites, 
Go to Menu -> Assets -> Import Package -> Custom Package. Go to the installed directory of Road Architect, select and import the Unity Package file. RoadArchitect will now show under 'Projects' on the main screen. 
Watch tutorials to build tracks, bridges, extrusions and edge objects. We mostly require Tutorial 1 to build this game. (https://www.youtube.com/watch?v=IR4lwbnuPVQ&t=170s)

I have made a cones boundary required for training by selecting a particular node, choosing 'Open Wizard -> Edge Objects -> Rigid/Static Cones'. It will create a boundary of cones till the next node. You can then change the cone placement on the track by using 'Horizonal Offset' in the Inspector once you select the starting node. For this project I required cones to be different for left and right side of the track so I selected 'Material Override' and picked my own colour(material) for one side of the cones(I picked the material from 'Traffic Cones' Free Asset donwloaded earlier). 
This was a bit tiresome, but it needs to be done for every node. For this reason, try to have as less nodes as possible for the track. 
In this way you can have desired cone placement and material as visible in the final game.   

If you choose to go with Realistic Car Controller, you need to import the package from inside Unity. Once it is visible in the project window, go to Resources -> Vehicles and pick one vehicle you want to use(you can also use multiple vehicles but it requires scripting). 
Delete all cameras associated with the vehicle
Also delete Main camera
Go to Tools -> BoneCracker Games -> Realistic car controller -> Create -> Cameras -> Add RCC car to Scene. 
Place this camera under the vehicle model, then it becomes pivoted to the vehicle.  
Check Transformations under Inspector and alter them to place it right at the driver viewing angle.  
Click on the Vehicle under Hierarchy and use Transforms to place it on the road. 

Unfortunately, I couldn't add the whole Unity Project here since Realistic Car Controller is in the Game folder and it is a paid asset. I have added the final project here. It is an executible file which runs without any libraries. Also, you can add a lot of other assets like traffic lights, traffic signs, particle systems etc. 
I chose not to add them since the whole purpose of making this is to collect trainig data for running Haar Cascade for the Formula Student Driverless Project. The images will be saved per frame and cropped cone images will be used as labelled data. 

Part-2 will have running Haar Cascade classifier based on training data collected from this game. 
