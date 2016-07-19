# The Arduino IDE

The laptops that you're using already have the Arduino IDE installed. To get up and running, go ahead and open *Launchpad* (the rocket icon on the Dock) and search for "Arduino" and select the application as soon as it appears.

The icon is a light blue circle with a white infinity sign inside. Here is a screenshot of what the Launchpad search looks like:
![Arduino-Launchpad-Screenshot](http://i.imgur.com/zbm1Mkh.jpg)

Once you've pulled this up, go ahead and click the *Arduino* application to launch it.

# Your First Program
Once the software has been installed, it's time to test the software and your ability to program your Arduino device. The first time you launch the Arduino software, a new <em>sketch</em> will be created.

![Arduino-new-sketch](http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/04/02121157/arduino_new_sketch.jpg)

## Sketches
Sketches are the programs that you write for your Arduino devices. They are uploaded to your Arduino device's memory so that they can run without being attached to your computer. A sketch is required to contain a *setup()* and *loop()* function.

## Setup()

The _setup()_ function is a set of commands that runs when the Arduino is first turned on. It only runs once and in order to get it to run again, you will either need to unplug the power to your Arduino and plug it back in or you will need to press the reset button on your Arduino.

<pre class="lang:arduino mark:1-4 decode:true" title="Arduino Setup Function">void setup() {
  // put your setup code here, to run once:

}
</pre>

<pre class="lang:arduino mark:1-4 decode:true" title="Arduino Loop Function">
void loop() {
  // put your main code here, to run repeatedly:
}</pre>

## Loop()
The <em>loop()</em> function runs continuously on the Arduino after the <em>setup()</em> function has been run. When your Arduino code reaches the end of the <em>loop()</em> function, it will begin again at the top of the <em>loop()</em> function continuously until power is removed from the Arduino device.
<pre class="lang:arduino mark:6-9 decode:true " title="Arduino Loop Function">void loop() {
    void loop() {
      // put your main code here, to run repeatedly:

}</pre>

## Blink Example
The Arduino IDE provides a number of useful example sketches that you can use to get started with different projects or to test different components. One of the most useful is the _Blink_ sketch. This sketch allows you to easily test your connection to your Arduino by uploading a very simple sketch that makes an LED blink. It is also a great example sketch to demonstrate how the <em>setup()</em> and <em>loop()</em> functions work.

You can load the example sketch by clicking on the <em>File</em> menu and selecting the <em>Examples</em> option. Now click the <em>01. Basics</em> sub-menu and finally, click the <em>Blink</em> menu item.

![Arduino Blink Example](http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/04/02123439/Blink_Example-600x504.jpg)

The sketch has the following code:

<pre class="lang:arduino decode:true " title="Blink Example Sketch">
/*
  Blink
  Turns on an LED on for one second, then off for one second, repeatedly.

  Most Arduinos have an on-board LED you can control. On the Uno and
  Leonardo, it is attached to digital pin 13. If you're unsure what
  pin the on-board LED is connected to on your Arduino model, check
  the documentation at http://www.arduino.cc

  This example code is in the public domain.

  modified 8 May 2014
  by Scott Fitzgerald
 */

// the setup function runs once when you press reset or power the board
void setup() {
  // initialize digital pin 13 as an output.
  pinMode(13, OUTPUT);
}

// the loop function runs over and over again forever
void loop() {
  digitalWrite(13, HIGH);   // turn the LED on (HIGH is the voltage level)
  delay(1000);              // wait for a second
  digitalWrite(13, LOW);    // turn the LED off by making the voltage LOW
  delay(1000);              // wait for a second
}</pre>


Before I explain what this code means, let's upload it to your Arduino device.

## Uploading Sketches

Plug your Arduino device into your computer. This usually involves some sort of USB cable and different Arduinos will have different connections. For this example, I am using an Arduino UNO which uses a USB Type B connector (that is the fat square one).

![Arduino Connection To Computer](http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/04/04232354/Arduino_Connection_To_Computer-small-263x300.jpg)

In the Arduino IDE, you need to make sure that you have the correct Arduino board selected before uploading the program. Use the <em>Tools</em> menu to select the correct board, again, in this example I'm using Arduino Uno but make sure you select the correct board that you are working with:

![Arduino Board Selector](http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/04/04232940/Arduino_Board_Selector-small-600x477.jpg)

You also need to select the correct port that you are working with. Again, this is done under the <em>Tools</em> menu. Recent versions of the Arduino IDE do a good job of detecting what boards are connected to each port.

> NOTE: If you do not see your port listed, try quitting the Arduino IDE and launching it again.

![Arduino port Selector](http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/04/04233147/Arduino_Port_Selector-small-600x352.jpg)

Now that we have all of our connections setup, we are ready to upload the sketch. Click the Upload button in the Arduino IDE.

![Arduino-upload-small](http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/04/04233656/Arduino_Upload-small-600x493.jpg)

When the upload is complete, a status will display reading <em>Done uploading</em> in the bottom of the Arduino IDE.

![Arduino Upload Done](http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/04/04233751/Arduino_Upload_Done-small-600x493.jpg)

Most Arduino's have an onboard LED that will now start blinking if your upload was successful.

![Blinking LED](http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/04/05000008/Blinking_LED-600x412.gif)

This can sometimes be hard to see, so I grabbed a regular LED and plugged the positive leg (the longer leg) of the LED into the hole marked 13 and the negative leg (the shorter leg) into the hole marked <em>GND</em>.

![LED Arduino](http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/04/06103728/LED_Arduino-300x298.jpg)

![Big Blink LED](http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/04/05000727/Blink_Big_LED.gif)

That covers how to upload a sketch to your Arduino. In the next lesson, we will cover some basics of the Arduino programming language.
