## Digital vs Analog
The _Blinking LED Experiment_ used digital output, but that's not the only type of output: you can also use **analog output**. Digital output has two states: ON or OFF, or as the method digitalWrite() refers to them, HIGH and LOW.

Essentially, if the voltage is flowing then the pin is receiving voltage and is ON. If the voltage isn't flowing, then the pin is OFF. The HIGH state on an Arduino pin means that the pin is receiving voltage (typically 5V), and the LOW state is when the pin is receiving 0V. In the blink example, the LED turned ON when it received voltage (when it was sent a HIGH state) and then turned OFF when it didn't have voltage (when it was sent a LOW state).

Digital output is binary, meaning it has two states, but this isn't the case for analog output. The difference is best shown using a light switch:

![Light Switch Example](http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/04/06222027/lightswitch-205x300.jpg)

The light switch has two states: on and off, but what if you want a switch that could control the brightness of a light and have a range of "on-ness" rather than being so finite. In that instance we are going to want to use **analog output**.

If a typical light switch represents digital output, then a dimmer switch represents analog output:

![Dimmer Switch Example](http://d3nnidcq81r9m6.cloudfront.net/wp-content/uploads/2016/04/06222259/dimmer_switch-300x274.jpg)

Analog output provides more control and flexibility because you're able to output a **range of values** instead of ON or OFF. The key point to remember is that analog is a range and digital is either HIGH (ON) or LOW (OFF).

The next lesson is a deeper dive into more of the specifics of how the Arduino handles analog output.
