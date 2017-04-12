## LED Flashlight
Now that you've worked with basic digital input with the pushbutton, it's time for a project! This activity will build on the skills you've used in the multi-LED projects as well as the pushbutton lesson.

The core of this activity is to create a circuit where a variety of LEDs will be controlled by a pushbutton. The timing and behavior of the LEDs is completely up to you. The basic concept is that the LEDs will behave one way when the button is OFF (not pressed) and another way when the button is ON (pressed).

One key point to remember is that for every new LED you're using, you'll need to make sure that you have a corresponding output pin set in your code!

## Experimenter Challenge: LED Flashlight
Instead of the state of the LED being solely determined by your code (blinking on and off in a loop), you're going to attach a button so that you can control whether the LED is on or off.

You'll be working from a basic code skeleton. However, for an additional challenge you should write your own code from scratch!

### Supplies:
- Uno and breadboard
- Jumper wires
- LED (start with 1, and then integrate more LEDs after)
- 220 or 560 Ohm resistor for each LED
- Tactile Pushbutton
- 10K Ohm resistor (brown, black, orange) for the button

### Steps:
The steps for this project will be broken into two sections, the circuit setup and the code. Let's setup the circuit first:

#### Circuit:
Refer to this _Fritzing Diagram_:
![Arduino Button](http://dhf-website.s3.amazonaws.com/images/ArdExp-buttonLight_bb.png)

1. Connect the **Arduino 5V** to the **+ rail of the breadboard**.
2. Connect the **Arduino GND** to the **- rail of the breadboard**.
3. Connect both sides of the breadboard: **- rail to - rail** and **+ rail to + rail**.
4. Connect the **pushbutton** so that it straddles the middle notch in the breadboard.
5. Connect the **top leg** of the button to the **+ rail**.
6. Connect the **bottom leg** of the button to the **10K Ohm resistor**.
7. Connect the **other leg of the resistor** to the **- rail**.
8. Connect the **LED** to **Arduino PIN 13** (or whatever pin you set in the code).

#### Code:
1. Navigate to this link and copy the code: [Arduino - Basic Pushbutton](https://gist.github.com/jonathanprozzi/cf8b7669e5653bc1a630e5d2c1ba99e1)
2. **CMD + C** to copy
 - Try to use it as a reference and code it yourself before copying and pasting it.
3. Make a new sketch and paste/enter the code into the new sketch.
3. Make changes to the code, but make sure to pay attention to the **code comments** to guide what you should (and shouldn't!) change.
4. If you change the pin placement of the LED or the button, make sure that your code matches.
5. **Upload** your code to the board and test your button!

### Flashlight: Experimenter Challenges
After completing the base activity and successfully wiring up the LEDs and the button, go ahead and try some of these challenges:

**Challenge One**: Modify the code so that the LEDs turn on in a specific sequence, but only while the button is pressed. Think of this sequence as if it were a secret code, or a Morse code message that you're transmitting! Work with one of your peers to create a unique code and communication device!

**Challenge Two**: Create a physical enclosure for your lights and button, as if you're creating a dashboard or an interface for the lights and buttons. Consider programming the button in such a way that it *powers up* the console once it's activated!

#### Overview:
The goal of this experiment is to develop an understanding of pushbuttons and how they fit within a circuit. Once you've developed an understanding of this process, you'll be able to repeat the button circuit and add it to other projects!

Remember, while this particular project used a button to control LEDs, you could easily swap out other components and make a button that controls something else, such as a servo motor!
