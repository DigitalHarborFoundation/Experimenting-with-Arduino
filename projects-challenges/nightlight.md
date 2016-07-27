# Night Light
For this project, you'll be creating a night light!

## Base Activity
This project extends what you did with the _photoresistor_. The goal is to work through some of the challenges and/or to build out a physical case for the night light!

Night lights are a common project to practice working with the _photoresistor_, and there are several projects that build on the base concept with slight variations. The goal of these _experimenter challenges_ will be to test out some new concepts, with both the circuit as well as the sketch.

## Supplies
The supplies are largely the same as what you used in the _photoresistor_ circuit.

Here's what you'll be using:
- Uno board and breadboard
- Jumper wires
- Photoresistor
- 10k Ohm resistor for the photoresistor
- LEDs (as many as you choose, depends on the challenge)
- 220 or 560 Ohm resistor for _each_ LED

### Steps
This project builds on the skills you've used while working with the photoresistor project. The base activity is largely the same whereas the challenges will require some additional insight and experimentation.

![Photoresistor Breadboard Diagram](http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/04/19211012/PhotoResistor-3944.jpg)

The connections are the same as the potentiometer project, except in this the photoresistor replaces the potentiometer. On the broadboard diagram, this box represents the photoresistor:

![Photoresistor Symbol](http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/04/19211010/Analog_Input__Photoresistors___Breadboard.jpg)

#### Circuit

1. Connect the 5V of the Arduino to the + rail of the breadboard.
2. Connect the GND of the Arduino to the - rail of the breadboard.
3. Attach the photoresistor to the breadboard. The legs of the photoresistor are the same so you don't need to worry about which leg is which, you just need to make sure that they're connected as shown on the breadboard.</li>
4. Place the 10kOhm resistor between the power rail and the top leg of the photoresistor.</li>
5. Place 1 jumper wire between the 10kOhm resistor and the top leg of the photoresistor. Connect this jumper wire to the A0 pin on the Arduino board. This is the _voltage divider circuit_.
 	- Look at the breadboard row where the top leg of the photoresistor is connected. Your board should have the 10kOhm resistor going from the power rail to the row with the top of the photoresistor in it, and then next would be the jumper wire that is connected to A0, and then finally the top leg of the photoresistor.
6. Use 1 jumper wire to connect the ground rail to the bottom leg of the photoresistor.

#### Sketch
The base sketch for the _night light_ is the same as you used in the potentiometer and photoresistor projects. The key will be to modify the sketch to meet the goals for each challenge.

```arduino
int ledPin=9; //Variable to store pin of LED
int potentPin=A0; //Variable to store pin of photoresistor
int potentValue=0; //Variable to store last known value of photoresistor
int brightnessValue=0; //Variable to store LED brightness

void setup() {
  // put your setup code here, to run once:
  pinMode(ledPin, OUTPUT); //Setup LED pin for output
}

void loop() {
  // put your main code here, to run repeatedly:
  potentValue=analogRead(potentPin); //Read the value of the photoresistor pin
  brightnessValue=map(potentValue,0,1023,0,255); //Map the photoresistor value to a brightness
  analogWrite(ledPin,brightnessValue); //Set the brightness of the ledPin
}
```

## Night Light: Experimenter Challenge

The example sketch provides the basic functionality for the night light. There are several things that you can modify once you understand the concepts involved.

Here are some suggestions:

- Create a physical interface for your night light. Try out various materials to see if you can increase the radius of the light. Additionally, experiment with materials to see if you can create _diffusion_.
- Add a _serial monitor_ to track the photoresistor value.
- Add more than 1 LED and have them trigger at different points. Perhaps if it isn't completely dark, only one LED comes on whereas if it's totally dark, more than one LED is activated.
    - Additionally, try to figure out how to integrate a _timer_ so that the night light will shut off after so many seconds of activity! This challenge will require some additional skills, but you can figure it out with some Googling or through accessing the [Arduino Reference](https://www.arduino.cc/en/Reference/HomePage).
