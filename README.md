# Workshops

# Coding workshop

Getting started:

Installing the Arduino IDE
The first step that needs to be completed before  any coding can be done is to set up the correct environment. Since we will primarily be using Arduino boards to program our robots, it is ideal for us to develop in the Arduino IDE. IDE is short for Integrated Development Environment, which contains not only the text editor need to write our code  in, but also a compiler to build our code, and communication protocols with the chip that we are programming. Arduino boards are small boards that contain a microcontroller and easy to use interfaces for programming the processor and using it to control electronics. Follow the steps below  to get the Arduino IDE installed:

1.  Head to http://arduino.cc/en/Main/Software to access the download page

2.  Download your appropriate installer, depending on what operating system your machine has.

4.  Run the installer, and leave  all options in their default states. Note: On Windows, you will get a pop up asking to install  the Arduino USB Driver. This is very important, so click allow.

5.  Once the  install finishes, close  the installer, and you  should have the Arduino IDE
installed on your computer!

# THE BASICS

In this section, we will review the  basic building blocks of an Arduino sketch (the  common name of an Arduino program), and work through several examples that will highlight these ideas. Our main reference for this section will be the official Arduino reference, which can be found at http://arduino.cc/en/Reference/HomePage. It is probably a lot to take in at once, but this page will probably ansdwer any questions you might have about the syntax of the arduino language.

# HARDWARE - THE BOARD ITSELF

Please review http://arduino.cc/en/Guide/Board?from=Tutorial for a general overlay of the Arduino Uno board. Although we may not be using the Uno for our actual projects, understanding the Uno board is key to understanding other Arduino boards. Don't worry if you don't understand everything just yet.

# SOFTWARE - THE ARDUINO SKETCH 

# GENERAL LAYOUT

Every Arduino sketch has two main components, a setup and a loop function, as seen below:

//   The setup function runsonce when you press reset or power the board:
void   setup ( )   {
    // . . .   code here
}

//   The loop function runs over and over again indefinitely:
void   loop ( )   {
    // . . .   code here
}

As seen in the comments, the setup function of the  Arduino function only  runs once, and before any  other code is run. The  main purpose of this  section is to initialize any  global variables that  might be used  later, set up board pins for use (which board pin controls what), etc. The loop function is the main logic function of the  Arduino sketch. It does exactly what you would expect it to - it loops! Generally, all the logic of the Arduino sketch is contained in this function.

# BLINK    

Let’s quickly examine pins and writes in action. Head to http://www.arduino.cc/en/Tutorial/Blink and follow the tutorial there. You can  find the code already written in your Arduino IDE by going to File>Examples>01.Basics> link. The next segment will teach you how to load the sketch onto the actual Arduino board.


# UPLOADING CODE

To upload a Arduino sketch  from the IDE to the board, simply follow these steps once you have an arduino sketch open:

1.  Compile your Arduino sketch using the check mark button in the top toolbar. This will build your  sketch code, and check if there are any syntactical issues. If there are,  you should fix them now.

2.  Connect the micro-USB end of the USB wire into the board, and  the USB end into your computer. If you completed the driver steps, your board should be recognized with no issues.

3.  Go to Tools > Board and make sure you have the correct board specified. For this tutorial we are using the Arduino Uno.

4.  Go to Tools  > Serial  Port, and make sure you  have  the  correct board for your  board selected. There generally is only one  port, but if there are more, trial and error usually works.

5.  Click on the Right Arrow button in the toolbar to upload your code.

# SYNTAX

The  Arduino IDE uses a custom programming syntax known as INO, which is really  just  a derivative of C/C++. Because of that, the syntax in Arduino sketches is almost exactly the same is in C or C++ programs. The full supported syntax is listed out in the Arduino reference (https://www.arduino.cc/en/Reference/HomePage). Make sure you are comfortable with the structure section.

For coding projects in any language you have to be able to use:
1. if and if ... else statements
2. for and while loops
3. arithmetic operations
4. comparison operations
5. boolean operations
6. constants and variables
7. boolean, char, int, string and array data types
8. Digital and Analog I/O. More precisely PinMode, AnalogWrite, AnalogRead, DigitalWrite, DigitalRead
9. Serial Print (https://www.arduino.cc/en/Serial/Print)

This is a lot to go through right now. If you have any prior experience with coding, then most of this should simply be looking up the new syntax. If you aren't familiar with theses concepts, then don't try to go through all of the refrence right now. Instead focus on the aspects that you think will help you solve a particular exercise as you go through this workshop.

# Exercise  1.1 (Serial Print, strings)
Write  an  Arduino sketch to  print "Hello World!". Make sure to use correct Arduino sketch layout.

# Exercise  1.2 (for loops, variables)
Build  on the following Arduino sketch so that it prints a 10-level left-aligned pyramid of asterisks. Make sure you use the variable levels in your loop function.

void setup ( )   {
  int   levels   =  10;
}

void loop ( )   {
  Serial.print("*") ;
}


#Exercise 1.3  (arrays)
Write an Arduino sketch that creates the following array {0, 1, 2, 3, 4, 5, 6, 7, 8, 9} using a while loop.

# FUNCTIONS 

Functions are the building blocks for more advanced logic. Instead of writing all logic inside the central loop function, we can create functions to separate out logic, and  simply call those functions within  the loop.  Not only does this help us keep track of the specific purpose of parts of our code, but it also helps us keep  our code clean and manageable.

Writing functions in an Arduino sketch is identical to writing a function in any  C program. Simply define the output type, the name of the function, and  any inputs into  the function.


int functionName  (int input1, char input2) {
  // . . .  logic here . . .
}

In the snippet above, we have  a function called functionName with output type integer, and two inputs: an integer input1, and a char input2. As an aside, if you are familiar with C systems programming, you are probably used to dynamic memory allocation using the malloc() and free() commands, and returning allocated addresses. Arduino boards don’t have a heap, so you won’t be able  to take advantage of that here. All logic should be done at the stack and global level.

# Exercise 2.1
Write a function that takes in two integers as input, and returns the integer sum of them.


# Exercise 2.2
Write a function that,  when  given a integer n, produces an array of with the first n Fibonacci numbers in it.


# Exercise 2.3
Call the first function in the second function so that after the Fibonacci array is created, the sum  off all elements in the array is computed.

# Final Challenge

Write a function that takes a list of strings an prints them, one per line, in a rectangular frame. For example the list ["Hello", "World", "in", "a", "frame"] gets printed as:

*********
* Hello *
* World *
* in    *
* a     *
* frame *
*********
