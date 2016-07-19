## Working with Servo Motors
Servo motors are small RC hobby motors that can be controlled by an Arduino through controlling the shaft. Servos have plastic arms that connect to the top of this shaft. You'll come across servos that have different tops attached. The ones in your kit have some options for you to try out. You're able to switch out these tops rather easily- sometimes there is a tiny screw that needs to be detached, but often you can just use your fingers to switch out the arms.

![Servo picture](http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/05/30211747/bcpl-workshop-iot-servo-1.jpg)

### Controlling a Servo
Servo motors have three wires:
- Red - Power (5v)
- Brown - Ground
- Orange - Signal / Data

These wires then connect to the Arduino board. The Arduino sends electric pulse signals to the servo, which causes it to rotate. When you begin working with the code, you'll see how this process of sending a message from the Arduino to a component is quite similar to what you've done so far with LEDs.

![Servo wires](http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/05/30211756/bcpl-workshop-iot-servo-2.jpg)

### Servos and Arduino
Once the servo motor is connected to an Arduino board, you're able to control the angle of the shaft position, typically between a range of _0 to 180 degrees_. There are certain types of servos that are _continuous rotation_ that can move at different speeds, but the more common types work within a range of 0 to 180 degrees and move one step (degree) at a time.

In order to work with servos, you'll need to import a code _library_ specifically for the servo. There are several Arduino libraries that you're able to include in projects. Often these libraries are written to provide additional support or functionality for working with certain components. Practicing importing and including libraries will open up lots of projects and ideas!

The _Servo Library_ can support up to **12** motors on the board, and uses a special **servo.write()** command to send position data to the motor. The **servo.write()** is from the Servo Library and the Arduino IDE wouldn't understand what it means without including the library.

You'll have the entirety of the code to experiment with, but let's cover some key parts:

**Including a Library**: to include a library in your code, you place an _include_ at the top of your code, before anything else:
```arduino
        #include <Servo.h> //This is necessary when working with servos. It includes the servo library.
```

The name of the library goes in the < >. In this example, it's called _Servo.h_

Many times when working with libraries there are code examples that you can reference if you need help knowing what to include.

**Creating a servo object**: the next key piece of code creates a servo object. This is what the Arduino uses to work with the servo component:
```arduino
Servo myservo;  // create servo object to control a servo
```
After you've done this step, you're then able to interact with the servo that you've attached to your board.

**Connecting the servo**: Just like when working with any of the other components, such as the LED, you need to tell the Arduino the pin number where the component is attached. For the servos, this is the pin that the orange (signal) wire connects with. Here's the code that goes into the **void setup()**:

```arduino  
myservo.attach(9);  // attaches the servo on pin 9 to the servo object- needs to match the pin servo is on board
```

That covers the key parts of the code. For the project, you'll have code provided that you can experiment with and tweak.

### Activity: Setting up a Servo
For this activity, you're going to practice the basic servo connection and experiment with the code. Once you have the basic concept, you'll then be able to integrate servos into more of your projects as well as combine them with other components.

#### Supplies:
- Uno board and breadboard
- Servo motor
- Three jumper wires

#### Steps (Board):
The servo needs to be attached to an Arduino pin that is capable of **PWM**, since that's how the servo is powered. These are the pins with the **~** symbol, such as **~9**.

Refer to this Fritzing diagram:
![Servo circuit](http://i.imgur.com/TbdwRUZ.png)

1. Once your supplies are gathered, connect the breadboard to the Arduino:
    - _- rail_ on the breadboard connects to _GND_ on Uno
    - _+ rail_ on the breadboard connects to _5V_ on Uno
2. Next, connect the servo:
    1. First, refresh yourself on the polarity of the servo. Remember which jumper wires you attached to the servo wires. Remember that brown: ground, red: power, orange: data/signal.
    2. Connect the jumper wire attached to the **brown servo wire (ground)** to the **GND (-)** rail on the breadboard.
    3. Connect the jumper wire attached to the **red servo wire (5V)** to the **power (+)** rail on the breadboard.
    4. Finally, connect the jumper wire attached to the **orange servo wire (signal)** to a jumper that connects to **pin 9** on the Arduino.
3. Note that if you change the pin number in either the board or the code, it must match. **You need to use a pin with a ~**.

#### Steps (Code):
Now for the code! You'll be getting the basic code template from a GitHub Gist account. There will be comments in the code for you to follow and modify.

1. Make sure to connect the Arduino to your computer and configure the board and port connection before moving on.
2. Navigate to this link and grab the sketch code from this Gist on Jonathan's GitHub:
    [Servo sketch code](https://gist.github.com/jonathanprozzi/e5a74481ecfd211a618483022b5633d0)

    ![copying code](http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/05/30200936/bcpl_-_iot_-_gist_copy-400px1.jpg)

3. Copy the entire gist code
Gist is a great way to share code with your learners. For this project, go ahead and copy the entirety of the code (lines 1 - 41).

    To copy, use <strong>CMD + C</strong> on a Mac, or <strong>Ctrl + C</strong> on Windows.

    _Note_: Don't close the browser window incase you need to repeat this process!

    - ![Copying into Arduino](http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/05/30201120/bcpl_-_iot_-_arduino_new_1-400px1.jpg)

    - ![Arduino 2](http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/05/30201125/bcpl_-_iot_-_arduino_new_2-400px2.jpg)

4. Create a new Arduino sketch:

    ![New Sketch](http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/05/30201401/bcpl_-_iot_-_pasted_code_sketch-400px4.jpg)

5. Paste the code into the new sketch</h3>
Once you've created the new sketch, paste the <strong>entire</strong> copied code into the sketch. You should replace everything- don't leave the original <strong> setup and loop</strong> functions or the code won't work. Check that your code matches the image before proceeding.

6. Begin modifying the code! Follow the comments and experiment. _Save your sketch!_

#### Going Further:

The modifications that you make depend on what you want to do for your project. This guide is for the basic servo example.

The code comments contain some suggestions for places to modify, but here are some starting points:

In the <strong>void loop()</strong> function, you can change the speed, starting position, and end position of the servo. If you want to do this, find the <strong>for loops</strong> on lines 19 and 31. The first one is for the forward motion of the servo and the second one is for the return motion. Experiment with modifying these positions and the <strong>delay</strong> values! Use the commented code as a reference point.
