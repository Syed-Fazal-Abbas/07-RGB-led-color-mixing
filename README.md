# Project 7: RGB LED Color Mixing

## Description
This is my seventh embedded systems project where I controlled an 
RGB LED using PWM (analogWrite) to produce different colors — Red, 
Green, Blue, and combinations like Purple, Yellow, and White.

## Hardware Used
- Board: Arduino Uno
- RGB LED (Common Cathode)
- Resistors: 3x 220 ohm
- Breadboard
- Jumper wires

## How It Works
The RGB LED's Red, Green, and Blue legs are connected to three PWM 
pins (9, 10, 11), and the common leg is connected to GND. Each pin 
is given a value between 0-255 using analogWrite(), controlling 
that color's intensity. By mixing different combinations, new 
colors can be created — for example, Purple (Red+Blue), Yellow 
(Red+Green), and White (all three at full brightness).

## Code

​```cpp
int redPin = 9;
int greenPin = 10;
int bluePin = 11;

void setup() {
  pinMode(redPin, OUTPUT);
  pinMode(greenPin, OUTPUT);
  pinMode(bluePin, OUTPUT);
}

void loop() {
  // Red
  analogWrite(redPin, 255);
  analogWrite(greenPin, 0);
  analogWrite(bluePin, 0);
  delay(1000);

  // Green
  analogWrite(redPin, 0);
  analogWrite(greenPin, 255);
  analogWrite(bluePin, 0);
  delay(1000);

  // Blue
  analogWrite(redPin, 0);
  analogWrite(greenPin, 0);
  analogWrite(bluePin, 255);
  delay(1000);

  // Purple (Red + Blue)
  analogWrite(redPin, 255);
  analogWrite(greenPin, 0);
  analogWrite(bluePin, 255);
  delay(1000);

  // Yellow (Red + Green)
  analogWrite(redPin, 255);
  analogWrite(greenPin, 255);
  analogWrite(bluePin, 0);
  delay(1000);

  // White (all on)
  analogWrite(redPin, 255);
  analogWrite(greenPin, 255);
  analogWrite(bluePin, 255);
  delay(1000);
}
​```
## Demo Video
[https://youtu.be/1ha5R7eo1Lw?si=eOJAtkasAZ7w2irz]

## What I Learned
- The concept of PWM (Pulse Width Modulation) and using analogWrite()
- Controlling multiple analog outputs at the same time
- The basic principle of color mixing (Red, Green, Blue combinations)
- The difference between Common Cathode and Common Anode RGB LEDs
