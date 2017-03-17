=======
Classes
=======

Classes can best be thought of as blueprints for your program. You use classes to create *templates* for objects. **They are not objects themselves. They are just the blueprints.** You create objects from classes, the same way you create a building from a blueprint. In this blueprint, you can have variables and functions.

To create a class, all you need to do is use the ``class`` keyword.

.. tabs::

    .. code-tab:: java

        public class MyClass{
            //Variables and methods go here
            int variable;
        }
    .. code-tab:: c++

        class MyClass{
            //Variables and methods go here
            public:
                int variable;
        }
    .. code-tab:: py

        class MyClass:
            //Variables and methods go here


Then, when you want to create a new **object** of that type, you create it like any other variable. You create new objects with the ``new`` keyword.

.. tabs::

    .. code-tab:: java

        MyClass object = new MyClass();

    .. code-tab:: c++

        MyClass object();
        // OR
        MyClass object2 = new MyClass();

    .. code-tab:: py

        object = MyClass()

When accessing methods in a class, all you need to do is

.. tabs::

    .. code-tab:: java

        object.variable = 3;

    .. code-tab:: c++

        object.variable = 3;
        // OR
        object2->variable = True;

    .. code-tab:: py

        object.variable = 3


.. note::
    Check C++ syntax rules for extra cases

The same syntax is used to access variables of an object.
::

    object.variable = True
    print(object.variable2)

Constructors
------------
When you create a new class, you must create a constructor. The constructor is the method that is called when you create a new class. It is similar to a method, except it has no return type, and must be named the same thing as the class name. If you create a ``Dog`` class, the constructor will be ``public Dog();`` Constructors, like methods can accept arguments.
`
