<!--
# Digital vs Analog
In the _Blinking LED Experiment_ you used <em>digital</em> output, but that's not the only type of output: you can also perform analog output. The difference between the two is best shown using a light switch. With _digital output_, we have two options on or off, or as the method **digitalWrite()** refers to them, HIGH and LOW.

![Light Example](http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/04/06222027/lightswitch-205x300.jpg)

But what if we want a switch that could control the brightness of our light and have a range of "on-ness" rather than being so finite. In that instance we are going to want to use <em>Analog</em> output.

![Dimmer Switch](http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/04/06222259/dimmer_switch-300x274.jpg)
-->
## Analog Out and the Arduino
The Arduino platform is primarily a digital platform so the voltage coming out of the pins is always the same which makes analog a little more difficult to do. The Arduino uses a trick where it cycles the power on and off very quickly on a pin in order to generate a voltage that varies in strength. This is called [Pulse Width Modulation](https://www.arduino.cc/en/Tutorial/PWM) or _PWM_ for short. Only certain pins on the Arduino support _PWM_ so if you need Analog Out, you will want a pin with a squiggly line near it:

![Arduino PWM Pins](http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/04/06223159/Arduino_PWM_Pins-small-600x384.jpg)

## Introducing analogWrite()
When you were working with digital output, you used digitalWrite(). Now that you're working with analog output, you will use _analogWrite()_. Let's take a look:

```arduino
int ledPin = 9; // the pin with the LED. this pin allows for PWM ~
int val = 255; //  the initial value to write.  

analogWrite(ledPin, val); // writes the value 255 to pin 9</pre>
```

**analogWrite()**: This command takes two parameters for input- the pin and the value to write.
- The pins available for analog output are marked with the <strong>~</strong> symbol. On the Arduino Uno board, these are pins 3, 5, 6, 9, 10, and 11.
- The value must be between 0 and 255.

This value controls how "on" the pin is. A value of 0 turns the pin **off** and a value of 255 means completely **on**. Any values in between 0 and 255 result in different levels of brightness. This is used to create a fading effect.

Now that you have the basic understanding of analog output, let's try a project: the Fading LED.

## Project: Fading LED
For this experiment, you're going to setup a circuit and create a new sketch that controls the brightness of an LED.

### Supplies:
- Uno board and breadboard
- Jumper wires
- LED of your choice
- 220 or 560 Ohm resistor

### Circuit Setup:
Setup your breadboard like this:

![Analog Output - Fading LED](http://dhf-website.s3.amazonaws.com/images/ArdExp-fadingLED_bb.jpg)


1. Connect the **Arduino GND** to the **- rail** on the breadboard.
2. Connect the positive leg of the LED to an **Arduino PMW Pin (~)**. In this example, pin ~9 is used.
3. Connect a 220 or 560 Ohm resistor from the negative leg of the LED to the **- rail**.

### Resistor?
You might be wondering why there is a resistor between our LED and the GND column. This is the proper way to setup this circuit.

When you did the simple Blinking LED, you turned the LED off at pretty fast rate and the aim was for you to start quickly.

This resistor should be in place to help absorb any left over current coming from the LED and reduce it to 0 to protect the Arduino.

### The Sketch:
Create a new sketch with the following code and upload it to your Arduino. You should see your LED light up in 4 different brightnesses: off, 25% on, 50% on, 75% on, and 100% on.

```arduino

void setup() {

  int ledPin = 9;
}

void loop() {
  analogWrite(9,0); //Turn the LED on pin 9 off
  delay(500); //Wait 500 milliseconds
  analogWrite(9,63); //Turn the LED on pin 9 25% on
  delay(500); //Wait 500 milliseconds
  analogWrite(9,126); //Turn the LED on pin 9 50% on
  delay(500);
  analogWrite(9,189); //Turn the LED on pin 9 75% on
  delay(500);
  analogWrite(9,255); //Turn the LED on pin 9 100% on
  delay(500);
}
```

## Bonus Challenge: Reverse Fade!

Here is a challenge to help you understand some of the concepts we have learned so far. To see the answer to the challenge, you can expand the code snippet in the next section.

Right now the code sketch results in the LED fading from off to max value. Your challenge is to make the LED **fade from max back to off**.

Attempt this first on your own and then look at the solution when you're ready.

### Challenge Solution

```arduino
void setup() {
  //No need for setup this time
}

void loop() {
  analogWrite(9,0); //Turn the LED on pin 9 off
  delay(500); //Wait 500 milliseconds
  analogWrite(9,63); //Turn the LED on pin 9 25% on
  delay(500); //Wait 500 milliseconds
  analogWrite(9,126); //Turn the LED on pin 9 50% on
  delay(500);
  analogWrite(9,189); //Turn the LED on pin 9 75% on
  delay(500);
  analogWrite(9,255); //Turn the LED on pin 9 100% on
  delay(500);
  analogWrite(9,189); //Turn the LED on pin 75% off
  delay(500); //Wait 500 milliseconds
  analogWrite(9,126); //Turn the LED on pin 9 50% on
  delay(500); //Wait 500 milliseconds
  analogWrite(9,63); //Turn the LED on pin 9 25% on
  delay(500);
  //If we left the next two lines on, then the LED would be off for 1000 milliseconds
  //because the loop would start back over and it would start with a duplicate of the lines below
  //analogWrite(9,0);
  //delay(500);
}
```
