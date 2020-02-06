.. _uhab:

.. ----------------------------------------------------------------------------
.. -- Define substitutions here --

.. |uHAB| replace:: μHAB
.. Substitutes |uHAB| in place of |uHAB| when rendering this text.

.. ----------------------------------------------------------------------------


*******************
|uHAB| Architecture
*******************

.. note::
   |uHAB| is under active development. Visit the project's GitHub page for
   `µHAB designs and documentation <https://github.com/RIT-Space-Exploration/uHAB>`_.


.. _uhab-background:

Purpose
=======

The purpose of |uHAB| is to provide a flexible, expandable, and affordable
platform that contains all of the necessary functionality for a high-altitude
balloon mission without the hassle of starting a completely new design from
scratch.

**Flexible**:
|uHAB| contains a wealth of available I/O that is broken out to easily
accessible headers. Both 5V and 3.3V digital pins are available for ease of
future component integrations. The powerful 300MHz, 32-bit microcontroller has
capabilities for CANbus, EBI/EMI, Ethernet, I²C, IrDA, LINbus, MMC/SD/SDIO,
QSPI, SPI, SSC, UART/USART, USB, x24 16-bit ADC (with oversampling), and x2
12-bit DAC. |uHAB| also features selection headers for multiple types of
antennas and remove-before-flight safes.

**Expandable**:
The layout of the PCB includes the familiar pinout of the common Arduino Mega
so that commercial Arduino shields may be utilized. Additional I/O is available
separately. The microcontroller selected offers enough processing power to
handle many more additional tasks and the available power supply allows for
some limited draw for future expansion modules called *helmets*.

**Affordable**:
|uHAB| will contain only the components necessary for a successful mission as
outlined below. Extra functionality will be available in the form of completely
separate additional *helmets* as needed. By reducing the functionality to a
minimum, |uHAB| lowers the overall costs associated for a HAB launch and allows
for more expansion.


.. _uhab-design-reqs:

Design Requirements
===================

Power Management
----------------
.. list-table::
   :header-rows: 1

   * - Requirement
     - Justification
   * - Battery powered
     - There is not necessary enough sunlight for solar panels and no other
       power source is available during the mission.
   * - Permits creation of other circuit voltages
     - Most low-voltage DC circuits use only 5V and 3.3V. If a future helmet
       needs a higher voltage, it will also need a separate power supply and/or
       regulator to achieve it.
   * - Supplies power for additional stackable helmet boards
     - At least 0.5A must be available on the 5V and 3.3V rails for
       additional stacking helmets. A power board helmet is highly recommended
       to be developed and included with μHAB.

Program Execution
-----------------
.. list-table::
   :header-rows: 1

   * - Requirement
     - Justification
   * - Programmable with Arduino syntax
     - Being able to program with the Arduino IDE and abstraction layer makes
       the system more available to beginners and faster to use for those who
       are more experienced.
   * - Interfaces with selected radios, memory, and future sensors or devices
       that may be added in upcoming missions.
     - This means that the microcontroller should contain popular communication
       protocols such as I2C, SPI, UART, etc.
   * - Compatible with USB
     - Being able to directly interface to a USB for programming and computer
       serial links means that cost can be reduced since a USB controller is
       not needed.
   * - Reprogrammable bootloader
     - The availability of adding (or readding) a bootloader must be included
       via header pins set aside for this purpose.
   * - 5V Tolerant digital pins for easier integration with Arduino shields
     - Since a goal for this board is to be compatible with commercial Arduino
       shields, 5V tolerance is necessary to be able to interact with them
       without damaging the controller.
   * - Fast and powerful enough to handle multiple additional modules that may
       require significant processing power
     - Like power, additional helmets that need an increased amount of
       processing power may require their own separate processor. However,
       enough processing power with μHAB will ease that requirement for most
       applications.

Data Storage
------------
.. list-table::
   :header-rows: 1

   * - Requirement
     - Justification
   * - On-board data storage
     - Although the GPS coordinates will occasionally be transmitted via APRS,
       coverage may be spotty or lossy. Recording the GPS coordinates
       throughout the flight (as well as other data with additional helmets),
       will greatly aid in post-mission analysis. It is also important to
       include nonvolatile storage so important mission parameters such as time
       of launch can be recovered in the event of a temporary loss of power.
   * - Do not need a large amount of storage
     - Since most data being written will be in CSV format, large amounts of
       storage will not be necessary. However, some options like the microSD
       allow for easily-upgradable storage.

Global Positioning
------------------
.. list-table::
   :header-rows: 1

   * - Requirement
     - Justification
   * - Receives global positioning information from GPS/GLONASS satellites
     - Being able to receive a HAB's location is critical to recovering it
       after the flight.
   * - GPS antenna connector available (antenna not included)
     - The HAB will most likely be inside of a case covered with a mylar
       wrapping to reduce the effects of ionizing radiation. This will not
       allow RF to pass through and so the GPS receiver antenna will need to be
       broken out with an antenna.
   * - Supports an active GPS antenna
     - In the event that an active antenna is used (antenna that draws power
       for a built-in amplification stage), then the RF chain must include the
       ability to supply the necessary power to the antenna.

Communications
--------------
.. list-table::
   :header-rows: 1

   * - Requirement
     - Justification
   * - Interfaces with APRS Network
     - Since point-to-point communication will be extremely difficult to
       maintain without using specialized ground equipment and a lot of
       transmit power on the HAB, utilizing the nationally-connected `HAM radio
       APRS network <http://www.aprs.org/>`_ allows for a drastic decrease in
       the amount of power and equipment required. The caveats are that a HAM
       radio license is needed to operate on this frequency, a callsign must be
       transmitted, and the APRS packet structure must be maintained.
   * - External communications antenna connector available (antenna not
       included)
     - The radio module will be included on the PCB, but the antenna will be
       broken out just like the GPS antenna mentioned above.
   * - Programming and bootloader nets broken out to header pins
     - Having access to these allows for a future potential of in-flight
       reprogramming via radio modules that could be added on a custom helmet.

Cutdown / Flight Abort
----------------------
.. list-table::
   :header-rows: 1

   * - Requirement
     - Justification
   * - Able to cut down from balloon if necessary
     - Being able to trigger descent at any time is a requirement for obtaining
       a waiver from the FAA. Geofencing and GPS time can be utilized to
       trigger cutdown if μHAB is being operated by itself and is independent
       of a ground-station command.

Remove Before Flight Safes
--------------------------
.. list-table::
   :header-rows: 1

   * - Requirement
     - Justification
   * - Manual triggers for behaviors
     - Manual triggers such as removing a pin or jumper can enable power,
       perform any necessary calibrations, enable things like buzzers or
       lights, or arm/disarm circuits and routines. This is useful for
       preventing unwanted behavior during flight preparation or setting off
       behaviors to begin such as "arming" the payload for flight.
