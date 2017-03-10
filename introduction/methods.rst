======
Method
======

Let's say you have 3 variables, ``x``, ``y``, and ``z``. You are tasked with performing some function on them. In this case, you want to print out the variable added to 3, added to 6, and added to 9. You create this code
::

    x = 5
    y = 10
    z = 0

    print(x + 3)
    print(x + 6)
    print(x + 9)
    print(y + 3)
    print(y + 6)
    print(y + 9)
    print(z + 3)
    print(z + 6)
    print(z + 9)

This will do exactly what you want, but it's very repetitive. It would be better if we could pull out all the common code. We can do this with a method.

A method is a block of code that you can refer to anywhere in the program. You can give arguments, or predefined information, to a method so it can use currently existing data. Methods normally have 3 main things, a name, a *return type*, and an argument list.

Let's look back at the example above. The code that is repeated is
::

    print(n + 3)
    print(n + 6)
    print(n + 9)

Where n changes between x, y, and z. So how do we turn it into a method. Let's start by giving it a name. Since it always adds multiples of three, we could call it ``printThrees``. You can use any name, but it should relate to what the function does, and be short.

Parameter
---------
A methods parameters are like placeholders. When a function is invoked, you pass a value as a parameter. This value is referred to as the actual parameter or argument. The parameter list refers to the type, order, and number of the parameters of a function. Parameters are optional; that is, a function may contain no parameters. However, if a function has parameters, you must use them (unless you're using Python, which has optional parameters). You define parameters like so
::

    function(param1, param2, param3)

.. note::
    In Java and C++, parameters need types.

You can then use these parameters in the function. For the example above
::

    printThrees(number)

When calling a function, you must pass in parameters in the order they are listed, separated by commas.

In the method **body**, we would put all the code that repeats.
::

    printThrees([int] number)
        print(number + 3)
        print(number + 6)
        print(number + 9)

.. note::
    In the method body, we used the parameter number in the print statements. This is all you need to do to use parameters in their respective methods.

We can then invoke, aka **call**, this method with
::

    printThrees(x)
    printThrees(y)
    printThrees(z)

.. todo::
    Recursion
