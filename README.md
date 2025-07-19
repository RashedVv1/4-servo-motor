# This project controls 4 servo motors using an Arduino Uno. The servos simulate basic movements that could be used in a humanoid robot, including a sweep motion and a holding position. It also includes a basic algorithm outlining how a walking motion can be programmed in a robot.

 Features:

Uses 4 servo motors

Executes the Sweep example motion for 2 seconds

Holds all motors at 90° position after sweeping

Provides a basic walking algorithm for a humanoid robot

Arduino Code:

#include <Servo.h>
#include <Servo.h>

Servo servo1, servo2, servo3, servo4;

void setup() {
  servo1.attach(9);
  servo2.attach(10);
  servo3.attach(11);
  servo4.attach(12);
}

void loop() {
  // Sweep motion for 2 seconds
  unsigned long startTime = millis();
  while (millis() - startTime < 2000) {
    for (int pos = 0; pos <= 180; pos += 5) {
      servo1.write(pos);
      servo2.write(pos);
      servo3.write(pos);
      servo4.write(pos);
      delay(15);
    }
    for (int pos = 180; pos >= 0; pos -= 5) {
      servo1.write(pos);
      servo2.write(pos);
      servo3.write(pos);
      servo4.write(pos);
      delay(15);
    }
  }

  // Hold at 90 degrees
  servo1.write(90);
  servo2.write(90);
  servo3.write(90);
  servo4.write(90);
  while (true); // Stop the loop here
}


