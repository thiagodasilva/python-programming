# Getting Started


This first thing you’ll need to do is install Minecraft Pi Edition on your
Raspberry Pi. Instructions for this can be found here:
http://pi.minecraft.net/
Now you need to open a terminal and move to the mcpi directory using
cd mcpi. Then to run Minecraft Pi use the following command in the
terminal ./minecraft-pi.
Once you’ve created a new game in Minecraft Pi, familiarise yourself with
the controls:
- **w** Move the player forward
- **a** Move the player left
- **s** Move the player backwards
- **d** Move the player right
- **mouse** Change the player direction/camera angle
- **tab** Release the mouse
- **right** click Place block
- **left** click Smash block
- **scroll wheel** Change selected block
- **space** Jump (fly higher when flying)
- **double tap space** Fly (double tap again to stop flying)
- **shift** Crouch (fly lower when flying)
- **e** Block selection menu
- **1–8** Change block selection from inventory
- **esc** Open the options menu (also releases mouse)

Play around in Minecraft. Build some things. See how different blocks,
like water, react when you smash their neighbours.

To run Minecraft Pi you must be using a Desktop environment, you can’t
run it from the default command line interface that Raspbian boots to be
default.

## Programming with Python

Python is a programming language that is suitable for beginners. It is
easy to read and write.

There are two versions of Python 2.7 and 3. We will be using 2.7 in this
book. There are some minor differences between the two versions. You
can find out more online or use a feature in Ninja-IDE (mentioned below)
to identify compatibility issues in your code.

### The Minecraft Pi API

The Minecraft Pi API allows programmers to interface their code with a
Minecraft Pi game. In other words you can write a program that interacts
with Minecraft Pi, without changing the game itself.
The API is stored within a subdirectory of the mcpi directory. You will
need to copy it to the same directory as your Python code in order to use
it. Navigate to the directory you will save your Python code and run the
following terminal command:
```bash
cp -r ~/mcpi/api/python/* .
```
Don’t forget the full stop.

### Writing and Running Code

There are a number of choices for writing your Python code with your
Raspberry Pi. We’ll go over your options. Whichever program you choose
to write and run your code is down to preference. Try the different options
out and see what you like best.
Whatever option you use to write and run your code, make sure you are
in a Minecraft game world when you run it otherwise you will receive an
error.

#### Terminal + nano

The terminal is a way to interact with your Raspberry Pi using text. It
uses a command line interface instead of a graphical user interface. You
might be used to the graphical environment of your desktop or file browser.
A terminal can does the same things, but with text instead of mouse clicks.

To create and edit a python file using the terminal we use the nano text
editor. In a terminal move to the directory that you want to create your
Python program and run the following command
```
nano filename.py
``` 
Change the file name to whatever you want.

The Nano text editor uses the cursor to place text. You can’t change the
cursor position with the mouse, you can only change it with the direction
keys. Furthermore you can’t use ctrl-c and ctrl-v to copy and paste
text.

To save your file you use ctrl-o, followed by the name you want to save
your file as. To exit the nano text editor you use ctrl-x. You will be prompted
to save your file when exiting.

The nano text editor can be difficult to use for people who are familiar
with using graphical user interface instead of a command line interface.
After you have created your file you can run it with the following command
in a terminal:
```
python filename.py
```
If you leave out the filename, Python will open as an interactive console,
which allows you to write code on the fly instead of running it from a file.
This is perfect for quickly testing a piece of code:
```
python
```
To exit the interactive console use ctrl+z.

#### IDLE

IDLE is the default integrated development environment of Python. An
integrated development environment gives you a space to write code and
provides other features like debugging and syntax highlighting. There
are two versions of IDLE included with the Raspberry Pi, we will be using
IDLE, not IDLE 3.

IDLE is a very basic IDE. By default it opens into an interactive console,
which is perfect for testing code quickly without the need to save. To create
a new file that is not an interactive console, click on file > new window
or press ctrl + n.

Save the file using the file menu. Make sure you save the file in same
directory as the mcpi api directory.

To run a program that you have written in the text-editor window you
click on the run menu then run module or press the F5 key.
You can also your program from the terminal.

#### Geany

Geany is another IDE that is more robust than IDLE. It is used for programming
in a number of programming languages. There are more features
in Geany than IDLE and I suggest you explore what it can do.

Geany does not come pre-installed with Raspbian. To install it connect to
the internet and run the following commands in a terminal:
```
sudo apt-get update && sudo apt-get upgrade
sudo apt-get install geany
```

Geany will now be available under the programming section of the task
bar menu.

Once you’ve saved your program you can run it from Geany’s in-built terminal
or from a regular terminal.

#### Ninja-IDE

Ninja-IDE is relatively less well-known IDE than the other options. It is
an extremely well-made IDE that is specifically designed for Python. As a
result it has a number of very useful features for Python developers, like
compatibility highlighting between Python 2.7 and Python 3.

At the moment Ninja-IDE on the Raspberry Pi is a bit more complicated to
install. You can find instructions for it on my website:
http://bit.ly/11BasQ0

There is a run button on the side bar, which will run your program.

You can also open directories, which be managed as a project. There are a
number of useful plug-ins and colour customisations, which you can find
via the menu.
