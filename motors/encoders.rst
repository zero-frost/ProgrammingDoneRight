Encoders
========

An encoder is a sensor that measures motor movement, usually in the form of position or rotation. They are useful for getting precise movement from a mechanism by providing feedback to a PID (or other feedback) loop.

Relative Encoders
-----------------

Relative encoders detect changes in position relative to their starting position, which resets when they power off. Hall-effect quadrature encoders, the most common encoders in FRC, have A & B outputs that are used to count the number and direction of steps.

Relative encoders are generally used as either velocity or distance sensors. For example you can use the rate of the steps to calculate the RPM of a flywheel launcher. If you put an encoder on a wheel you can calculate the distance traveled by multiplying the number of steps by a constant.

Absolute Encoders
-----------------

Absolute encoders provide their position relative to a static point, even after a power loss or reboot. Absolute encoders have more complex outputs, like analog or PWM, and have higher resolutions than most relative encoders. Absolute encoders do everything relative encoders do along with providing accurate position, but they are more expensive and complex.

Absolute encoders are used in applications like swerve drive modules where their direction always needs to be relative to the robot. Absolute encoders must be used when the position readings need to be relative to the encoder and not its starting position.
