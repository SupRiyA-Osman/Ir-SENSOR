#include <Servo.h>  // Include the Servo library

Servo myServo;      // Create a Servo object
const int irPin = 9; // Pin connected to the IR sensor
const int servoPin = 5; // Pin connected to the servo motor

void setup() {
  pinMode(irPin, INPUT);  // Set IR sensor pin as input
  myServo.attach(servoPin); // Attach the servo to the specified pin
  myServo.write(0); // Start with the servo at 0 degrees
}

void loop() {
  int sensorValue = digitalRead(irPin); // Read the value from the IR sensor
  
  if (sensorValue == HIGH) {
    // If object is detected (IR sensor output is HIGH)
    myServo.write(90); // Move the servo to 90 degrees
  } else {
    // If no object is detected
    myServo.write(0); // Move the servo to 0 degrees
  }
  
  delay(100); // Wait for 100ms before checking again
}
Show quoted text
