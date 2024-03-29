# About the gripper


<p align="left"> <img src="../assets/GRIP_CVR.png" alt="drawing" width="5000"/> <br /> </p>  

SSG-48 adaptive electric gripper is a gripper based on **Spectral micro BLDC drivers**. It is a gripper capable of controlling its gripping force, making it perfect for assembly tasks and human-robot collaboration. Gripping force can be adjusted allowing you to grasp a wide range of items; from delicate and soft to rigid and sturdy.<br /> 

STL files are open source allowing you to add a custom griping tool and attach it to any robotic arm or robot. 

SSG-48 adaptive electric gripper is available as a fully assembled gripper or you can build your own by following assembly manual.

If you plan to build SSG-48 adaptive electric gripper by yourself you will need to source all the parts from [this BOM]().
After that you can follow the [assembly manual]() to assemble your gripper.

General specs:

* Power supply: 24V
* Idle power: 0.5W
* Weight: 400 g
* Maximum gripping force: 20N
* Minimum gripping force: 1N
* Operating temperature -5 to 65 deg
* Communication interface: CAN bus
* Material: PETG plastic
* Stroke: 0 - 48 mm

<p align="left"> <img src="../assets/gripper_stroke.png" alt="drawing" width="650"/> <br /> </p> 


## Pinout
<p align="left"> <img src="../assets/GRPCON.png" alt="drawing" width="650"/> <br /> </p> 

To power the gripper you need to use 24V. <br />
You can send commands to the gripper using 5V CAN bus. <br />
Check control page and learn how the gripper works. <br />
Check CAN protocol page if you wish to use gripper API.

## Dimensions
   |   |   |
    ---- | ---- 
    <p align="left"> <img src="../assets/DIM2.PNG" alt="drawing" width="600"/> <br /> </p> | <p align="left"> <img src="../assets/DIM3.PNG" alt="drawing" width="535"/> <br /> </p> 
    
<p align="left"> <img src="../assets/DIM3.PNG" alt="drawing" width="500"/> <br /> </p> 


### Dimensions with PAROL6 adapter

<p align="left"> <img src="../assets/DIM1.PNG" alt="drawing" width="500"/> <br /> </p> 



## 3D model

[Link to the STEP model]()
<p align="left"> <img src="../assets/GRIP_MODEL.PNG" alt="drawing" width="500"/> <br /> </p> 


## Torque curves

## Spectral driver config

Upload preconfigured BIN file. Re calibrate the motor after that. TODO<br />
Using serial interface (On how to use it check this link) (What adapter to get check this link)<br />
You will need send these commands:<br />
#Gripper 1