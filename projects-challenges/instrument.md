# Music Instrument
This experiment is rather open-ended. The goal is to combine a variety of components with the _piezo element_ with the end result being a music instrument.

Think of the piezo as being the required output, and that you can choose from all of the sensors you've used as the input.

Remember, you can use more than one input! Think about what you would want your instrument to do and then work backwards from there.

## Base Activity
The base activity for this is to create an instrument using _at least two_ sensors for input, and the _piezo element_ for the tone output.

The sensors that you use are up to you. An example that meets the goals of this challenge is the _basic theremin_ project. Think of this _experimenter challenge_ as a way of building on that basic concept and extending it by including more than one input source.

## Supplies
- Uno board and breadboard
- Jumper wires
- Piezo element
- Additional sensors of your choice!
    - Suggestions: photoresistor, potentiometer, FSR, tilt sensor, pushbutton
    - Make sure to use the correct resistor where needed! Consult the project guides for each component if you're not sure.

### Steps
Much of this project is open-ended. You'll be designing and building your own instrument, so make sure to plan out the functionality of your instrument and then determine what components are necessary to realize your vision!

#### Circuit
The circuit will depend on what you'd like to include in the instrument. However, you'll want to start with either the _basic theremin_ or the example project from the _Sound_ lesson. Here is the circuit sketch from that lesson.

Refer to this _fritzing diagram_ for the circuit setup:

![Piezo Fritzing Diagram](http://i.imgur.com/3NnMOtYg.png)

1. Connect the Arduino **5V** to the **+ rail** on the breadboard.
2. Connect the Arduino **GND** to the **- rail** on the breadboard.
3. Connect one leg of the **piezo** to the **- rail** on the breadboard.
4. Connect one leg of the **piezo** to a **digital pin** on the Arduino. In this example, the connection is to **digital pin 9**.

#### Sketch
Here's the sketch from the example project in the sound lesson:

```arduino
/*
* Adafruit Arduino - Lesson 10. Simple Sounds
* Note (from Jonathan): This will continue to play the loop while
* the Arduino has power! The idea is to introduce the tone command.
* If you're tired of the sound and just want it to play ONE time,
* see if you can figure out what to uncomment.
*/

int speakerPin = 9;

int numTones = 10;
int tones[] = {261, 277, 294, 311, 330, 349, 370, 392, 415, 440};
//            mid C  C#   D    D#   E    F    F#   G    G#   A

void setup(){

}

void loop(){
    for (int i = 0; i < numTones; i++){
      tone(speakerPin, tones[i]);
      delay(500);
      //noTone(speakerPin);
  }
}
```

If you need a refresher on how to attach sensors to this project, refer to how the photoresistor was added to the theremin.

## Music Instrument: Experimenter Challenge
While the design and functionality of the instrument is up to you, here are some suggestions to get you started.
