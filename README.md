# Arduino Circuits Projects

## Table of Content
- [Overview](#overview)
- [Arduino Components](#getting-started-with-arduino-components)
- [Tinkercad Simulator](#tinkercad-simulator)
- [Circuits](#circuits)
  - [On/Off LED Circuit](#onoff-led-circuit)
  - [Fade In/Out LED Circuit](#fade-inout-led-circuit)
## Overview   

This repository documents my learning process in implementing Arduino circuits, using digital and physical components to control sensors and output devices.



## Getting Started with Arduino Components

### Arduino UNO R3
![s-l400](https://github.com/user-attachments/assets/d6ede363-3aba-4aaa-9eda-269f558c0df2)

The Arduino is a microcontroller board that reads inputs, like pressing a button or detecting light from a sensor, and turns it into an output, like lighting up an LED. 

([What is Arduino?](https://docs.arduino.cc/learn/starting-guide/whats-arduino/) )

### Digital Pins
![Arduino-Uno-Pinout-1](https://github.com/user-attachments/assets/2ab2d359-c7ed-4729-a779-0136e3759959)
Digital pins on an Arduino can be configured as either input or output. There are 14 digital I/O pins, 6 of which can be used as PWM outputs. Digital pins can have two distinct values: HIGH (1) or LOW (0). You can change the pin state using `digitalWrite()` or `analogWrite()`.

([Digital Pins](https://docs.arduino.cc/learn/microcontrollers/digital-pins/))

```
void setup() {
  // Set up pin 11 as an output
  pinMode(LED_PIN, OUTPUT);
} // end of setup()
```
#### The difference between `digitalWrite()` and `analogWrite()` 
`digitalWrite()` sets the digital pin to either HIGH or LOW, while `analogWrite()` applies Pulse Width Modulation (PWM) to simulate varying voltage levels (0-5V) by creating an on-off pattern. PWM cycles every 2 milliseconds, and the pin value can be set between 0 and 255 to control the output. 
([Basics of PWM (Pulse Width Modulation)
](https://docs.arduino.cc/learn/microcontrollers/analog-output/))
```
//turn pin 12 on (high) using digitalWrite()
  digitalWrite(LED_PIN , HIGH);
// Set up pin 13 to 50% brightness using analogWrite()
  analogWrite(LED_PIN, 127); 
```
![image_thumb11](https://github.com/user-attachments/assets/049496de-7262-4992-989e-81aec74645db)

### Breadboard
![Breadboard-Pinout](https://github.com/user-attachments/assets/f240af38-34df-4cbc-9688-d69f349f4dd3)


Breadboards are used to build prototypes of electronic circuits and test whether they work. The breadboard has three key sections: the power rail, ground rail, and circuit area. 
([components101](https://components101.com/misc/breadboard-connections-uses-guide))
### Resistor
![image](https://github.com/user-attachments/assets/072b7fd4-5146-4b56-ac53-c313d34f75a6) 
([© Copyright 2006 Blue Point Engineering](https://neurophysics.ucsd.edu/courses/physics_120/resistorcharts.pdf))

Resistors limit current flow in a circuit, much like a dam slows the flow of water. This prevents components like LEDs from receiving too much power. I used 220-ohm resistors in the LED circuits.


![41PGLUlslDL](https://github.com/user-attachments/assets/eec328fb-3ff3-4278-b8f0-9c4c45119634)

### LED
Light Emitting Diodes (LEDs) provide visual feedback in a circuit. LEDs have two legs: the cathode (short leg, -) is connected to the ground rail, and the anode (long leg, +) is connected to the circuit area


![400px-LED_With_Schematic_Symbol_and_Labels](https://github.com/user-attachments/assets/5d7e8f59-6313-4fe7-9c1f-7d0cd8423d60)

([carnegie mellon university](http://cmra.rec.ri.cmu.edu/products/electronicsv2/basic_components/what_is_an_led/1/vid1.html))

### Wires

![45040-dscn0624-400x300](https://github.com/user-attachments/assets/8e0e3ed5-7258-417d-9070-d3c0c4cc7026)

([Exploring Arduino](https://www.exploringarduino.com/parts/jumper-wires/))

Jumper wires connect the arduino with the external  components and vice-versa.
## Tinkercad Simulator
All the digital circuits are made using [Tinkercad](https://www.tinkercad.com/). Tinkercad is a free web app for 3D design, electronics, and coding.

## Electronics
This section discusses the concepts in electronic circuits that are realted to prototyping arduino circuits.
### Ohm`s Law
Ohm's law describes the relationship between voltage, current, and resistance in a circuit.

|Symbol  |Term      |Unit     |
|:------:|:--------:|:-------:|
| V      |Voltage   | Volts   |
|I       |Current  | Amperes |
|  R     |Resistor  | Ohms    |


<img width="364" alt="Simple_electrical_schematic_with_Ohms_law" src="https://github.com/user-attachments/assets/5309a3c2-72e6-4ca4-8d4b-3eac2056be39"> 

([File:Simple electrical schematic with Ohms law.png
](https://en.m.wikipedia.org/wiki/File:Simple_electrical_schematic_with_Ohms_law.png))

## Circuits
This section is about circuits implementations.
### On/Off LED Circuit
The objective of the circuit is to implement an on/off LED loop. 
#### Components
- Arduino Uno R3.
- Breadboard.
- 220ohm resistor.
- LED
- Jumper Wire
#### Code
```
// C++ code
//
//The code sets pin 12 as an output and turn it on/off 
//with a one second delay

//Define pin 12 as a constant
#define LED_PIN 12  
void setup()
{
  //set up pin 12 as an output
  pinMode(LED_PIN , OUTPUT); 
}

void loop()
{
  //turn pin 12 on (high)
  digitalWrite(LED_PIN , HIGH); 
  // Wait for 1000 milliseconds (1 second)
  delay(1000);
  //turn pin 12 off(low)
  digitalWrite(12, LOW);
  //wait for 1000 milliseconds (1 second)
  delay(1000); 
}
```
#### Digital Circuit
![image](https://github.com/user-attachments/assets/dfcadb87-2733-4dfa-90f6-c8f148cdd65d)
[Tinkercad link](https://www.tinkercad.com/things/6mtscSBUH3T-1led-and-1resistor-circuit?sharecode=A88vDCyh6bdy0jNWU5W7For1Mzw2JRQiKFfG-1IOvtw)
#### Physical Circuit

#### Bug report
Poor indentation  and commenting at the first version of the code which made it hard to read.

### Fade in/out LED Circuit
he objective of the circuit. is to make the LED fade in/out.
#### Components
- Arduino Uno R3.
- Breadboard.
- 220ohm resistor.
- LED
- Jumper Wire
#### Code
```
// C++ code
//
// The code makes the LED pin fade in/out by
// using digital PWM pin number 11

// Define pin 11 as a constant
#define LED_PIN 11  

void setup() {
  // Set up pin 11 as an output
  pinMode(LED_PIN, OUTPUT);
} // end of setup()

void loop() {
  //Increase the brightness of the LED (from 0 to 255)
  for (int i = 0; i <= 255; i++) {
    // increment pin 11 value to increase brightness
    analogWrite(LED_PIN, i); 
    // Wait for 5 milliseconds before increasing brightness
    delay(5); 
  }

  //Decrease the brightness of the LED (from 255 to 0)
  delay(1000);  
  // Gradually decrease the brightness of the LED (from 255 to 0)
  for (int i = 255; i >= 0; i--) {
    // decrement pin 11 value to decrease brightness
    analogWrite(LED_PIN, i); 
    // Wait for 5 milliseconds before decreasing brightness
    delay(5); 
  }

  // Wait for 1000 milliseconds (1 second) after reaching zero brightness
  delay(1000);  
}//end of loop()

```
#### Digital Circuit
![image](https://github.com/user-attachments/assets/86588ee4-0dba-44cd-9b1a-f0a02ac90b61)

[Tinkercad link](https://www.tinkercad.com/things/fcb8VSDf7Mx-fade-in-out-led?sharecode=yD5MbceEbOKH0mRyDnn8-NINcv56IyzxM4bcpRsiwLc)

#### Physical Circuit
#### Bug report
I needed to add one second delay for the digital version to see the LED fading
