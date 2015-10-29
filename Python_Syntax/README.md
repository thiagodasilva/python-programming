# Python Syntax

Syntax is the basic set of rules that programming languages use. These rules are
Python’s equivalent of grammar and punctuation.

Python’s syntax is necessary for structuring a program so that the computer can
understand the instructions the programmer is giving it. Without syntax the
computer would not understand what it was being told to do.

Understanding syntax is necessary as it underpins everything in programming.
Without it you can’t communicate with the computer.

This chapter covers the fundamentals of Python’s syntax. At the start of this
chapter there are several programming challenges using Minecraft Pi. Each
challenge states the knowledge you require to complete the task. Before starting
the exercises it is recommended you complete the first Python tutorial on
Codecademy, unless you’re feeling adventurous. If you can’t quite remember how
to use a certain concept we’ve included reference for everything you have
covered over at Codecademy. As with every chapter in this book you can the
reference part of this chapter in a number of different ways:
* look at the references to support your understanding when attempting the exercises
* use it when you need extra help to understand a topic introduced in Codecademy
* refer to it to as a reminder when you’re writing a program
* let it help you with revision for your exams.

The book was written to support you when you’re learning to program, so
use it for whatever support you need.

## Minecraft Exercises

Let’s practice variables with Minecraft on the Raspberry Pi. Each of these
exercises introduces you to some code that uses variables. These exercises
will show you how changes the player’s position in Minecraft and
also stop the player from destroying blocks. For each exercise we’ll tell
you the concepts you’ll practice and its difficulty. We’ll even explain the
Minecraft bits of code to you as you go.

When using these exercises, identify where the variables are and how
they’re being used. This will help you understand what’s going on. If
you’re unsure of something refer back to the explanations earlier in the
chapter.

When you think you get it, try the extensions exercises. You can also be
creative and try your own ideas by changing, rearranging and combining
the code.

### Teleport the Player

> #### Skills & knowledge
> Skills and knowledge we’ll practice in this exercise
> * variables
> * Integers
> * Co-ordinates
> * The Minecraft API
> * Setting the player position

Let’s get started with your first program using Python and the Minecraft API.
We’ll start with something simple, teleporting the player to a new location with
integers.

Your character has a position in the Minecraft world. This is represented by
three numbers that you can see in the top left corner of the game window. These
numbers are known as x, y and z.

> TODO: Include image here

When you move you’ll notice that these numbers change. These variables are
co-ordinates and represent your position in Minecraft’s 3D world as shown in
figure 3.1.1: y represents height and x and z represent your position on a flat
plane.

As well as moving your character with the keyboard, you can change their
position using Python. We’ll take you through the code to do that.

#### Instructions

Create a new file and name it teleport.py. Move the Minecraft API folder to the
same folder, steps to achieve this can be found on page [page number].

Now open the teleport.py file in a text editor. First of all we need two lines
of code that connect to our program to Minecraft. You will use these two lines
of code in all programs that interact with Minecraft. Add these two lines at the
top of your program:
```python
import mcpi.minecraft as minecraft
mc = minecraft.Minecraft.create()
```
We’ll now create the three integer variables
that represent the x, y and z position that we want to teleport our character
to. For now let’s set our destination to co-ordinates (10, 11, 12).
```python
x = 10
y = 11
z == 12
```
Finally we need a single line of code that will move the player.
```python
mc.player.setTilePos(x,y,z)
```
This is a function, you’ll learn more about functions later. What you need to
know is that the setTilePos(x,y,z) bit at the end of the line tells Minecraft to
change the player’s position using the three variables that we just set.

Here’s the full code. We’ve included some comments so that it’s easy to
understand:
```python
#connect to Minecraft import mcpi.minecraft as minecraft
mc = minecraft.Minecraft.create()

”””set x,y and z variables
to represent coordinates”””
x = 10
y = 11
z = 12

#change the player’s position
mc.player.setTilePos(x,y,z)
```
Now let’s run the program. Do these steps:
1. . Open Minecraft Pi (instructions on page [page #number])
2. Open up a terminal and change the directory to where you saved your program
(instructions on page [page number]).
3. Type python teleport.py in the terminal and press enter.

Well done! Your program should now run and your character will be teleported to
co-ordinates (10,11,12).

#### Extensions

* Change the values of the x, y and z variables
* Use negative values for the x, y and z variables

> ### Alert:

> Don’t use a value larger than 127 for the x and z variables or a value larger
> than [find value] for the y variable. The Minecraft Pi world is only small and
> numbers bigger than this will cause the game to crash [check this]Don’t use a
> value larger than 127 for the x and z variables or a value larger than [find
> value] for the y variable. The Minecraft Pi world is only small and numbers
> bigger than this will cause the game to crash [check this]

### Teleport the Player Precisely

> #### Skills & knowledge
> Skills and knowledge we’ll practice in this exercise
> * Variables
> * Floats
> * Following instructions
> * The Minecraft API
> * Setting the player position in Minecraft with Floats

In this exercise we’ll not give you the code to copy, instead we’ll give you
help to work out what you have to do. Don’t worry, it’s pretty similar to the
last exercise, with some tiny differences.

In the last exercise you learned how to set the player’s position using
integers. You may have noticed that the location of the player in the top left
of the window has a decimal place. For more precise movement across blocks, the
location of the player is actually stored as a float in the game. In this
exercise you’ll set the player’s position using Floats.

#### Instructions

Using the previous exercise as a guide follow these steps to teleport the player
using a float value:

1. create a new file named teleportPrecise.py (make sure the Minecraft API
folder is in the same directory)
2. Open the teleportPrecise.py file and add the two lines of code that connect
our program to the Minecraft game
3. Define three variables named x, y and z and set their values to floats
4. Add the following line of code `mc.player.setPos(x,y,z)`
5. Open a Minecraft world and run the code

Notice there is a difference between `mc.player.setPos(x,y,z)` and
`mc.player.setTilePos(x,y,z)`, which we used in the last exercise:
* `setPos(x,y,z)` uses floats to set the player’s position
* `setTilePos(x,y,z)` uses integers to set the player’s position

#### Extension

* Change the values of x, y and z variables. Use a mixture of positive
and negative floats.
* See what happens when you only change the decimal values slightly.

### Teleportation Tour

> #### Skills & knowledge
> Skills and knowledge we’ll practice in this exercise
> * Reusing Code
> * Changing values
> * Time
> * Setting the player position in Minecraft

In this exercise we’ll practice changing the values of variables. We’re going to
reuse some code from the first exercises to teleport the player to several
locations across the map. The player will teleport to one location, wait a few
seconds then teleport to another location.

For this we’ll show you how to make Python wait for a few seconds.

We’ll be using the code from the first exercise. We’ve copied it here so that
it’s easier for you. You can use the code from the second exercise if you want
and it’ll work just the same.
```python
.
 1 #connect to Minecraft
 2 import mcpi.minecraft as minecraft
 3 mc = minecraft.Minecraft.create()
 4
 5 #set x, y and z variables
 6 x = 10
 7 y = 11
 8 z = 12
 9 #change the player’s position
10 mc.player.setTilePos(x,y,z)
```
Let’s get started. As usual do the following steps. You’ll need these steps
for every exercise so we’re going to stop telling you to do them from now
on.

1. Create a new file as usual, name it something simple that explains
it’s purpose, in this example use tour.py
2. Make sure the Minecraft API is in the same directory
3. Open the file in a text editor

Now let’s edit the code:

1. Copy the code from `teleport.py` into `tour.py`
2. On line 4 add the following code: `import time`
3. On line 11 add the following code: `time.sleep(5)`
4. Copy lines 5 to 10 and paste them on line 12 onwards
5. Change the values of the x, y and z variables on lines 13, 14 and 15
respectively
6. Open a Minecraft world and run the code

You should see the player teleport to the first location, wait five seconds,
then teleport to the second location. The `time.sleep(5)` line makes Python
wait for five seconds.

#### Extensions

* Wait a different amount of time
* Copy the code to move the player as many times as you want
* Change only one variable: you don’t have to change every variable every time

### Stop Smashing Things

> #### Skills & knowledge
> Skills and knowledge we’ll practice in this exercise
> * Booleans
> * Problem solving
> * Immutable Blocks

Here’s a nice simple task to finish things off. In Minecraft it’s easy to
smash blocks. This is useful when you want to smash things, but can be
annoying if you’ve spent ages building something really cool. In this exercise
we’ll make it so that the player can’t smash blocks.

#### Instructions

With `setting(world_immutable, True)` you can make blocks immutable. Immutable
is another way of saying things cannot be changed. Here’s the code you need to
do this:
```python
1 import mcpi.minecraft as minecraft
2 mc = minecraft.Minecraft.create()
3
4 mc.setting(world_immutable, True)
```
After you’ve created this program and run it you’ll notice that you can’t
smash blocks.

Your task now is to copy your program into a new file and change it to
allow the player to smash blocks. *Hint*: there’s a boolean in there.

#### Extensions

* Try firing an arrow with your bow. What happens? Why do you think this
is?

## Variables and Data Types

A variable stores a piece of data in the computer’s memory.

There are different types of data that a variable can store including numbers
and strings. These data types can store a wide variety of things, from
names to GPS co-ordinates.

Variables are one of the most important concepts to learn as they are fundamental
to programming.

> ### Variable

> Variables store data in a computer’s memory. This data can be a number of
> things such as numbers, letters and symbols. Every variable has a name and a
> value. The = symbol is used to set the value of a variable. When setting a
> variable, the variable name is always on the left of the = and the value is
> always on the right.

> #### Expression:
> ```python
> 1 variableName = value
> ```
> #### Statement:
> ```python
> 1 age = 23
> 2 height = 162.5
> 3 canDrive = True
```

When creating a variable you need three things: a variable name, an equals
sign = and a value. In this example ”speed” is the variable name and 30 is
the value:
```python
1 speed = 30
```
The variable name always goes on the left of the equals sign and the value on
the right.

The name of the variable can be whatever you want, although it is better to name
it something that explains its purpose. This makes it easier for the programmer
to understand what is going on in the future.

Variables can hold data of various types. In this chapter we will cover three of
these data types:
* Integers
* Floats
* Booleans

### Integers

You have come across integers almost every day of your life. Integers are whole
numbers. For example there might be 12 people in the street, you are going to
meet 5 friends, or you’ve just bought 2 apples. The number of these things are
all described with integers.

Integers can represent positive and negative numbers. Negative numbers are
numbers less than 0. They have a - sign before the number.

Using integer in Python is easy. Say that we want 5 cats to take photos of. In
Python we can declare an integer variable to represent this like so:
```python
1 cats = 5
```
As with all variables, the variable name is written at the start of the line. We
then put an equals sign to tell Python that we’re assigning a value to a
variable. Finally we write the integer value that we want to store in the
variable.

The value side of the integer variable should not be written with any spaces,
letters or symbols. Otherwise Python will get confused and won’t understand
that you want to create an integer. The - symbol is the one exception, which
you must use if you want to create a negative value.

To say the temperature is negative 5 degrees would set a variable like so:
```python
1 temperature = -5
```
> ### Integers

> A data type for whole numbers, which are either positive or negative. For
> example 10, 32, -6, 194689 and -5 are all integers. 3.14 and 6.025 are not
> integers as they have decimal places.

> #### Expression
> ```python
> 1 12
> ```

> #### Statement:
> ```python
> 1 age = 12
> ```

### Floats

Not all numbers are whole numbers. Decimal places are used to represent values
that can’t be described with whole numbers. For example you might have half
(0.5) an apple, you hourly pay is £7.34 or the market is 2.6 miles away from
your house.

Floating numbers are used instead of integers when more precise data is
required.

Integers only makes sense where things are measured in whole numbers, like you
have 2 cats. It wouldn’t make sense to have two and a half cats.

Floats on the other hand represent numbers where it makes sense to have
fractions of numbers. Like the temperature can be -6.3 degrees, 17.4 degrees,
18.9 degrees and so on.

Floats can represent whole numbers, but integers cannot represent numbers with
decimal places.

You can link this with Maths. Integers are used for discrete data and floats
are used for continuous data.

In Python declaring a float variable is achieved in the same as declaring
all other variable types, except you include a decimal point within the
number value. For example to say we have 1.34 litres of water:

```python
1 litresOfWater = 1.34
```
To create a negative float you precede the number with a - symbol:
```python
1 temperature = -4.37
```

> ### Float

> Number values with decimal places, either positive or negative. For example
> 3.14, 6.025, 105896.7584926, -8.276 and 1.00 are all floats.

> #### Expression:
> ```python
> 1 17.5
> ```

> #### Statement:
> ```python
> 1 tax = 17.5
> ```

### Booleans

Booleans are an interesting data type. There are only two possible values for a
boolean, True or False.

Think of a basic light switch, it can be either on or off. This is how a boolean
works, it is either True (on) or False (off).

In Python we can declare a boolean variable like this to represent that the
light is on:
```python
1 light = True
```
When the light is off we would write this:
```python
1 light = False
```
The first letter of True and False values must always be capitalised.

Booleans have a number of uses. They are particularly useful for representing
answers to questions with either True or False. For example, is someone asleep?
Is the dog hungry? Is it raining?

> ### Boolean

> Data that is either True or False. Also represented as 1 or 0, On or Off.

> #### Expression:
> ```python
> 1 True
> 2 False
> ```

> #### Statement:
> ```python
> 1 canFly = True
> 2 isBird = False
> ```

### Changing Values of Variables

You can change the value of a variable at any time. You do this in the same way
as declaring a variable, with an equals sign. For example, say we declared a
variable ”cats” as 5 and we then wanted to change it to 10 as we bought more
cats. It would look like this in Python:
```python
1 cats = 5
2 cats = 10
```
The cats variable started out as 5, but then it is changed to 10. When it is
changed the cats variable forgets the old value and remembers the new one.
Pretty simple.

> Alert: Python reads programs in line order, starting at the top and ending at
> the bottom. In other words it will execute code on the first line, then the
> second line and so on. Keep this in mind when changing the value of a
> variable.

## Whitespace and Statements

Python needs to know when to stop reading one instruction in your code and when
to start reading the next one. This is where statements and white space come in.

Think of sentences in English. If I didn’t include any full stops in my
sentences you would find it very difficult to understand what I was trying to
tell you. Take following text:

> There are no dragons in the pub there is a witch

That is quite difficult to understand. However with the correct punctuation:

> There are no dragons. In the pub there is a witch.

See what I mean? By using full stops my sentence becomes easier for you to
understand. It makes it easier to communicate. And that is what syntax in
programming is about, clearly communicating instructions to the computer.

### Statements and Line Breaks

Think of a single instruction in your code as a sentence. To end a sentence in
English you use a full-stop. Instead of a full stop, Python uses a new line to
indicate the end of an instruction.

Each instruction on a new line in Python is called a statement. Python requires
a new line between each statement so that it can see where one statement ends
and another begins.

For example if we wanted to create a three variables in Python, we would write
it like this:

```python
1 socks = 12
2 human = True
3 age = 25
```

Notice how each statement is on a new line. This means Python can understand
that you want to create three variables.

If you don’t put each statement on a new line Python will get confused:

```python
1 socks = 12 human = True age = 25
```

This code will confuse Python and it will not be able to follow your
instructions. It doesn’t know where one statement starts and another begins.
When Python is confused it won’t do what you want it to do. It will tell you it
is confused with an error message.

### Indentation
Sometimes it is necessary to indicate that some code belongs in a group.
This is important for reusing code, trying different options and repeating
the same instructions. Python uses indentation and spaces for these
things.

> Alert: Indentation is important in Python. We won’t cover this topic in depth
> until later. For the moment it is important to remember not to use the tab key
> or put in lots of spaces at the start of a line as this will confuse Python,
> cause errors, or make your program do something unexpected

## Comments

Comments are statements in your code that the Python interpreter ignores.
Statements that are comments don’t do anything. They are useful though.

Comments can be used to write notes in your code so that you can read what
pieces of code do in the future. They can also be used to stop the interpreter
reading statements in your code. This is useful when you’re testing or trying to
find bugs and errors.

In Python there are two ways to write comments: on a single line or on multiple
lines.

> ### Single Line Comments

> Comments tell the Python interpreter not to read statements with comments.
> Single line comments only block a single line from the Python interpreter. The
> # symbol indicates the start of a comment.

> #### Expression:
> ```python
> 1 #Commented text
> ```

> #### Statement:
> ```python
> 1 # Sets characteristics of a person
> 2 name = ”Helen” #person’s name
> ```

### Single Line Comments

Let’s look at different ways to use the single line comment:
```python
1 #We have 5 cats
2 cats = 5
```

In this code the Python interpreter would ignore the first line, but would read
the second line.

If you wanted the interpreter to ignore the second statement as well you
would put a hash sign at the start of the line like this:
```python
1 #We have 5 cats
2 #cats = 5
```

In this way Python would not create the variable cats and not set it to 5.
The comment makes it ignore that statement.

You don’t have to put a comment at the start of a line. You can put it at
the end, as long as there is a complete statement on that line. For example:
```python
1 cats = 5 #We have 5 cats
```

This would work and create a cats variable with a value of 5.

However if we were to move the comment symbol earlier in the line (e.g.
before the 5) we would get an error. The error would occur because the
statement is not complete:
```python
1 cats = #5 We have 5 cats
```

Python would get confused as it expects you to include a value, but there
isn’t one as it ignores everything after the start of the comment. Avoid
this.

### Multi-line Comments

Sometimes you want Python to ignore several lines of code. You might have a long
explanation of what the code does or you simply want to block it from reading
large sections of code while you’re debugging. Writing the comment symbol at the
start of each line is tedious and time consuming for a large number of lines. We
therefore use multi-line comments to achieve this.

Multi-line comments in Python block out several lines of code, which the
interpreter will ignore.

The same principles apply to multi-line comments as single line comments, but
the syntax is different. Here is an example:
```python
1 ”””This program takes picture of ducks.
2 No code has been written yet,
3 but we’re hopeful it will work”””
```

Multi-line comments in Python start with three double quotation marks
on the first line that you want to block. It finishes with three more double
quotation marks at the end of the last line you want to block out.

> ### Multi Line Comments

> Comments tell the Python interpreter not to read statements with comments.
> Multi line comments block out several lines of code.

> #### Expression:
> ```python
> 1 ”””Commented
> 2 statements
> 3 go here”””
> ```

> #### Statement:
> ```python
> 1 ”””We have five cats
> 2 Jonesie likes swimming
> 3 The other four don’t”””
> ```
