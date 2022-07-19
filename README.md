# GPS-aided Inertial Navigation System Module (In Progress)

* MCU: STM32F103C8T6
* Communication Protocol: CAN
* Features: Pitch, Roll, Yaw, Direction, Latitude, Longitude, Temperature, Altitude, Pressure 

<hr>

<h3>CAN Frame </h3>
(Based on CANopen)

Upper 6 bits - Module ID - max 0x3F </br>
Lower 5 bits - Command ID - max 0x1F</br>
CAN ID = (Module ID << 5) | Command ID</br>
Default Module ID : 0x200 (Standard)

| CMD_ID | Name | Sender  | Signals | Start byte | Signal Type | Bits |
| ------ | -----| -------- | --------  | -------- | -------- |-------- |
| `0x001`   | Heartbeat | Module  | Latitude, Longitude  | 0, 4  | IEEE 754 Float, IEEE 754 Float | 32, 32 |


<hr>

<h3>Sensors: </h3>

* MPU-9250
  * 9-axis MEMS sensor
  * Pinout:
    - PB11: SDA
    - PB10: SCL
  * Communication Protocol: I2C
  
* NEO-6M
  * GPS Module
  * Pinout:
    - PA3: TX
    - PA2: RX
  * Communication Protocol: UART
 
* BMP180
  * Barometric Pressure/Temperature/Altitude Sensor
  * Pinout:
    - PB7: SDA
    - PB6: SCL
  * Communication Protocol: I2C

<hr>

<h3>PCB Design </h3>

<img width="500" alt="Screenshot 2022-07-18 at 11 41 18 PM" src="https://user-images.githubusercontent.com/103095333/179577610-0c274702-8bef-49db-9b5b-6c50e04fc092.png">

    
