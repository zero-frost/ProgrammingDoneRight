PID Control
===========

PID
  Proportional, Integral, Derivative feedback loop

Gain
  Amount of output given from each of the components of PID.

Feedforward
  A known value supplied to the output as a guesstimate so the PID only has to make minor corrections.

PID Control lies at the heart of any advanced robotics motion. Essentially, it is a way of controlling something, i.e. a wheel or an arm, using information gathered by the surroundings, In robotics, data is usually gathered through sensors, like encoders, range sensors, light sensors, etc. Using this data, robots can determine how they should act.

Imagine you are driving a car and you see a stop sign. When you're about, 200ft away, you start applying the brakes the car starts slowing down. As you get closer, you keep your foot on the brake. If you don't think you're slowing down enough, you push harder. If the car will stop too far away, you let off the brake a little, so you get exactly where you want to be. This is an example of a feedback loop. You had a task (stopping), and you used information gathered by your surroundings (distance from the stop sign measure with your eyes) to cause an mechansim (your foot on the brake) to act accordingly.

In robotics, the same concept can be applied. Many teams use PID control to drive during autonomous, using encoders as their sensor, shooting, using cameras as their sensor, or rotating, using gyros as their sensor.

The main equation for PID Control is::
    output = P * error + I * total_error + D * delta_error

Each of these parts is explained below.

Which ones to use
-----------------
P control is best used on slow moving parts that aren't subject to overshooting, or parts of the robot that don't need complete accuracy. Turning to a certain degree, for example, can be done with just P in some cases (but not all).

The most common control loop is PI. It combines simple P control with the fine tuning feature of an Integral gain.

PID isn't completely necessary in FRC.

Proportional
------------

``P * error``

Proportional control is using a predetermined constant (``kP``)to control how much a mechanism can move. Every time the PID code is run, the error is calculated, and the proportional gain is multiplied to this. In the car analogy, lets say the pressure you were applying was inversely proportional to the distance you were from the stop sign. ``P = 1/(error^2)`` and ``error`` is distance from the stop sign. (Note, P is 1/error^2 because you want the output to be 1/error.)

========  ======
Distance  Output
========  ======
200        .005
150        .0067
100        .001
50         .02
10         .1
1          1
========  ======

Using this P value, we apply more pressure the closer we get, causing us to slow down.

Using only Proportional control can be done, and is usually better for slow moving mechanisms, or mechanisms where you don't need com

Integral
--------
When controlling a motor with just P, you may find that it oscillates. This happens because it has too much power when it gets to the setpoint, and it overshoots. Then when it tries to correct, it overshoots again, and this cycle continues. One way to reduce this is to lower ``P``. This could have some bad side effects though. By reducing ``P``, your motor may not get *all* the way to where you want it to. It may be off by a few degrees or rotations. To overcome this **steady-state** error, an Integral gain is introduced.

If you've taken calculus, you know the integral is the area under a curve or line. It's the same with PID. The Integral gain is the sum of all the past error. This means the gain will increase more and more the longer the motor isn't where it's supposed to be.

Even though this reduces steady state error, it may increase settling time. If you notice it oscillating a little bit before settling, you may need a Derivate gain.

Derivative
----------
Derivative gain works by calculating the change in error. By finding this change, it can predict future system behavior, and reduce settling time. It does this by applying a brake more or less. This can be useful if it is imperative that you don't overshoot. This isn't even used in the industry much, but if you find yourself with long settling times, it may help to introduce a Derivative gain.

Tuning Method
-------------
.. todo::
  Zeiger-Nicols
