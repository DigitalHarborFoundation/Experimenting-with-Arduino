# Working with Breadboards
The next step in your Arduino experimentation is to start integrating the breadboard. This will greatly expand the amount of projects that you can work with. First, let's examine the breadboard itself.

## What is a Breadboard?
Breadboards allows us to create prototypes of circuits and let us expand beyond the basic footprint of the Arduino. They can come in many shapes and sizes but they all have the same basic functionality.

![Breadboard-Small](http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/04/06124622/Breadboard-small-288x300.jpg)

The edge of a breadboard usually has two columns on each side. One marked with a "+" in red and one marked with a "-" in blue.  These are called power rails. You would normally use these to connect your power source to your breadboard (more on that later). The holes in each column are connected to each other the entire length of the breadboard but the red and blue columns are NOT connected, they are separate.

![Breadboard-Connections-PowerRail](http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/04/06125739/BreadboardConnections-PowerRails.jpg)

The rows on the inner part of the breadboard are one connection with a break in the middle. So hole A1 is connected to hole E1 but NOT to hole F1.

![Breadboard-Connection-Rows](http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/04/06130008/BreadboardConnections-Rows.jpg)

## Jumper Wires

Jumpers are wires that bridge connections between two devices. In this project, we are going to use them to connect our Arduino to our breadboard. You can buy specific jumper wires or you can make your own which is what I recommend doing once you have run out of jumper wires.

![Jumper-wires-Small](http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/04/06131211/Jumper_Wires-small-300x225.jpg)

#### Wire Color?

Contrary to what movies would like you to believe, the wire color means nothing. It can be a useful guide for human beings, but the electronics don't care. I generally try to use red colored wires for power and black or green wires for GND connections. Again, this is a guide and if I run out of red wire, I often substitute for whatever my hand touches first in the box of jumper wires.

## Activity: Putting it all Together
This aim of this activity is to transition your blinking LED project to the breadboard.

### Supplies:
- Uno board & USB cable
- Your modified Blink sketch from previous day
- Breadboard
- 1 jumper wire
- LED pack
- Resistor pack

### Steps:
1. Make sure that your previous Blink sketch is still uploaded to the board. If you're unsure, connect and re-upload the sketch.
2. Plug your LED into any two rows on the breadboard with the long leg (the positive leg) towards the top of the breadboard.
3. Connect a jumper wire from the GND pin on the Arduino to the “-” column on the breadboard.
4. Connect a jumper wire from pin 13 on the Arduino to the same row containing the top leg of the LED.
5. Connect a jumper wire from the same row containing the bottom leg of the LED to the “-” column on the breadboard.

Here is a screenshot showing the completed circuit:

![Blink-Breadboard](https://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/04/06215054/Blink_Breadboard-2-small.jpg)

## Experimenter Challenges
Now that you understand the basics it's time to level up your Arduino & breadboard skills! One of best ways to experiment with this project is to add multiple LEDs to your breadboard.

This is a great time to practice connecting your Arduino code with the changes and additions that you make to the board and circuit.

Remember, each LED is going to need it's own dedicated **pinMode()** and **digitalWrite()** or else it won't work!

### Project Idea: LED Traffic Light
Once you've experimented with the challenge, here's a project that you can try. The idea behind this project is to create a Traffic Light using the same components you've been using.

This project challenge will require you to work with some additional resistors and you'll have to tinker with the Arduino code. Once you complete it, you'll have a much deeper understanding of these concepts!

Don't feel like you're bound to using red, yellow, and green LEDs! You should use three unique colored LEDs, but the colors that you select are up to you.

#### Project Steps:
<!--- project guide will be written up and include --->
