# The Force Sensitive Resistor (FSR)
The Force Sensitive Resistor (FSR) is a sensor that detects physical pressure. [Adafruit Learn](https://learn.adafruit.com/force-sensitive-resistor-fsr/overview) has an excellent overview of the FSR and you should definitely check it out if you're looking for a more information about the sensor.

## Introducing the FSR
The pressure that the FSR detects can come in several forms, but two common ones are squeezing and weight.

The input that comes from the FSR is similar to what you receive from a photoresistor in that it will return a range of inputs.

The FSR is a thin component that has a circular head. Here's an image of the FSR from [Sparkfun Electronics](http://www.sparkfun.com):

![FSR - Sparkfun](https://cdn.sparkfun.com//assets/parts/2/9/6/7/09375-1.jpg)

## Project: Light Force!
This project is similar to the _Fading LED_ except instead of using the photoresistor or potentiometer to change the LED's brightness, you'll be using the FSR! The FSR is a great component that can be included in a variety of projects once you understand the basic functionality.

### Supplies
- Uno and breadboard
- Jumper wires
- LED
- 220 or 560 Ohm resistor for the LED
- FSR
- 10k Ohm resistor for the FSR

### Steps
The steps for this project are split between the circuit setup and the sketch itself. The sketch is a basic project designed to get you up and running with this new sensor.

#### Circuit
Refer to this _fritzing diagram_ for the circuit setup:

![FSR-Fritzing Diagram](http://i.imgur.com/RGQD56C.png)

1. Connect the Arduino **5V** to the **+ rail** on the breadboard.
2. Connect the Arduino **GND** to the **- rail** on the breadboard.
3. Connect one leg of the **FSR** to the **+ rail** on the breadboard.
4. Attach a 10k Ohm resistor between the **-- rail** and the other leg of the **FSR**.
5. Connect the FSR leg with the 10k resistor to **Arduino: A0** pin. The connection should look like this:
    - 10k resistor from - rail to B, jumper to A0 on C, and FSR leg on E. The A0 connection is placed between the resistor and the FSR leg.

#### Sketch
Here's the basic sketch to get up and running with the FSR. Experiment with changing some of the values. The serial monitor is included so that you can monitor the input values from the FSR.

```arduino
//declare global variables

int fsrPin = 0; //fsr is connected to analog 0
int ledPin = 11; //led is connected to pin 11 (pwm)
int fsrReading; //analog reading from the fsr
int ledBrightness;

void setup() {
  Serial.begin(9600); //setup the serial monitor for debugging
  pinMode(ledPin, OUTPUT); //set the led pin to output
}

void loop() {
  fsrReading = analogRead(fsrPin); //read the value from the analog pin
  Serial.print("FSR Reading = ");
  Serial.println(fsrReading);

  /*
   *  we need to use map to change the range from the analog reading to the
   *  brightness of the LED, just like with the photoresistor and potentiometer projects
   */

  ledBrightness = map(fsrReading, 0, 1023, 0, 255); //map the analog values to the brightness
  //press harder -> brighter LED!
  analogWrite(ledPin, ledBrightness);
  delay(100); //delay the writing slightly  
}
```

<hr/>
### Going Further
Now that you have a basic understanding of how to setup the FSR circuit, go ahead and begin integrating it into some of your other circuits!

For starters, check out the _Experimenter Challenge_ for the FSR. 
