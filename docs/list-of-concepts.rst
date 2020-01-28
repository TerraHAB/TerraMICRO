.. _list-of-concepts:

List of Experiment Concepts
===========================


Stable Imaging Platform / Bus Attitude Control
----------------------------------------------

Active gimbals make for a (power hungry) off-the-shelf solution for image
stabilization. For a challenge one could build a gimballed camera mount from
scratch.

A more novel idea would be to control bus attitude. A senior design team from
2017 attempted to do attitude control with a reaction wheel, but I don't think
they had a way to dump momentum. A simpler (and more novel) approach would be
to use RC aircraft engines or drone motors to actively counteract wind forces.
A simpler objective could be using drone propellers for anti-spin control or
active ballast weights for anti-rocking control.


Altitude Control
----------------
Actively change the ascent or descent rate. For a simpler demonstration, only
control the ascent rate. For a challenge, maintain an altitude set point. For a
greater challenge, extend the flight duration by controlling altitude.


Intra-balloon Environment Sensors
---------------------------------
Develop a sensor platform to measure environmental conditions (temperature,
pressure, humidity) within the balloon from ambient, through filling, and
finally through the burst event. Send the data to the main payload storage over
a wired or wireless link.

As a stretch goal, instrument the bus with environmental sensors. Compare
balloon internal conditions to ambient ones add correlate it with altitude rate
of change or burst events.


On-board Image Processing
-------------------------
Perform image processing (of any level) on images or video on the payload
electronics in flight. For an extra challenge, apply any of the following
constraints:

- Payload electronics do not exceed $30.
- Image processing algorithms have a practical or scientific use beyond a
  simple demonstrator.
- Image processing takes place on an FPGA. Bonus if it occurs in real time.
- Image processing includes data fusion with additional sensors or camera
  sources.


Real-time Data Transfer
-----------------------
Receive real time telemetry and payload data in flight. For a greater
challenge, send commands from a ground station during the flight. For a simple
demonstration, send limited health and status telemetry. As a stretch, send
rich data (like photos or live video) to a ground station in flight.


Characterize Atmospheric Composition
------------------------------------
Measure atmospheric composition along the balloon's ascent. Characterize how
composition changes with altitude. For a greater challenge, use multiple
flights to see how composition changes with altitude from different
geolographic locations, time of day, time of year, or different weather
conditions.


Characterize Radiation Environment
----------------------------------
Measure radiation intensity along the balloon's ascent. Characterize how
intensity changes with altitude. For a greater challenge, use multiple flights
to see how intensity changes with altitude from different geolographic
locations, time of day, time of year, or different weather conditions.


Model and Test Latex Balloon Burst Conditions
---------------------------------------------
Prior to launch, predict the conditions that lead to the balloon's burst event.
Instrument the payload and balloon to test the model in flight. For an extra
challenge, apply any of the following constraints:

- Model the burst event only using parameters that can be measured in flight.
- Test the model on the ground with simulated atmospheric conditions and a
  sub- or full-scale balloon.
- Record high-speed video of the balloon bursting in flight.


Controlled Descent
------------------
After balloon cutdown, control the descent of the payload. For a simpler
challenge, use a reefed parachute. For a greater challenge, steer the descent
path using a parafoil or aero control surfaces.


Vegetation Density Experiment
-----------------------------
Measure vegetation density using NDVI with cameras in flight. For a greater
challenge, do the image processing on-board.
