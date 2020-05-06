## External Stepper Motor Driver

This is a StepStick (or Pololu) style module designed to control large, externally mounted stepper motor drivers.

![](http://www.buildlog.net/blog/wp-content/uploads/2020/05/20200506_153427.jpg)

The StepStick style stepper motor drivers are used in countless designs, but sometimes they don't have as much power as you need. Stand alone stepper motor drivers can be found that drive huge motors with lots of current.

![](http://www.buildlog.net/blog/wp-content/uploads/2020/05/20200506_150742-scaled.jpg)



These driver generally have opto isolators on the inputs. This isolates the noise and power spikes that could damage your controller. These opto isolators generally run on 5V and can pull a little current. Many microcontrollers can handle that current, but 3.3V microcontrollers can't deliver the specified voltage. Also, most CNC controllers use a common enable signal. It could damage your microcontroller if that one signal is connected to multiple drivers.

This modules solves those problems. It uses a 74ACT245 buffer to drive the opto isolators. Each signal has its own 5V signal including the enable signal. The 5V comes from your motor power voltage (9-24VDC). Each module has its own power regulator.

The module is compatible with all StepStick style sockets including those designed for Trinamic SPI drivers. It directs the step, direction and enable signals through your existing motor connectors.

**Input Motor Voltage Range:** This module is designed to be run in a 9-24VDC range on the VMot pin. This is the voltage that would normally be sent the the stepper motors. The limiting factor is the 5V regulator. It generates heat proportional to the voltage. I ran it at 24V with all channels forced on (an unlikely mode) for over an hour and the part only got a little warm (no heatsink or fan). It was well below the rated temperature. The part is rated for 35V. If you can keep it cool, you get go a little higher. I chose the biggest regulator I could fit ([T.I. LM78L05ACMX/NOPB](https://datasheet.lcsc.com/szlcsc/1809280410_Texas-Instruments-LM340MP-5-0-NOPB_C131990.pdf))

There are other, similar modules, out there that do not have any active circuitry and just reroute the signal to a connector. This may not work and does not provide a buffer to protect your sensitive and expensive microcontroller.

![](http://www.buildlog.net/blog/wp-content/uploads/2020/05/labels.png)




