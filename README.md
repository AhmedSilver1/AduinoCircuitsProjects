# Arduino Circuits Projects

## Table of content
- [Overview](#overview)
- [Arduino Components](#getting-started-with-arduino-components)
- [Tinkercad Simulator](#tinkercad-simulator)
- [Circuits](#circuits)
  - [On/Off LED Circuit](#onoff-led-circuit)
  - [Fade In/Out LED Circuit](#fade-inout-led-circuit)
## Overview   

This repository documents my learning process in implementing Arduino circuits, using digital and physical circuits to implement seneors and output components.



## Getting Started with Arduino Components

### Arduino UNO R3
![s-l400](https://github.com/user-attachments/assets/d6ede363-3aba-4aaa-9eda-269f558c0df2)

Arduino is a microcontroller board that reads inputs like a push of a button or light on a senors, and turn it into an output like turning on an LED.([What is Arduino?](https://docs.arduino.cc/learn/starting-guide/whats-arduino/) )

### Digital Pins
![Arduino-Uno-Pinout-1](https://github.com/user-attachments/assets/2ab2d359-c7ed-4729-a779-0136e3759959)
Pins in Arduino can be configured as either input or output. It has 14 digital input/output pins, 6 of them can be usd as PWM output. Digital pins have two distinct values: HIGH(1) or LOW(0). You can cahnge the state of pins to achive the desired input or output. Changing the value of the pin can be done by using digitalWrtie(), or analogWrite(). ([Digital Pins
](https://docs.arduino.cc/learn/microcontrollers/digital-pins/))

```
void setup() {
  // Set up pin 11 as an output
  pinMode(LED_PIN, OUTPUT);
} // end of setup()
```
#### The difference between digitalWrite() and analogWrite() 
Digitalwrite() allow you to set the digital pin to HIGH or LOW only. While analogWtite() apply Pulse Width Modulation(PWM) to create an on-off pattern that can simulate voltages between 5v and 0v. This is done in 2miliseconds cycles where you can set the pin between 0 and 255 during the duty cycle. ([Basics of PWM (Pulse Width Modulation)
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


Breadbaord are used to build prototypes of electronic circuits to test if it works or not. ([Breadboard](https://en.wikipedia.org/wiki/Breadboard)) The breadboard is divided to three parts. The power rail, the ground rail, and the circuits area
([components101](https://components101.com/misc/breadboard-connections-uses-guide))
### Resistor
![image](https://github.com/user-attachments/assets/072b7fd4-5146-4b56-ac53-c313d34f75a6) 
([© Copyright 2006 Blue Point Engineering](https://neurophysics.ucsd.edu/courses/physics_120/resistorcharts.pdf))

Resistors work like a dam in a river. Just like a dam slows down the water flow, a resistor slows down the flow of electricity in a circuit. This helps make sure that the components only get the right amount of power, preventing them from getting too much. I used 220Ohm for the LED circuits.

![41PGLUlslDL](https://github.com/user-attachments/assets/eec328fb-3ff3-4278-b8f0-9c4c45119634)

### LED
Light Emitting Diode is mainly used to provide visual feedback in a ciruit. The LED have two legs Cathode(short leg), and Anode(long leg). The Cathode is the (-) where you connect it to the ground rail, while the anode is the (+) where you connect it to the circuits area. 


![400px-LED_With_Schematic_Symbol_and_Labels](https://github.com/user-attachments/assets/5d7e8f59-6313-4fe7-9c1f-7d0cd8423d60)

([carnegie mellon university](http://cmra.rec.ri.cmu.edu/products/electronicsv2/basic_components/what_is_an_led/1/vid1.html))

### Wires

![45040-dscn0624-400x300](https://github.com/user-attachments/assets/8e0e3ed5-7258-417d-9070-d3c0c4cc7026)

([Exploring Arduino](https://www.exploringarduino.com/parts/jumper-wires/))

Jumber wiers connect the arduino with the external  components and vice-versa.
## Tinkercad Simulator
All the digital circuits are made using [Tinkercad](https://www.tinkercad.com/). Tinkercad a is a free web app for 3D design, electronics, and coding.

## Electronics
This section talk about the concepts in electronic circuits that are realted to prototyping arduino circuits.
### Ohm`s Law
Ohm`s law till us the electric Current through a wire in  a ciruit. 
|Symbol  |Term      |Unit     |
|:------:|:--------:|:-------:|
| V      |Voltage   | Volts   |
|I       |Curttent  | Amperes |
|  R     |Resistor  | Ohms    |


<img width="364" alt="Simple_electrical_schematic_with_Ohms_law" src="https://github.com/user-attachments/assets/5309a3c2-72e6-4ca4-8d4b-3eac2056be39"> 

([File:Simple electrical schematic with Ohms law.png
](https://en.m.wikipedia.org/wiki/File:Simple_electrical_schematic_with_Ohms_law.png))

## circuits
This section is about circuits implementations.
### On/Off LED Circuit
The objective of the circuit is to implement an on/off LED loop. 
#### Components
- Arduino Uno R3.
- Breadboad.
- 220ohm resistor.
- LED
- Jumper Wire
#### Code
```
// C++ code
//
//The code sets pin 12 as an output and turn it on/of 
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
Poor indentation  and commenting at the first version of the code witch made it hard to read.

### Fade in/out LED Circuit
The objective of the ciruit is to make the LED fade in/out.
#### Components
- Arduino Uno R3.
- Breadboad.
- 220ohm resistor.
- LED
- Jumper Wire
#### Code
```
// C++ code
//
// The code make the LED pin fade in/out by
// using digttal PWM pin number 11

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
