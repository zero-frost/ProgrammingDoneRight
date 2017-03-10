==================
Variables
==================

In programming, a variable is something can be given a value. A variable's name can be the letter a, the word frog, or a mix of letters and numbers, such as player2. You can give a variable a value using the ``=`` sign.

.. tabs::

   .. code-tab:: java

       int x = 3
       boolean frog = true
       String player2 = "Tim"

   .. code-tab:: c++

       int x = 3
       bool frog = true
       string player2 = "Tim"

   .. code-tab:: py

       x = 3
       frog = True
       player2 = "Tim"

Notice that the value assigned to a variable can change, hence the name variable. It can be a number, a word, or even another variable.

Variables are probably the most used programming feature. They help keep track of data, and are the essence of object-oriented programming.

In FRC, variables are usually assigned to things like motors, sensors, and joysticks.

Types
-----
In Java and C++, variables must be given a **type**. Types are either primitive types or :doc:`classes`.

Primitive types are types that are builtin and have no class associated with them. These are types such as ``int``, ``double``, ``float``, ``long``, and ``boolean``. All primitives are lowercase.

.. tabs::

    .. code-tab:: java

       int x = 3 //x is of type 'int'
       boolean frog = true //frog is a boolean
       String player2 = "Tim" //player2 is a String. String is not a primitive, although you can create them the same way. String player2 = new String("Tim") would also work.

    .. code-tab:: c++

       int x = 3
       bool frog = true //note in java, 'boolean' is the name of the boolean primitive. In c++, it is just 'bool'.
       string player2 = "Tim" // In C++, string is lowercase, but not a primitive. You must include "string".

    .. code-tab:: py

       '''Python has no types'''
       x = 3
       frog = True
       player2 = "Tim"

Once you create a variable of a certain type, you can't assign a value not of that type to it. Because Python has no types, you can always change what type of value a variable holds.

Naming
------

Giving variables good names is an integral part of writing good code. You will most likely be working with other people on you code, and it is important that they can read and understand your code just as well as you can. By naming your variables clear, concise names, it makes reading code in the future 10x easier. For example::

  ts = 100
  topSpeed = 100

It is clear that the name ``topSpeed`` is a better variable name, because you can understand what the variable is. ``ts`` on the other hand isn't very understandable, and you'll have to look at other code to figure out what it means.

Conventions
^^^^^^^^^^^
..  tabs::

    .. code-tab:: java

        final int CONST = 3; //Constants should be all UPPERCASE
        class MyRobot{} // Classes should be UpperCamelCase
        int joystickButton = 2; // Variables should be lowerCamelCase
        public void getGyroHeading(){} // Methods should be lowerCamelCase

    .. code-tab:: c++

        final int CONST = 3; // Constants should be all uppercase
        class MyRobot{} // Classes should be UpperCamelCase
        int joystickButton = 2; // Variables should be lowerCamelCase
        public void getGyroHeading(){} // Methods should be lowerCamelCase

    .. code-tab:: py

        CONST = 3 # Constants should be UPPERCASE
        class MyRobot # Classes should be UpperCamelCase
        joystick_button = 2 # Variables should be lowercase_with_underscores
        def get_gyro_heading(): # Methods should be lowercase_with_underscores

.. note::
    None of these rules are required. If your team already has conventions in place, use them. However, if you aren't sure on rules to follow, these are simple and easy to read.
