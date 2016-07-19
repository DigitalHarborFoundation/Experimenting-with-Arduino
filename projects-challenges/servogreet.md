<p style="text-align: center;">Make a servo-powered greeter with Arduino!</p>
<p style="text-align:center;">
<!-- <img class="aligncenter" src="http://dhf-website.s3.amazonaws.com/images/tinkercad-bookmark-collage.jpg" alt="tinkercad-bookmark-collage" width="1023" height="482" /> -->
<!-- need photo -->

</p>

<h1>Setup and Supplies</h1>
In this project, you're going to be using an Arduino and micro servo motor to create a waving popsicle stick arm. You're going to make the basic 'skeleton' which can then be extended into several other fun projects! This fun and flexible Arduino project introduces several important Arduino concepts while still offering a high level of customization and modification.

<img src="http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/05/30195358/project-sample-400px1.jpg" alt="project sample-400px1" width="400" height="426" class="alignnone size-full wp-image-3848" />

<h3>Build time:</h3>
Approximately 45-50 minutes
<h3>Skills needed:</h3>
<ul>
 	<li>Basic computer skills</li>
 	<li>Basic programming knowledge - this can be developed through the activity!</li>
 	<li>Basic understanding of electronics - this can be developed through the activity!</li>
</ul>
<h3>Tools:</h3>
<ul>
 	<li>Computer</li>
    <li><a href="https://www.arduino.cc/">Arduino IDE</a> - the programming environment for Arduino</li>
    <li>Arduino Uno board - the board used for this project</li>
    <li>Micro servo motor</li>
    <li>Popsicle stick - this is the motor 'arm'</li>
    <li>Basic crafting materials - there are many integration options for these materials</li>
</ul>

<hr/>

<h2>How to Create a Servo-Powered Arm Using Arduino</h2>

<img src="http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/05/30195550/bcpl_-_iot_-_step_2-400px6.jpg" alt="bcpl_-_iot_-_step_2-400px6" width="400" height="157" class="alignnone size-full wp-image-3850" />

<h3>Step 1: Download the Arduino IDE</h3>
Navigate to the <a href="https://www.arduino.cc/en/Main/Software">Arduino download page</a> and select the download for whichever OS you're running. You can also access this page by going to the Arduino homepage and selecting the <em>Download</em> tab.


<img src="http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/05/30195809/bcpl_-_iot_-_arduino_step_2-400px1.jpg" alt="bcpl_-_iot_-_arduino_step_2-400px1" width="400" height="256" class="alignnone size-full wp-image-3851" />

<h3>Step 2: Open the Arduino IDE</h3>
Once you've downloaded and installed the Arduino IDE, go ahead and open it up. The icon is a light blue circle with a white infinity in the middle. If it's your first time opening the IDE, it may take a moment to open. If you get a message about creating a new network connection, go ahead and click "Allow."


<img src="http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/05/30200249/bcpl_-_iot_-_line_numbers-400px3.jpg" alt="bcpl_-_iot_-_line_numbers-400px3" width="400" height="266" class="alignnone size-full wp-image-3854" />

<h3>Step 3: Turn on line numbers (Optional)</h3>
If your sketch already show line numbers, you can skip to Step 4. If not, you can turn them on by following these steps:
<ul>
    <li>Click on <strong>Arduino</strong> in the menu at the top of the IDE.</li>
    <li>Click on the <strong>Preferences</strong> sub-menu to open the IDE preferences.</li>
    <li>Make sure that "Display line numbers" is selected.</li>
    <li>Click the 'Ok' button in the bottom right to save.</li>
</ul>

<img src="http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/05/30200627/bcpl_-_iot_-_gist-400px1.jpg" alt="bcpl_-_iot_-_gist-400px1" width="400" height="270" class="alignnone size-full wp-image-3855" />


<h3>Step 4: Get the project code</h3>
For this project, you're jumping in and modifying some existing code. Don't worry if you don't understand all of the code. You'll gradually increase your understanding of Arduino programming by experimenting with code that already exists. The code file for this project has lots of helpful comments that you can read that explain several of the key concepts that are used.

Navigate to this link to access the project code:

<a href="https://gist.github.com/jonathanprozzi/e5a74481ecfd211a618483022b5633d0">BCPL Workshop: Servo Sketch gist on GitHub</a>


<img src="http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/05/30200936/bcpl_-_iot_-_gist_copy-400px1.jpg" alt="bcpl_-_iot_-_gist_copy-400px1" width="400" height="270" class="alignnone size-full wp-image-3856" />

<h3>Step 5: Copy the entire gist code</h3>
Gist is a great way to share code with your learners. For this project, go ahead and copy the entirety of the code (lines 1 - 41).

To copy, use <strong>CMD + C</strong> on a Mac, or <strong>Ctrl + C</strong> on Windows.

<em>Note</em>: Don't close the browser window incase you need to repeat this process!


<img src="http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/05/30201120/bcpl_-_iot_-_arduino_new_1-400px1.jpg" alt="bcpl_-_iot_-_arduino_new_1-400px1" width="400" height="194" class="alignnone size-full wp-image-3857" />

<img src="http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/05/30201125/bcpl_-_iot_-_arduino_new_2-400px2.jpg" alt="bcpl_-_iot_-_arduino_new_2-400px2" width="400" height="177" class="alignnone size-full wp-image-3858" />


[three_fifth_last padding="0 0px 0 5px"]
<h3>Step 6: Create a new Arduino sketch</h3>
Open the Arduino IDE and create a new sketch. To do this, click on the <strong>File</strong> menu and then select <strong>New</strong>. Once you've done this, a new sketch will pop up. After this new sketch appears, you can close the previous sketch.


<img src="http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/05/30201401/bcpl_-_iot_-_pasted_code_sketch-400px4.jpg" alt="bcpl_-_iot_-_pasted_code_sketch-400px4" width="400" height="227" class="alignnone size-full wp-image-3859" />


[three_fifth_last padding="0 0px 0 5px"]
<h3>Step 7: Paste the code into the new sketch</h3>
Once you've created the new sketch, paste the <strong>entire</strong> copied code into the sketch. You should replace everything- don't leave the original <strong> setup and loop</strong> functions or the code won't work. Check that your code matches the image before proceeding.

As a quick check, line 6 of your sketch should read: "#include <Servo.h> //This is necessary when working with servos. It includes the servo library."

<img src="http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/05/30202428/Arduino_Connection_To_Computer-small-400px1.jpg" alt="Arduino_Connection_To_Computer-small-400px1" width="400" height="457" class="alignnone size-full wp-image-3860" />

[/two_fifth]


[three_fifth_last padding="0 0px 0 5px"]
<h3>Step 8: Connect the Arduino to your computer</h3>
Connect the Arduino to your computer via USB. You'll see some lights on your Arduino begin to glow. If you see these, your Arduino is now being powered by your computer's USB! If you don't see any lights on the Arduino, try unplugging it and reconnecting.
[/three_fifth_last]

[two_fifth]

<img src="http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/05/30202635/Arduino_Board_Selector-small-400px1.jpg" alt="Arduino_Board_Selector-small-400px1" width="400" height="318" class="alignnone size-full wp-image-3861" />

<img src="http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/05/30202645/Arduino_Port_Selector-small-400px2.jpg" alt="Arduino_Port_Selector-small-400px2" width="400" height="235" class="alignnone size-full wp-image-3862" />

<img src="http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/05/30203651/bcpl_workshop_-_iot_-_upload-400px1.jpg" alt="bcpl_workshop_-_iot_-_upload-400px1" width="400" height="199" class="alignnone size-full wp-image-3863" />

[/two_fifth]

[three_fifth_last padding="0 0px 0 5px"]
<h3>Step 9: Uploading the sketch to the Arduino</h3>
Once your board is connected, you need to upload the sketch to the board. First, you need to check to make sure that the board and port is detected by the IDE. To do this, follow these steps:
<ul>
  <li>Click the <strong>Tools</strong> menu in the IDE and scroll down to the <strong>Boards:</strong> submenu. Make sure that it says <strong>Board: Arduino/Genuino Uno</strong>. If it doesn't, hover over the Board entry and choose "Arduino/Genuino Uno" from the menu.</li>
  <li>Next, make sure that your port is correct. There are a few different options. Usually, the IDE will auto-detect the board and set this. If this is the case, it'll have the Arduino/Genuino Uno listed in the popup menu linked to <strong>Ports</strong>. If you don't see this, hover over <strong>Ports</strong> and select the board that is linked to your USB port.</li>
  <li>If you don't see any board on the USB port, close the IDE and unplug the Arduino. Plug it back in and re-open the IDE.</li>
</ul>

Once the board and port are set, go ahead and click the <strong>Upload</strong> button at the top right of the IDE. It looks like an arrow. After you click this the sketch will begin to upload to the board. This process sometimes takes a minute or two. You'll see it say "Done uploading" at the bottom of the IDE when this completes.

[/three_fifth_last]

[two_fifth]

<img src="http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/05/30211747/bcpl-workshop-iot-servo-1.jpg" alt="bcpl workshop - iot - servo 1" width="400" height="299" class="alignnone size-full wp-image-3864" />

<img src="http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/05/30211756/bcpl-workshop-iot-servo-2.jpg" alt="bcpl workshop - iot -  servo 2" width="400" height="299" class="alignnone size-full wp-image-3865" />

[/two_fifth]

[three_fifth_last padding="0 0px 0 5px"]
<h3>Step 10: Assembling the servo</h3>
The next step is to do the wiring for the servo motor. For this project, you're going to attach the servo directly to the Arduino board. The first thing you need to do is to examine the wires that are attached to the servo. There are 3 wires bundled together and they are brown, red, and orange.

For this particular servo, here is the polarity:
<ul>
  <li>Brown: Ground</li>
  <li>Red: Power (5V)</li>
  <li>Orange: Signal/data</li>
</ul>

If your servo doesn't have the hinge attached, find the single-arm hinge and just pop it onto the top of the servo. It snaps into place with minimal effort.

Use 3 jumper wires and attach them to the end of the servo wire bundle. The jumper wire color doesn't matter, but it's common to use black for your ground and red for power. Just remember which color jumper you attach to each servo wire.
[/three_fifth_last]

[two_fifth]

<img src="http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/05/30211806/bcpl-workshop-iot-servo-4.jpg" alt="bcpl workshop - iot - servo 4" width="400" height="299" class="alignnone size-full wp-image-3867" />

[/two_fifth]

[three_fifth_last padding="0 0px 0 5px"]
<h3>Step 11: Attaching the 'arm'</h3>
Before attaching the servo to the Arduino, you'll want to build out the popsicle stick 'arm.' You may need to make some adjustments to the exact positioning of the popsicle stick based on your project, but it's generally easier to attach it at this point.

Tape the popsicle stick to the servo hinge. The servo in this example uses a single-armed hinge. If you only have the full servo hinges (double sided) you can just cut off one side of the arm.

However you choose to align and tape the popsicle stick is up to you. You may need to adjust it throughout your project. You'll definitely need to tape it in such a way that the servo lies completely on it's back, as in the image. Otherwise your servo will not be sturdy.

[/three_fifth_last]

[two_fifth]

<img src="http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/05/30213451/bcpl-workshop-iot-arduino.jpg" alt="bcpl workshop - iot - arduino" width="400" height="299" class="alignnone size-full wp-image-3873" />

<img src="http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/05/30215536/bcpl_-_igd_-_arduino_closeup-400px1.jpg" alt="bcpl_-_igd_-_arduino_closeup-400px1" width="401" height="536" class="alignnone size-full wp-image-3881" />

[/two_fifth]

[three_fifth_last padding="0 0px 0 5px"]
<h3>Step 12: Connecting the servo to the Arduino</h3>
Now that your servo arm is ready to go, you need to connect it to the Arduino. To make things easier, it's beneficial to unplug your Arduino from the USB so that you can easily maneuver the board while working.
<ul>
  <li>First, refresh yourself on the polarity of the servo. Remember which jumper wires you attached to the servo wires. Remember that brown: ground, red: power, orange: data/signal.</li>
  <li>Connect the jumper wire attached to the <strong>brown servo wire</strong> to the <strong>GND pin</strong> on the Arduino.</li>
  <li>Connect the jumper wire attached to the <strong>red servo wire</strong> to the <strong>5V</strong> pin on the Arduino. The GND and 5V pins are next to each other on the Arduino board.</li>
  <li>Finally, connect the jumper wire attached to the <strong>orange servo wire</strong> to <strong>pin 9</strong> on the Arduino.</li>
</ul>

The pin that connects to the signal/data on the servo must match the pin that's used in the sketch's code. If you want to change the pin, you need to also modify it in the code on line 14 in the <strong>void setup()</strong>:

<pre class="lang:arduino decode:true " >void setup() {
  myservo.attach(9);  // attaches the servo on pin 9 to the servo object- needs to match the pin servo is on board
                      // if you change to another pwm pin on the board (11, 10, 9, 6, 5, 3) change above number to match
}  </pre>
[/three_fifth_last]

[two_fifth]

<img src="http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/05/30220200/bcpl_workshop_-_iot_-_loop_modify-400px1.jpg" alt="bcpl_workshop_-_iot_-_loop_modify-400px1" width="400" height="183" class="alignnone size-full wp-image-3884" />

[/two_fifth]

[three_fifth_last padding="0 0px 0 5px"]
<h3>Step 13: Modify the code!</h3>
The modifications that you make depend on what you want to do for your project. This guide is for the basic servo 'waving arm' that can be used and integrated into several projects.

The code comments contain some suggestions for places to modify, but here are some starting points:

In the <strong>void loop()</strong> function, you can change the speed, starting position, and end position of the servo. If you want to do this, find the <strong>for loops</strong> on lines 19 and 31. The first one is for the forward motion of the servo and the second one is for the return motion. Experiment with modifying these positions and the <strong>delay</strong> values! Use the commented code as a reference point.
[/three_fifth_last]

[two_fifth]

<img src="http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/05/30195358/project-sample-400px1.jpg" alt="project sample-400px1" width="400" height="426" class="alignnone size-full wp-image-3848" />

[/two_fifth]

[three_fifth_last padding="0 0px 0 5px"]
<h3>Project Ideas</h3>
Now that you've created the base servo arm, you can do a variety of different things. In this example, a paper hand has been added to the popsicle stick to create a 'waving arm.' Once you understand the connection between the servo motion and the Arduino code, you can experiment with changing the values to fine-tune your project.

Some other ideas are to make a 'stick puppet' where you draw build a face onto the servo. Have fun and keep experimenting!

[hr]
<h2>Learn more</h2>
<ul>
 	<li>Check out additional <a href="http://blueprint.digitalharbor.org/projects/">Step-By-Step Projects</a> from the Digital Harbor Foundation</li>
 	<li>Sign up for one of the <a href="http://blueprint.digitalharbor.org/workshops/" target="_blank">Educator Workshops</a> at our Baltimore Tech Center</li>
</ul>
