User-defined functions
**********************

Introduction
============

There is still a lot of duplicated code --- the actual drawing of the rectangle
--- around. If you need to copy and paste code, that is usually a sign of
lacking abstractions. (Programmers call it a *code smell.*)

Functions are one way to express abstractions in Python. Let's take
``turtle.reset()`` for example. It is actually an abstraction for a number of
steps, namely:

* Erase the drawing board.
* Set the width and color back to default.
* Move the turtle back to its initial position.

A function can be defined with the ``def`` keyword in Python::

    def line_without_moving():
        turtle.forward(50)
        turtle.backward(50)

You can access variables in functions as well::

    size = 50
    def line_without_moving():
        turtle.forward(size)
        turtle.backward(size)

.. important::

   Python uses *whitespace to identify blocks of code* belonging together.
   While other languages use special characters (like curly brackets ``{}``) in
   Python a block is introduced with a colon at the end of the line and
   subsequent commands within a deeper indentation level --- usually 4 spaces.
   The block ends with the first line with a lesser indentation level.
   
   If you mix up tabs and spaces the interpreter is going to complain. Make
   sure to always use one or the other.

A function for a square
=======================

Exercise
--------

Write a function that draws a square. Can you see how you could improve the
tilted squares program with that and greatly relieve experimentation?

Solution
--------

::

    def tilted_square():
      turtle.left(angle)

      turtle.forward(50)
      turtle.left(90)
      turtle.forward(50)
      turtle.left(90)
      turtle.forward(50)
      turtle.left(90)
      turtle.forward(50)
      turtle.left(90)

    angle = 20            # <--
    tilted_square()
    tilted_square()
    tilted_square()


A function for a hexagon
========================

Exercise
--------

Write a function that draws a hexagon.

.. image:: /images/hexagon.png

Now combine that function into a honeycomb.

.. image:: /images/honeycomb.png

Solution
--------

::

    def hexagon():
        turtle.forward(100)
        turtle.left(60)
        turtle.forward(100)
        turtle.left(60)
        turtle.forward(100)
        turtle.left(60)
        turtle.forward(100)
        turtle.left(60)
        turtle.forward(100)
        turtle.left(60)
        turtle.forward(100)
        turtle.left(60)

    hexagon()
    turtle.forward(100)
    turtle.right(60)

    hexagon()
    turtle.forward(100)
    turtle.right(60)

    hexagon()
    turtle.forward(100)
    turtle.right(60)

    hexagon()
    turtle.forward(100)
    turtle.right(60)

    hexagon()
    turtle.forward(100)
    turtle.right(60)

    hexagon()
    turtle.forward(100)
    turtle.right(60)

