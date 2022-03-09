# outlet_vision_flow
A program for computer vision-based measurement of pipe outlet flow using video data.

# Overview: 
This is a Windows application that takes a video as input and produces estimates of outlet flow. It allows a user to select a video clip of an overflow event and visualize the resulting flow rates. The application creates a csv file that records flow rate at a time interval of 0.2s. 


This application is for 64-bit Windows systems, including Windows 7 and later. A minimum of 3rd generation Intel Core i3 processor and 4GB memory is recommended. It was recently tested and verified on a Windows 10 Pro desktop with an Intel(R) Core(TM) i9-10900 CPU.

Download all files in the main directly. Upon running the Overflow.exe file, the following window should appear. This is the primary window for the application. 
![overflow-mainpage](https://user-images.githubusercontent.com/23243852/157518126-10512d61-5294-46be-84ea-68af68278ea7.PNG)

The first step is to select a video for processing. Several test videos are available in this repository. If you would like to record your own outlet flow event, the experimental setup and video must meet the following requirements: 
- At least 8MP and 20 fps video are recommended. Be sure the setup has good lighting and the outlet flow (water) is visible against a uniform, non-white background.
- The camera must be stationary for the entire duration of data capture. 
- This program has been developed to take in .avi files.
- The approach is robust to small movements and objects in the background, but obstructions of the outlet flow should be avoided.
- The video must be collected perpendicular to the outlet. Both the outlet radius and the height to the container are required (see R and H image below).
![hori-lab-model](https://user-images.githubusercontent.com/23243852/157520478-5690def6-2104-48a3-aa87-8e97a9cf685d.png)

After uploading your video and providing the required dimensions, the application can be run by selecting the green Run button. During processing, a video output with detected flow and estimated measurements will be shown in real time: 
![overflow-process](https://user-images.githubusercontent.com/23243852/157521039-8f4c33fe-923a-4a70-81a2-f7dfb351bb1c.PNG)

After procesing, the user will have the option to save the data to a .csv file in a specified location: 
![overflow-savetocsv](https://user-images.githubusercontent.com/23243852/157521142-3ea005ff-1f6b-4d41-a1ff-19c51dad9035.PNG)

The software uses a variety of computer vision aprpoaches to detect motion of the overflow event. Once only the water overflow has been detected, a parabola fitting approach is used to determine key points that are used estimate the wetted area of the pipe, after which Manning's equation is used to estimate flow. Please check back for a link to the full manuscript with key details, which will be included once published.
