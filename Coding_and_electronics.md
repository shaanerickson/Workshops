# Coding and Electronics workshop

This workshop is intended to guide you through some basic coding techniques, teach you the basics of designing electric circuits as well as give you an introduction to programming an arduino board. If at any point you have a question, don't hesitate to ask one of the HURC members for guidance.

## Getting started:

Installing the Arduino IDE
The first step that needs to be completed before any coding can be done is to set up the correct environment. Since we will primarily be using Arduino boards to program our robots, it is ideal for us to develop in the Arduino IDE. IDE is short for Integrated Development Environment, which contains not only the text editor we need to write our code in, but also a compiler to build our code, and communication protocols with the chip that we are programming. Arduino boards are small boards that contain a microcontroller and easy to use interfaces for programming the processor and using it to control electronics. Follow the steps below  to get the Arduino IDE installed:

1. Click [here](http://arduino.cc/en/Main/Software) to access the download page.

2. Download your appropriate installer, depending on what operating system your machine has.

4. Run the installer, and leave  all options in their default states. Note: On Windows, you will get a pop up asking to install  the Arduino USB Driver. This is very important, so click allow.

5. Once the install finishes, close the installer, and you should have the Arduino IDE installed on your computer!

## THE BASICS

The first thing you need to know before getting started are the components most used in electronic circuits, and how they work (at a very high level). The following are the components that you will need to know in order to begin building simple circuits (and, subsequently, simple robots). Figure 0.1 shows how a component is represented in a circuit schematic, and directly below are pictorial representations. Feel free to compare the images to the real life counterparts available.

1. Power sources - A power source provides the voltage ( Volts) and current (Amperes) necessary to drive a circuit. At its core, it is a source of electric potential, and without it a circuit would be useless. Power sources can take the form of batteries, power supplies, or microcontrollers (an Arduino has a max pin output of 5V ). For simplicity, we will be using a DC power source.
2. Resistors - Resistors (Ohms), to put it simply, resist. They impede the flow of electrons through a circuit, and subsequently results in a voltage drop. A voltage drop is a change in the amount of voltage in the circuit, and through it one is able to control how a circuit behaves fairly accurately. One thing to know is that current always follows through the path of least resistance, thus if a current has a choice between a 500 Ohm resistor and a 10000 ohm resistor, it will flow through the 500 ohm resistor.
3. Potentiometers (aka pots) - Potentiometers are essential variable resistors. While a resistor can only have a fixed resistance, potentiometers can be tuned to any resistance within its range (we will be using 10 kOhm pots, meaning they can take a value between 0 Ohms and 10000 Ohms).
4. LEDs - LED stands for Light Emitting Diode. In its simplest form, it turns current into light and heat, while at the same time acting like a resistor and producing a voltage drop. Because LEDs are diodes, it is important to know that they only work if connected in the proper direction (the longer leg is the positive end, the shorter leg is the negative end). LEDs and capacitors are the only components we will be working with that work only in one direction.
5. Capacitors - Capacitors act like buckets for electricity; they store charge and can thus be used as temporary and small batteries (as well as producing some other useful phenomenon). Capacitors, like LEDs, are polarized and will only work if placed in circuit in the correct orientation.

![alt tag](https://raw.githubusercontent.com/HarvardURC/Workshops/master/assets/coding_electronics/fig%200.1.jpg)

In this section, we will review the basic building blocks of an Arduino sketch (the  common name of an Arduino program), and work through several examples that will highlight these ideas. Our main reference for this section will be the official Arduino reference, which can be found [here](http://arduino.cc/en/Reference/HomePage). It is probably a lot to take in at once, but this page will probably answer any questions you might have about the syntax of the arduino language.

## HARDWARE - THE BOARD ITSELF

Please review [this tutorial](http://arduino.cc/en/Guide/Board?from=Tutorial) for a general overlay of the Arduino Uno board. Although we may not be using the Uno for our actual projects, understanding the Uno board is key to understanding other Arduino boards. Don't worry if you don't understand everything just yet.

## SOFTWARE - THE ARDUINO SKETCH

### GENERAL LAYOUT

Every Arduino sketch has two main components, a setup and a loop function, as seen below:

The setup function runsonce when you press reset or power the board:
```ino
void setup ( )   {
    // code here
}
```
The loop function runs over and over again indefinitely:
```ino
void   loop ( )   {
    //code here
}
```

As seen in the comments, the setup function of the  Arduino function only runs once, and before any other code is run. The main purpose of this section is to initialize any global variables that might be used later, set up board pins for use (which board pin controls what), etc. The loop function is the main logic function of the Arduino sketch. It does exactly what you would expect it to - it loops! Generally, all the logic of the Arduino sketch is contained in this function.

### BLINK    

Let’s quickly examine pins and writes in action. Head [here](http://www.arduino.cc/en/Tutorial/Blink) and follow the tutorial there. You can find the code already written in your Arduino IDE by going to File>Examples>01.Basics>blink. The next segment will teach you how to load the sketch onto the actual Arduino board.


### UPLOADING CODE

To upload a Arduino sketch from the IDE to the board, simply follow these steps once you have an arduino sketch open:

1. Compile your Arduino sketch using the check mark button in the top toolbar. This will build your sketch code, and check if there are any syntactical issues. If there are, you should fix them now.

2. Connect the micro-USB end of the USB wire into the board, and the USB end into your computer. If you completed the driver steps, your board should be recognized with no issues.

3. Go to Tools>Board and make sure you have the correct board specified. For this tutorial we are using the Arduino Uno.

4. Go to Tools>Serial Port, and make sure you have the correct board for your board selected. There generally is only one port, but if there are more, trial and error usually works.

5. Click on the Right Arrow button in the toolbar to upload your code.

### SYNTAX

The Arduino IDE uses a custom programming syntax known as INO, which is really just a derivative of C/C++. Because of that, the syntax in Arduino sketches is almost exactly the same is in C or C++ programs. The full supported syntax is listed out in the [Arduino reference](https://www.arduino.cc/en/Reference/HomePage). Make sure you are comfortable with the structure section.

For coding projects in any language, but Ino in specific you have to be able to use:
1. if and if ... else statements  
2. for and while loops  
3. arithmetic operations  
4. comparison operations  
5. boolean operations  
6. constants and variables  
7. boolean, char, int, string and array data types  
8. Digital and Analog I/O. More precisely PinMode, AnalogWrite, AnalogRead, DigitalWrite, DigitalRead  
9. [Serial Print](https://www.arduino.cc/en/Serial/Print)  

This is a lot to go through right now. If you have any prior experience with coding, then most of this should simply be looking up the new syntax. If you aren't familiar with theses concepts, then don't try to go through all of the refrence right now. Instead focus on the aspects that you think will help you solve a particular exercise as you go through this workshop.

#### Exercise  1.1 (Serial Print, strings)
Write an Arduino sketch to print "Hello World!". Make sure to use correct Arduino sketch layout.

#### Exercise  1.2 (for loops, variables)
Build on the following Arduino sketch so that it prints a 10-level left-aligned pyramid of asterisks. Make sure you use the variable levels in your loop function.
```ino
void setup ( )   {
  int   levels   =  10;
}

void loop ( )   {
  Serial.print("*") ;
}
```

Expected output:  
\#  
\#\#  
\#\#\#  
\#\#\#\#  
\#\#\#\#\#  
\#\#\#\#\#\#  
\#\#\#\#\#\#\#  
\#\#\#\#\#\#\#\#  
\#\#\#\#\#\#\#\#\#  
\#\#\#\#\#\#\#\#\#\#  

#### Exercise 1.3  (arrays)

Write an Arduino sketch that creates the following array {0, 1, 2, 3, 4, 5, 6, 7, 8, 9} using a while loop.

### FUNCTIONS

Functions are the building blocks for more advanced logic. Instead of writing all logic inside the central loop function, we can create functions to separate out logic, and simply call those functions within the loop. Not only does this help us keep track of the specific purpose of parts of our code, but it also helps us keep our code clean and manageable.

Writing functions in an Arduino sketch is identical to writing a function in any C program. Simply define the output type, the name of the function, and any inputs into the function.

```ino
int functionName  (int input1, char input2) {
  // . . .  logic here . . .
}
```

In the snippet above, we have a function called functionName with output type integer, and two inputs: an integer input1, and a char input2. As an aside, if you are familiar with C systems programming, you are probably used to dynamic memory allocation using the malloc() and free() commands, and returning allocated addresses. Arduino boards don’t have a heap, so you won’t be able to take advantage of that here. All logic should be done at the stack and global level.

#### Exercise 2.1

Write a function that takes in two integers as input, and returns the integer sum of them.

#### Exercise 2.2

Write a function that, when given a integer n, produces an array of with the first n Fibonacci numbers in it.

#### Exercise 2.3

Call the first function in the second function so that after the Fibonacci array is created, the sum off all elements in the array is computed.

## Final Challenge

Write a function that takes a list of strings an prints them, one per line, in a rectangular frame. For example the list ["Hello", "World", "in", "a", "frame"] gets printed as:

\*\*\*\*\*\*\*\*\*  
\* Hello__ \*  
\* World__\*  
\* in_____ \*  
\* a______\*  
\* frame__ \*  
\*\*\*\*\*\*\*\*\*  

NOTE: Underscores represent spaces.  
Use a separate function for determining the frame width that takes in the list of words as an input and a separate function for printing a line of the frame, that takes in a word and the frame width.
