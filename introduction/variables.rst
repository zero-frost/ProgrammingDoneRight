==================
Variables
==================

In programming, a variable is something can be given a value. A variable's name can be the letter a, the word frog, or just nonsense, like dj6vEc1418. You can give a variable a value using the ``=`` sign::

    x = 3
    frog = True
    dj6vEc1418 = "Apple"


Notice that the value assigned to a variable can change, hence the name variable. It can be a number, a word, or even another variable.

Variables are probably the most used programming feature. They help keep track of data, and are the essence of object-oriented programming, which is what FRC
is.

In FRC, variables are usually assigned to things like motors, sensors, and joysticks.

Types
-----
In Java and C++, variables must be given a **type**. Types are either primitive types or :ref:`classes_label_`.

Primitive types are types that are builtin and have no class associated with them. These are types such as ``int``, ``double``, ``float``, ``long``, and ``boolean``.

.. note::
    The exact primitive names differ between Java and C++.

``String`` is another common type, but it is also a builtin class. Using the example above, you the types of the 3 variables are
::
    int x = 3
    boolean frog = True
    String dj6vEc1418 = "Apple"

Naming
------

Giving variables good names is an integral part of writing good code. You will most likely be working with other people on you code, and it is important that they can read and understand your code just as well as you can. By naming your variables clear, concise names, it makes reading code in the future 10x easier. For example::

  ts = 100
  topSpeed = 100

It is clear that the name ``topSpeed`` is a better variable name, because you can understand what the variable is. ``ts`` on the other hand isn't very understandable, and you'll have to look at other code to figure out what it means.
