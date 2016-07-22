# The Tilt Sensor
Tilt sensors are another sensor that you can experiment with. The _tilt sensor_ is a great way to integrate some motion sensing into a project without having to buy a much more expensive component such as an _accelerometer_.

## Introducing the Tilt Sensor
While an accelerometer has a range of input information to work with, the tilt sensor communicates two states: HIGH and LOW. This makes the tilt sensor similar in function to a pushbutton.

Here's an image of the tilt sensor from [Sparkfun Electronics](http://www.sparkfun.com):

![Tilt Sensor - Sparkfun](https://cdn.sparkfun.com//assets/parts/4/6/8/5/10289-01.jpg)

The tilt sensor has a tiny metal ball inside the cylinder, and when the ball falls into position, the legs become connected. This is similar to how the pushbutton legs are connected once the button is pushed.

You can detect changes in orientation by reading the state of the sensor. Let's work through a sample project!

## Project: Motion Triggered Lights
For this basic project, you're going to be controlling a series of LEDs by changing the orientation of the breadboard. This project example introduces the functionality of the tilt sensor as well as some new code!

### Supplies
- Uno board and breadboard
- Jumper wires
- Tilt sensor
- 10k Ohm resistor for the tilt sensor
- LEDs (you can choose how many)
- 220 or 560 Ohm resistor _for each LED_

### Steps
The steps for this project are split between the circuit setup and the sketch itself. Since this sketch introduces new commands, there will also be a section explaining each new command.

#### Circuit
Refer to this _fritzing diagram_ for the circuit setup:

![Tilt Sensor- Fritzing](http://i.imgur.com/hJ1g1xp.png)

1. Connect the Arduino **5V** to the **+ rail** on the breadboard.
2. Connect the Arduino **GND** to the **- rail** on the breadboard.
3. Connect one leg of the **tilt sensor** to the **+ rail** on the breadboard.
4. Attach a 10k Ohm resistor between other leg of the **tilt sensor** and the **- rail** of the breadboard
5. Connect the leg of the **tilt sensor** that has the 10k resistor to the input pin. In this example, it's pin 2.
6. For each LED, connect the positive leg (long leg) to an Arduino pin.
7. For each LED, attach a 220 or 560 Ohm resistor from the negative leg (short leg) to the **- rail**.

_Note_: The digital input connection for the tilt sensor should be placed on the breadboard in between the 10k resistor and the tilt sensor leg.

#### Sketch

Here is a basic sketch for the tilt sensor. This will make the LEDs change state as the tilt sensor changes state. There are some new concepts used in this code, and there will be some 'going further' challenges as well.

Parts of this sketch are based on the sketch used in the Adafruit tilt sensor lesson.

```arduino
int sensorPin = 2; //pin where tilt sensor connects
int ledPinOne = 4; //make an LED connection var for each LED
int ledPinTwo = 5;
int ledPinThree = 6;
int ledPinFour = 7;
int switchState = 0; //current state of the tilt sensor
int LEDstate = HIGH; //variable to store the state of the LEDs
int tiltValue; //variable to store the value read from the pin
int previous = LOW; //variable to store the previous state of the pin

unsigned long time = 0; //tracks how long since the last change of state
unsigned long debounce = 50; //sets an initial value for the debounce variable.
//debounce is used to check twice (in this case within 50 ms) to make sure the sensor has triggered

void setup() {
  pinMode(sensorPin, INPUT); //set the sensor for input
  digitalWrite(sensorPin, HIGH); //initialize the tilt sensor to be on
  pinMode(ledPinOne, OUTPUT); //set the LEDs for output
  pinMode(ledPinTwo, OUTPUT);
  pinMode(ledPinThree, OUTPUT);
  pinMode(ledPinFour, OUTPUT);
}

void loop() {
  tiltValue = digitalRead(sensorPin);

  if (tiltValue != previous) {
    time = millis();
  }

  if ((millis() - time) > debounce) {
    switchState = tiltValue;

    if (switchState == HIGH)
      LEDstate = LOW;
     else
      LEDstate = HIGH;
    }

  digitalWrite(ledPinOne, LEDstate);
  delay(100);
  digitalWrite(ledPinTwo, LEDstate);
  delay(100);
  digitalWrite(ledPinTwo, LEDstate);
  delay(100);
  digitalWrite(ledPinThree, LEDstate);
  delay(100);
  digitalWrite(ledPinFour, LEDstate);
  delay(100);

  previous = tiltValue;
}
```
Much of the code is familiar, but let's break down the overall gist of the sketch:

There are several global variables that are being set. Most of these are familiar. One that is new is the _LEDstate_ variable, which is either going to be HIGH or LOW. This is used for toggling the state of the LEDs later in the sketch.

The _previous_ variable is used to track the last state of the tilt sensor.

The code inside the **void setup()** is pretty familiar - you're just assigning the pins their associated modes.

The core of the sketch is inside the **void loop()**. The first step is to read the value of the tilt sensor.

Once a change is detected, the value of **millis()** is saved inside a variable called _time_. There is then a check to see if the tilt sensor has been triggering for longer than the debounce value, and if it has, the state changes.

Next, there is some conditional logic to determine the state of the LEDs based on the state of the tilt sensor. This is similar to the logic used in the _pushbutton_ project.

The LEDs are then set to the appropriate state by using the _LEDstate_ variable.

At the end of the loop, the current state is stored in the _previous_ variable.

### New Commands
- **unsigned long** is a type of variable that is meant to store long numbers. Since the time and millis values can become quite long, this type is used.
- **millis()** is a command that returns the number of seconds that the current Arduino program has been running.
- **debounce** is a new concept. Note that debounce is the variable name. Debouncing is when an input is checked twice within a (typically) short period of time to make sure that the input has been triggered. In this example, the debounce variable is being used to check to make sure that the tilt sensor has actually changed states.

<hr/>

### Going Further
After you understand the concepts used in this project, you should experiment with changing the values of the LEDs.

Remember, the tilt sensor is similar in functionality to a pushbutton, so any of the challenges you did with buttons can apply to this as well!

Try to come up with some inventive ways to incorporate a tilt sensor into your experiments!
