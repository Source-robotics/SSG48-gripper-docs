# CAN protocol

Since the SSG48 gripper is based on [spectral micro BLDC drivers](https://github.com/PCrnjak/Spectral-Micro-BLDC-controller), it inherits all of their control methods and functionality. <br />
Here we will describe only ones that are needed for gripper operation. For full list of commands go [Here](https://source-robotics.github.io/Spectral-BLDC-docs/apage7_can/). <br />
Also since the gripper is based on Spectral micro it has UART interface you can control it with.

### **Respond_Gripper_data_pack**

!!! Note annotate "" 

* Command ID: 60 <br />
* Direction: BLDC driver -> host <br />
* Python call: None, this command is sent only by driver <br />
* Length: 4 byte <br />
* Type of frame: standard <br />

Size (bytes) | Variable (Spectral_BLDC Lib python attribute)  | Type | Details
---- | ---- | ---- | ----
0  | gripper_position | unsigned 8bit |
1-2 | gripper_current |  16 bit signed |
3(bit 0) | gripper_activated | bit (0/1) | gripper activate (1) / deactivated (0)
3(bit 1) | gripper_action_status | bit (0/1) |  1 is goto, 0 is idle or performing auto release or in calibration
3(bit 2 and 3) | gripper_object_detection | 2 bit | 0 in motion, 1 object detected closing, 2 object detected opening, 3 at positon
3(bit 4) | gripper_temperature_error | bit (0/1) | gripper_temperature_error
3(bit 5) | gripper_timeout_error | bit (0/1) | gripper_timeout_error
3(bit 6) | gripper_estop_error | bit (0/1) | gripper_estop_error
3(bit 7) | gripper_calibrated | bit (0/1) | gripper calibration status; calibrated (1) / not calibrated (0)

---

---

### **Send_gripper_data_pack**

!!! Note annotate "" 

* Command ID: 61 <br />
* Direction: Host -> BLDC driver <br />
* Python API reference: Send_gripper_data_pack() <br />
* Type of frame: standard <br />
* Length: 5 byte 

Size (bytes) | Variable | Type 
---- | ---- | ----
0  | Position | unsigned 8bit
1 | Velocity | unsigned 8bit
2-3 | Current | signed 16bit  
4(bit 0)  | Gripper activate |  bit (0/1)
4(bit 1)  | Gripper action status |  bit (0/1)
4(bit 2)  | Gripper estop status |  bit (0/1)
4(bit 3)  | Gripper release direction |  bit (0/1)

Driver will respond to this command with:<br />
**Respond_Gripper_data_pack**

Alternatively you can send empty Send_gripper_data_pack command

* Command ID: 61 <br />
* Direction: Host -> BLDC driver <br />
* Python API reference: Send_gripper_data_pack() <br />
* Type of frame: standard <br />
* Length: 0 byte 

Driver will respons to this command with:<br />
**Respond_Gripper_data_pack**

---

### **Send_gripper_calibrate**

!!! Note annotate "" 

* Command ID: 62 <br />
* Direction: Host -> BLDC driver <br />
* Python API reference: Send_gripper_calibrate() <br />
* Type of frame: standard <br />
* Length: 0 byte 

**Driver will not respond to this command!**<br />

---


---

### **Send_Save_config**

!!! Note annotate "" 

* Command ID: 13 <br />
* Direction: Host -> BLDC driver <br />
* Python API reference: Send_Save_config() <br />
* Type of frame: standard <br />
* Length: 0 byte 

**Driver will not respond to this command!**<br />

---

### **Send_Reset**

!!! Note annotate "" 

* Command ID: 14 <br />
* Direction: Host -> BLDC driver <br />
* Python API reference: Send_Reset() <br />
* Type of frame: standard <br />
* Length: 0 byte 

**Driver will not respond to this command!**<br />

---

### **Send_Clear_Error**

!!! Note annotate "" 

* Command ID: 1 <br />
* Direction: Host -> BLDC driver <br />
* Python API reference: Send_Clear_Error() <br />
* Type of frame: standard <br />
* Length: 0 byte 

**Driver will not respond to this command!**<br />

---