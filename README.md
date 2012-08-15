Sharp-IR-sensor
===============

Code to read the distance measured by a Sharp GP2D12 IR sensor

This code was written for another project I worked on 
(https://github.com/PSU-AVT). It's meant to work with some asynchronous adc code
written for the other project. You can just swap out the adc calls with whatever
you are using on your system - it does not have to be asynchronous.
I'm putting this up as sample code. These sensors are not the easiest to work 
with and have some strange pitfalls. This code does not cover all the pitfalls,
because our mechanical design limits the sensors measureing range to the region
where these sensors are roughly linear (looking at the graphs in the datasheet
will make more sense).

This code should work fine with the same sensors and a 10bit adc, you will have
to modify the numbers in the formula ((float)4400/(adcGetVal(PIN) - 19)) - 1;
You can read more at http://acroname.com/robotics/info/articles/irlinear/irlinear.html. These numbers deal with linearlizing the values returned by the sensor.
