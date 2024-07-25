# Robot-motion
Simple robot walking algorithm that creates a basic walking motion by lifting and moving each leg in a sequence, while keeping the other leg stationary. The walking cycle can be repeated to create a continuous walking motion.
# Setup
* Put the servo motors to their eight positions in each leg (hip, knee, and ankle).
* Set the walking speed and stride length.
# Simple-motion-cycle
1. **Lift Left Leg**
	* Servo 1 (Left Hip): Move to 120 degrees (lift left leg)
	* Servo 2 (Left Knee): Move to 60 degrees (bend left knee)
	* Servo 3 (Left Ankle): Move to 120 degrees (lift left ankle)
2. **Move Left Leg Forward**
	* Servo 1 (Left Hip): Move to 150 degrees (move left leg forward)
	* Servo 2 (Left Knee): Move to 90 degrees (straighten left knee)
	* Servo 3 (Left Ankle): Move to 150 degrees (move left ankle forward)
3. **Lower Left Leg**
	* Servo 1 (Left Hip): Move to 90 degrees (lower left leg)
	* Servo 2 (Left Knee): Move to 120 degrees (bend left knee)
	* Servo 3 (Left Ankle): Move to 90 degrees (lower left ankle)

4. **Lift Right Leg**
	* Servo 4 (Right Hip): Move to 120 degrees (lift right leg)
	* Servo 5 (Right Knee): Move to 60 degrees (bend right knee)
	* Servo 6 (Right Ankle): Move to 120 degrees (lift right ankle)
5. **Move Right Leg Forward**
	* Servo 4 (Right Hip): Move to 150 degrees (move right leg forward)
	* Servo 5 (Right Knee): Move to 90 degrees (straighten right knee)
	* Servo 6 (Right Ankle): Move to 150 degrees (move right ankle forward)
6. **Lower Right Leg**
	* Servo 4 (Right Hip): Move to 90 degrees (lower right leg)
	* Servo 5 (Right Knee): Move to 120 degrees (bend right knee)
	* Servo 6 (Right Ankle): Move to 90 degrees (lower right ankle)
-------------------------------------------------------------------------

* Repeat steps 1-6 to create a continuous walking motion
* Adjust the walking speed and stride length and each servo motor's angle to best control the robot's movement

-------------------------------------------------------------------------

**Notes**

* The servo motor movements should be smooth and gradual to create a natural walking motion.
* The walking cycle can be adjusted to change the robot's gait, speed, and stride length.
* The algorithm can be modified to add additional features, such as turning or stopping.
* The servo motor positions and movements may need to be adjusted based on the specific robot design and servo motor characteristics.
* This is a basic algorithm and may need to be modified and fine-tuned to work with any specific robot design and servo motor characteristics.

-------------------------------------------------------------------------
### Using simulation environment to connect an electronic circuit composed of 6 servo motors  
#### Requirements
* Online 3D modeling simulator e.g. Tinckercad https://www.tinkercad.com

#### Circuit design:
![6-servo](https://github.com/user-attachments/assets/3bb6859c-6fa3-460f-b2a7-3dbfc14a8d1e)

---------------------------------------------------------------------------
#### List of the circuit's components:
![Component List - 6 servos](https://github.com/user-attachments/assets/c289ea32-2289-46b2-b587-bd03572974f5)

---------------------------------------------------------------------------
#### Schematic View of the circuit:
![Schematic View](https://github.com/user-attachments/assets/7ad95aaa-1308-4e25-9f4b-119d3982a60f)

---------------------------------------------------------------------------


* After connection each of the six servo motor to the Arduino board and to the power source, you can use the following code to control the motion of each one:


```
#include <Servo.h>

// Define the servo objects
Servo servo1;
Servo servo2;
Servo servo3;
Servo servo4;
Servo servo5;
Servo servo6;

// Define the pin numbers for each servo
int servo1Pin = 12;
int servo2Pin = 10;
int servo3Pin = 8;
int servo4Pin = 6;
int servo5Pin = 4;
int servo6Pin = 2;

void setup() {
  // Initialize the servo objects
  servo1.attach(servo1Pin);
  servo2.attach(servo2Pin);
  servo3.attach(servo3Pin);
  servo4.attach(servo4Pin);
  servo5.attach(servo5Pin);
  servo6.attach(servo6Pin);
}


void loop() {
  // Sweep servos from 45 to 0 degree for 3 servos
  for (int pos = 45; pos >= 0; pos -= 1) {
    servo1.write(pos);
    servo2.write(pos);
    servo3.write(pos);
    delay(20); // Delay
  }

  // Sweep servos from 45 to 0 degree for 3 servos
  for (int pos = 45; pos >= 0; pos -= 1) {
    servo4.write(pos);
    servo5.write(pos);
    servo6.write(pos);
    delay(20); // Delay
  }
  // Sweep servos from 0 to 360 degrees
  for (int pos = 0; pos <= 360; pos += 1) {
    servo1.write(pos);
    servo2.write(pos);
    servo3.write(pos);
    servo4.write(pos);
    servo5.write(pos);
    servo6.write(pos);
    delay(20); // Delay 
  }

  delay(2000); // Wait for 2 seconds
}
```
-------------------------------------------------------------------

## Demo:


https://github.com/user-attachments/assets/0cabf434-1add-46c2-96a7-a1859314e6ec






