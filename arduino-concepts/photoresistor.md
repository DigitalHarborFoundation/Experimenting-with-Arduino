# The Photoresistor
The previous guide introduced the concept of _analog input_ as well as new components such as the _potentiometer_. In this guide, you'll be working with a new component called a _photoresistor_.

Photoresistors are similar to potentiometers in that they are both types of _variable resistors_ and that they can be used in projects as analog inputs. The values of a photoresistor are based on the ambient light, where the amount of resistance decreases as the intensity of ambient light increases.

The photoresistor has only 2 pins instead of the 3 of the potentiometer. As this is the case, you'll need to create a _voltage divider circuit_ to use the photoresistor. You don't need to worry about how to calculate such a circuit from scratch, as most projects that require one will provide guidance on how to create one.

The photoresistor will be used to gather _analog input_ in a similar way that the potentiometer did. Instead of changing the resistance by turning a knob, the level of ambient light will change the resistance amount produced by the photoresistor.

The photoresistor has two pins and has a white colored top with red "squiggly" lines running across the head. Here is a picture of the one in your kit:
![Photoresistor image](http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/04/19211011/pasted-image-small-3936.png)

The polarity of the legs doesn't matter - there isn't a positive or negative leg like the LED. However, you'll need to make sure that you're building out the circuit correctly.

## Project: LED Nightlight


### Supplies

**Reminder**: The 10k Ohm resistor is the brown/black/orange resistor. Here is an image:

![10kOhm resistor](http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/04/19211010/RES-103-DIAG-small-2983.png)

- Uno and breadboard
- Jumper wires
- **(New!)** **Photoresistor**
- 10k Ohm resistor for the Photoresistor
- LED circuit supplies:
    - LED and 220 (or 560) Ohm resistor

### Steps

Use this breadboard diagram as your guide:

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

You can run the same sketch as you did for the potentiometer! This works because the photoresistor is sending output to the A0 analog input on the Arduino. The only difference is that the values are being sent from the photoresistor instead of the potentiometer. If you're having any difficulties, double check to make sure that you've placed the photoresistor correctly and that its connected to A0 on the Arduino.

### New commands
None! This project introduced a new component with no additional code for the sketch.

### Going Further
