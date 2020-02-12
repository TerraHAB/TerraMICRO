.. _design-reqs:

*******************
Design Requirements
*******************

TerraMICRO's technical design is driven by making engineering decisions to meet
the design requirements listed in this section. All of these requirements must
be met before the mission takes flight, with test data to prove it.

By designing the vehicle to meet a set of requirements, we hold our engineering
decisions accountable and resist the temptations of scope creep and "cool
factor."

When we, as a team, elect to override one of these requirements, we will commit
to providing justification for doing so (even if the reason is *because we
thought it would be more fun this way* or *because we couldn't afford to buy
the parts needed to do it right.*)


Critical Design Requirements
============================

Regardless of the mission objectives, the HAB system must meet several key
design requirements in order to achieve mission success. These requirements
serve as success criteria and also as constraints to the design trade space.

Some requirements are non-negotiable, such as `FCC or FAA regulations
<https://www.ecfr.gov/cgi-bin/text-idx?rgn=div5&node=14:2.0.1.3.15#sp14.2.101.d>`_
for unmanned free balloons and other basic functions to ensure
a safe, controlled flight. Other requirements may come from
limitations related to cost, manufacturability, which stem from the TerraHAB
organization's own budgets. These critical requirements supercede any mission
or design requirements that contribute to meeting the mission's objectives.

.. list-table:: Critical Design Requirements
   :header-rows: 0

   * - The flight vehicle **must** include multiple independent cut-down
       mechanisms.
   * - The flight vehicle **must** have at least one redundant system capable
       of transmitting its coordinates to ground control.
   * - The flight vehicle **must** remain powered-on and airborne for at least
       3 hours.
   * - The flight vehicle **must** have a total mass of no more than 2.72 kg
       (6 lbs).


.. _mission-reqs:

Mission Success Criteria
========================

The objectives listed in this section provide the basis for TerraHAB's criteria
for success and drive all other mission requirements. These objectives steer
the vision and end goals for the mission and every subsystem or feature in the
end result should support at least one of these objectives.

.. list-table:: Example Engineering & Technology Objectives
   :header-rows: 0

   * - **In-Flight Balloon Monitoring**
     - A system will be able to monitor the temperature and pressure within a
       balloon and report that back to the HAB payload.
   * - **uHAB Avionics Platform**
     - Flight test uHAB as a flexible, expandable, and cost-effective platform
       to support many different mission profiles or payloads with all of the
       basics for a HAB launch included out of the box.
   * - **Open-Loop Altitude Regulation**
     - Limit maximum altitude and rate of ascent by the controlled release of
       helium during flight to prolong the mission duration. Maintain 75,000
       feet altitude for at least 30 minutes.
   * - **HD On-Board Video**
     - Horizon-looking full color video at 1080p @ 30 fps or better (1080p @
       60fps or 4K @ 30fps preferred).
   * - **Video Capture of Balloon Burst**
     - Capture the balloon burst event with minimum resolution of 720p @ 60fps
       or better. (720p @ 120fps or 1080p @ 120fps preferred)


Stretch Goals
-------------

There are several design features that are specific requests from TerraHAB
engineers. The flight system should meet these requests or provide
justification for not including them. These features are not required for
mission success, but it is expected that the TerraHAB team strives to
accomplish these goals.

.. list-table:: Example Stretch Goals & Desired Features
   :header-rows: 0

   * - **Remove Before Flight Pins**
     - Include externally accessible remove before flight pins to safe or
       disarm subsystems while on the ground, such as a power pin (included in
       uHAB), a startup sequence pin, a launch pin, and so on.
   * - **Status Indicators & Displays**
     - Include displays and self-test and status check codes to ensure that the
       balloon is stable and behaving nominally during testing, integration,
       and preparation for flight.
   * - **Simple Balloon Filling**
     - Simple and clear procedures during flight preparations, including a
       quick-disconnect from helium fill plumbing.
   * - **Vegetation Density Experiment**
     - Use NDVI with a commercially available RGB (VNIR) camera to estimate
       vegetation density from images in real time during flight. Minimum video
       quality 480p @ 30fps.


.. _system-reqs:

System Requirements
===================

The intent of this specification is to quantify and control the criteria
by which mission success is defined, and to provide traceability to each
subsystem's performance to ensure mission success is achieved by the
vehicle's design.

.. note::
   All of the systems demonstrated by this mission shall be thoroughly tested
   on the ground prior to launch. Flight data and telemetry recorded during the
   flight should be consistent with behavior observed during testing.


Avionics
--------
Since |uHAB| serves as the core avionics platform for TerraMICRO, avionics
requirements are inherited from |uHAB| requirements.

.. include:: uhab-reqs.rst

Power
-----


Flight Software
---------------


Telemetry
---------


Recovery
--------


Payload Bus & Interfaces
------------------------


Instruments & Sensors
---------------------


Altitude Regulation
-------------------
