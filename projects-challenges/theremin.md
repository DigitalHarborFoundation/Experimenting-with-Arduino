# Basic Theremin
For this project, you'll be creating a basic theremin!

The theremin is a musical instrument that can be controlled without any physical contact! The theremin typically has one or two antennas that are set to detect the hand position of the performer. The hand movement and position then controls one or more oscillators that are usually linked to the frequency and volume output.

The theremin was invented in 1928 by Leon Theremin, a Russian inventor. It has a distinct, recognizable sound, and was a staple of early film soundtracks due to the eerie sounds that it could generate.

## Base Activity
For this project, you'll be creating a basic theremin using the Arduino! You'll be using the _piezo element_ and the _photoresistor_ to create the basic theremin. There are some additional challenges and options, but these components are the core of the instrument.

## Supplies
The supplies are a combination of what you used for the _piezo element_ synth and the _photoresistor_ circuit.

Here's what you'll be using:
- Uno board and breadboard
- Jumper wires
- Piezo element
- Photoresistor
- 10k Ohm resistor for the photoresistor

### Steps
This project builds on the skills you've used while working with the projects for the piezo and the photoresistor. The steps are split into two parts: circuit assembly and code for the sketch.

#### Circuit

This is the diagram and steps for the basic activity. For the Experimenter Challenges, you may need to build on this basic circuit to solve the problem!

Use this breadboard diagram as your guide:

![Theremin Diagram](http://i.imgur.com/fUH08d0.png)

1. Connect the 5V of the Arduino to the + rail of the breadboard.
2. Connect the GND of the Arduino to the - rail of the breadboard.
3. Attach the _piezo element_ to the breadboard.
4. Connect one leg of the piezo to the - rail of the breadboard.
5. Connect the other leg of the piezo to _digital pin 9_ or whatever other pin that you select. Remember, if you change this pin number you'll need to change it in the sketch as well!
6. Attach the _photoresistor_ to the breadboard.
7. Connect one leg of the photoresistor to the + rail of the breadboard.
8. Place a 10k Ohm resistor from the - rail of the breadboard to the other leg of the photoresistor.
9. Connect the leg of the photoresistor that has the 10k Ohm resistor to _analog input A0_. If you change this input pin, make sure to change it in the code as well.

_Note_: The analog input connection for the photoresistor should be placed on the breadboard in between the 10k resistor and the photoresistor leg.

For example, let's say the photoresistor leg is on 27e on the breadboard. You'd want to place the resistor on 27a and the analog input jumper on 27c.

#### Sketch

The photoresistor input is going to be used to control the pitch of the piezo element. There will be some additional _Experiementer Challenges_ where you'll be able to modify some of the functionality, but the base sketch will be using the photoresistor to control pitch.

The basic code is a slightly modified version of the [Adafruit _Pseudo Theremin_ lesson](https://learn.adafruit.com/adafruit-arduino-lesson-10-making-sounds/arduino-code). Here's the sketch:

```arduino
/*
 * Code based on the Adafruit Arduino Lesson 'Pseudo Thermin' by Simon Monk
 * Adafruit Arduino - Lesson 10. Pseudo Thermin
 * https://learn.adafruit.com/adafruit-arduino-lesson-10-making-sounds/arduino-code
*/

int photoPin = 0; //this is the pin the photoresistor is attached to
int speakerPin = 9; //this is the pin the piezo is attached to

void setup(){

}

void loop(){
  int reading = analogRead(photoPin);
  int pitch = 200 + reading / 4; // no need to map because the value is divided by 4
  tone(speakerPin, pitch);
}
```

This basic sketch doesn't contain any new commands! Instead, it's a combination of several concepts you've used in previous projects. Let's take a moment to look at the code:

Two global variables are created, _photoPin_ which is the pin that the photoresistor is attached to, and _speakerPin_ which is the pin that the piezo is attached to.

There isn't any additional code inside the **void setup()**. The core of the code is inside the **void loop()**.

The first action in the loop is to use **analogRead()** to get a reading from the photoresistor. This value is stored inside a local variable named _reading_.

Next, there is another local variable named _pitch_ that is equal to a base of 200 + the photoresistor reading divided by 4. Having a base value of 200 ensures that the pitch being output is no lower than 200 Hz.

Note that this code doesn't use **map()**.

## Basic Theremin: Experimenter Challenge

The example sketch provides the basic functionality for the theremin. There are several things that you can modify once you understand the concepts involved.

Here are some suggestions:

- Modify the line of code to alter the pitch range. Experiment with changing the values to see what you can do!
- Create a physical interface for your instrument.
- Add a _serial monitor_ to track the photoresistor value as well as the pitch.
- Add a _potentiometer_ to control the volume OR have the potentiometer control the pitch and the photoresistor control the volume!
