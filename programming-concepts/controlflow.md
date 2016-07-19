<!--- screenshots and examples need to be changed to Arduino examples instead of js --->

# Control Flow in Arduino Programming
The term _control flow_ may seem daunting at first, but at its core its essentially a group of statements and structures that govern the interactivity and processes of programs. You've already worked with one type of control flow in your Arduino experimentation- _functions_.

Two more types of control flow will be covered in this section, <em>conditional logic</em> and <em>looping</em>. This may seem like a lot of things to understand at first but are rather straightforward when they're broken down into component parts.

## The Block Statement
The first, and most basic, control flow statement is the <em>block statement</em>. You've actually already integrated these into your code when you've worked with <em>functions</em>. Consider this code contained within the **void loop()** function (you're going to have this code memorized  by the end of the camp!):

```arduino   
void loop() {
  digitalWrite(13, HIGH);   // turn the LED on (HIGH is the voltage level)
  delay(1000);              // wait for a second
  digitalWrite(13, LOW);    // turn the LED off by making the voltage LOW
  delay(1000);              // wait for a second
}
```

  With regard to the above example, you can think of the block statement as containing, or controlling, the code within the function. In this particular example, this would be the code that controls the on/off messages of the LED as well as the delays.
  As you move into the other types of control flow covered in this lesson, you'll see this form used each time. Just remember that code contained within { } is chunked together for a reason.

## Conditional Statements

_Conditional statements_ are one of the core pillars of programming, whether it be for the web, video games or other applications. Developing a practical and functional understanding of working with conditional statements will greatly enhance the level of interactivity that you're able to develop and include in your code.

Let's take a look at two examples. The first is stripped down to demonstrate a concept, and the second is a snippet of functional Arduino code.

**Example one**:

```arduino
    if (x > 10) {
        //if true, do these things
    } else {
        //if false, do these things
    }
```

In this example, the if statement is evaluating a condition that is contained with the ( ) following the word <em>if</em>. The statement that is within the ( ) needs to be able to be evaluated as a Boolean value, meaning it must either evaluate to <em>true</em> or <em>false</em>.

In the above example, the statement would evaluate as true <em>if the value of the variable x is greater than 10</em>. If this returns true, then the code within the first set of { } is executed.

This particular form includes an else { } block statement as well. This is the code that executes if the condition is false. Since the statement contained within the ( ) is Boolean, meaning it is either true <strong>or</strong> false, only one block statement of code will execute.

**Example two**:

 This is a snippet of code using a concept that you'll integrate into an upcoming project.

```arduino
if (buttonState == HIGH) {
  // turn LED on:
  digitalWrite(ledPin, HIGH);
} else {
  // turn LED off:
  digitalWrite(ledPin, LOW);
}
```

This example is checking to the state of a button to determine whether it is on or off. The setup is similar to the first example, as there is an expression inside the ( ) being checked.

The _buttonState_ variable is checked to see if it is in a HIGH (on) state, and if that condition evaluates as true, then a _digitalWrite_ message is sent to the board to turn on the LED.

In the else { } statement, which will execute when _buttonState_ is NOT equal to HIGH, then sends a message to turn the LED off.

Notice the inclusion of _variables_ in the above examples. Variables and conditional statements are commonly used together to execute commands that are determined by checking a particular state.

Now that you have an understanding of the structure of conditional statements, it's time to introduce another key concept, <em>operators</em>.

## Basic Operators

This section includes some of the basic operators that you'll use in your Arduino projects. There are lots of resources available online, particularly on the [Arduino Reference Page](https://www.arduino.cc/en/Reference/HomePage) for a more in-depth list if you're wanting to develop a deeper understanding of this tool.
<!---
### Assignment Operators
You've already worked with the first type of operator, which is the <em>assignment operator</em>. These are operators that assign a value to to something on the left based on the evaluation of what's on the right. Here are some examples:



There are several more, but these are some of the most common that you'll use for now.

<!--- double check syntax! --->

### Comparison Operators
Another type of operator is the <em>comparison operator</em>. This was used in the example above where the value of a "name" variable is checked to see if it is empty. These are commonly used in <em>if...else statements</em> because they return true or false based on the evaluation. Many of these are the same as what you've likely used in math classes. Here are some examples:

<ul>
 	<li>Equal (==) : This returns true if the values are equal.</li>
 	<li>Not equal (!=) : This returns true if the values aren't equal.</li>
 	<li>Greater than (&gt;) : This returns true if the value on the left is larger than the value on the right.</li>
 	<li>Greater than or equal to (&gt;=) : This returns true if the value on the left is larger or equal to the value on the right.</li>
 	<li>Less than (&lt;) : This returns true if the value on the left is less than the value on the right.</li>
 	<li>Less than or equal to (&lt;=) : This returns true if the value on the left is less than or equal to the value on the right.</li>
</ul>

One thing that you should remember is that when evaluating equality within conditional statements, you want to use the (==) operator. If you use only a single (=), Arduino thinks that you're attempting to assign a value and it can become confused about how to handle the statement.

There are other operator types that you'll encounter, but for now focus on developing an understanding of how these operator types are used with conditional statements to provide control flow to your code.
