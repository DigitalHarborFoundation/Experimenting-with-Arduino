# Flashlight
Now that you've worked with basic _digital input_ with the pushbutton, it's time for a project! This activity will build on the skills you've used in the multi-LED projects as well as the pushbutton lesson.


One key point to remember is that for every new LED you're using, you'll need to make sure that you have a corresponding output pin set in your code!

## Base Activity:
The core of this activity is to create a circuit where a variety of LEDs will be controlled by a pushbutton. The timing and behavior of the LEDs is completely up to you. The basic concept is that the LEDs will behave one way when the button is OFF (not pressed) and another way when the button is ON (pressed).

You'll be working from a basic code skeleton. However, for an additional challenge you should write your own code from scratch!

### Supplies:
- Uno and breadboard
- Jumper wires
- At least 3 LEDs
- 220 or 560 Ohm resistor for each LED
- Pushbutton
- 10K Ohm resistor for Pushbutton

### Steps:
The steps for this project will be broken into two sections, the circuit setup and the code. Let's setup the circuit first:

#### Circuit:
1. Refer to this diagram as you wire your circuit:
2. Connect the 5V and GND of the Arduino to the + and - rails of the breadboard as you've previously done.
3. Complete the LED circuit for as many LEDs as you're including. Here's a reminder of the process:
    - Connect the long leg (+) of the LED to the Arduino pin.
    - Connect a 220 (or 560) Ohm resistor to the short leg (-) of the LED and the - rail of the breadboard.
    - Repeat this process for each LED. Each one will need a unique pin and a resistor!
4. Connect the pushbutton to the lower half of the breadboard, split over the middle gap of the board.
5. Connect the top left leg of the pushbutton to the + rail of the breadboard.
6. Add the 10K resistor from the - rail to the lower leg of the button.
7. Connect the lower leg (and after the resistor) to the _digital input_ pin on the board, such as pin 2.

#### Code:
1. Navigate to this gist and use it as a reference.
2. Try to use it as a reference and code it yourself before copying and pasting it.
3. Follow the comments to modify the code!

### Flashlight: Experimenter Challenges
After completing the base activity and successfully wiring up the LEDs and the button, go ahead and try some of these challenges:

**Challenge One**: Modify the code so that the LEDs turn on in a specific sequence, but only while the button is pressed. Think of this sequence as if it were a secret code, or a Morse code message that you're transmitting! Work with one of your peers to create a unique code and communication device!

**Challenge Two**: Create a physical enclosure for your lights and button, as if you're creating a dashboard or an interface for the lights and buttons. Consider programming the button in such a way that it *powers up* the console once it's activated!

#### Overview:
The goal of this experiment is to develop an understanding of pushbuttons and how they fit within a circuit. Once you've developed an understanding of this process, you'll be able to repeat the button circuit and add it to other projects!

Remember, while this particular project used a button to control LEDs, you could easily swap out other components and make a button that controls something else, such as a servo motor!
