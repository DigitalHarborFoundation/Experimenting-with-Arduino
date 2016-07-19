# Beyond the Button
Now it's time to experiment with buttons, servos, and LEDs! Button projects will all use the same basic circuit and code outlined in the previous article. The challenge is to explore and experiment with seeing what different devices you can control!

## Base Activity:
Connect a pushbutton to the board, and write a program to have it control something. What it controls is entirely up to you!

### Supplies:
- Uno board and breadboard
- Jumper wires (at least 4)
- Pushbutton
- Optional: LED
- Optional: Servo
- 10K Ohm resistor
- 220 Ohm or 560 Ohm resistor (for the LED)

### Experimenter Challenges
Once you've built your basic pushbutton circuit, you should connect it to either an LED or a servo. You could even experiment with connecting it to BOTH components!

Here are some ideas:
- Turn a servo on/off with the push of a button.
    - Extend this into a button controlled fan.
- Trigger a light pattern while the button is pressed. Think about integrating delay values into the button code.


### Super Level-Up
Instead of having the button act as a _momentary switch_, use what you've learned about _conditional statements_ to create a button state.

Instead of having to hold the button down, once the button is pressed it has an ON state and once it's pressed again, it switches to an OFF state.

Use the basic conditional code from the previous article to get started.

Here are some helpful tips:
- Use **digitalRead(pin)** to check the state of the pin.
- Use conditional logic to evaluate the following: _if the button is pressed, the state is set to HIGH. if it's pressed again, the button state is set to LOW_ and experiment from there.
    - If you need help, ask!

You can use this concept to create a servo or LED that activates at the push of a button!

As a super challenge, could you find a way to make it so that the LED is OFF while the servo is ON? 
