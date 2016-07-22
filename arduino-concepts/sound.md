# Making Sound with Arduino
In addition to all the other great things you've controlled so far with the Arduino, you're also able to work with sound! Incorporating the _piezo element_ will open up exciting new possibilities and enable you to create your own Arduino music instruments!

Up to this point you've manipulated light by programming LEDs and reading input from a photoresistor. You've worked with motion through reading the input of a potentiometer as well as programming the turns and steps of a servo motor. Now you're going to enter into a world of experimentation that is totally new: sound and audio!

## Introducing the Piezo Element
When working with sound, you'll first need to attach some form of speaker component to the Arduino. One of the most commonly used is the _piezo element_. The piezo is attached to one of the Arduino's digital pins, and it produces a beep when it receives a pulse of current. To generate different pitches, the pulse is sent at different _frequencies_. Once you start pulsing at these frequencies, the piezo's beeps will blend together and generate tones.

The core component that you'll use in this process is the piezo element. It's a small black disc with two legs. Here's a picture of one from [Adafruit](http://www.adafruit.com):

![Piezo Element](https://cdn-learn.adafruit.com/assets/assets/000/002/295/medium800/learn_arduino_piezo_sounder.jpg)

Connecting a piezo is similar to how you connect an LED. One of the legs attaches to GND and the other to a digital pin.

### Project: Make Some Sound
For the introduction to the piezo, you're going to be using an example sketch provided by Adafruit.

### Supplies
- Uno board and breadboard
- Jumper wires
- Piezo element

### Steps
The steps for this project are split between the circuit setup and the sketch itself. Since this sketch introduces new commands, there will also be a section explaining each new command.

#### Circuit
Refer to this _fritzing diagram_ for the circuit setup:

![Piezo Fritzing Diagram](http://i.imgur.com/3NnMOtYg.png)

1. Connect the Arduino **5V** to the **+ rail** on the breadboard.
2. Connect the Arduino **GND** to the **- rail** on the breadboard.
3. Connect one leg of the **piezo** to the **- rail** on the breadboard.
4. Connect one leg of the **piezo** to a **digital pin** on the Arduino. In this example, the connection is to **digital pin 9**.

#### Sketch
This sketch will cover how to output some basic sound from the piezo element. There are several possibilities that you'll be able to experiment with after you understand the structure of the code. Let's check it out!

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

Let's break the code down, and then look at some of the new commands that were introduced.

First, you'll need to create some global variables. These are outside of **void setup()** so that you'll be able to access them inside **void loop()**.

One of the variables is _speakerPin_ which is set to the pin that the piezo element is connected to, in this case, it's connected to pin 9. Remember, if you change the pin connection, you'll also need to change it in the code.

Next, the _numTones_ variable stores the total amount of tones that you'll be playing. In this case, there are 10 tones, so this variable has a value of 10.

The last variable, _tones[]_ is actually an **array**. Arrays are similar to variables but hold a list of values instead of a single value. In this case, the _tones_ array contains all the tones that will be used in the sequence.

Now that all the variables and arrays are initialized, the Arduino is ready to output some sound! The actual pattern and emission of sound happens in the **void loop()**, so let's examine the code in that section.

The code is contained within a **for loop()** that iterates through the total number of tones, and plays each tone in sequence.

Remember, the code within the for loop will run for each item in the list, until it hits the end point. In this case, the end point is when the total number of tones have been played.

The **tone()** command is then used to actually play the sound. Let's examine that in further detail since it's a new command!

### New Commands

**tone()** : This is the command for emitting sound from the piezo element, and it takes two arguments. The first is the pin that the sound should be emitted from, in this case it's the **speakerPin** variable that stores the pin number that the piezo is connected to.

The next parameter is the frequency of the tone to be played. In this example, **tones[i]** is used to play the tone for the associated step in the loop. Remember, **i** is the step in the for loop, and the loop is cycling through all of the notes in the original tones array.

Using tones[i] is a way to tell the Arduino that it should play the corresponding item in the array index that matches the step number.

You don't need to play sounds this way. You also could use the following format (but it's less efficient):

```arduino
tone(speakerPin, 440) //this plays a middle A frequency
```

It's good to know both methods of playing sound. Remember, as long as the second argument of _tone()_ is a frequency, you can pass it in however you like.

**noTone()** is the other new command. It's commented out in the code example, but this command terminates the sound being played from the pin that the speaker is connected to. It takes one argument: the speaker pin number. This is used to stop all sound generation.


<hr/>

### Going Further
Now that you know the basics of outputting sound from the Arduino, go ahead and explore some different sequences! Here's some helpful guides that include notes and their corresponding frequencies.

[Arduino Reference: Tone](https://www.arduino.cc/en/Reference/Tone) - This is the official reference page from Arduino.

[Arduino Tutorial: Tone](https://www.arduino.cc/en/Tutorial/ToneMelody?from=Tutorial.Tone) - This tutorial has more detail about using **tone()** in your projects.
