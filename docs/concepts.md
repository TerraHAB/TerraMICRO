# Mission Concepts

TerraMICRO was conceived as a payload-agnostic high altitude balloon
architecture. In addition, TerraMICRO should host one or more technical
or scientific experiments. These experiments need not be related to
uHAB---they serve as a means to validate the design and architecture
while stressing the system in a real-world use case.

## List of Experiment Ideas

### Stable Imaging Platform / Bus Attitude Control

Active gimbals make for a (power hungry) off-the-shelf solution for
image stabilization. For a challenge one could build a gimballed camera
mount from scratch.[^1]

A more novel idea would be to control bus attitude. A senior design team
from 2017 attempted to do attitude control with a reaction wheel, but I
don't think they had a way to dump momentum. A simpler (and more novel)
approach would be to use RC aircraft engines or drone motors to actively
counteract wind forces. A simpler objective could be using drone
propellers for anti-spin control or active ballast weights for
anti-rocking control.

**Pairs with:** [On-board Image Processing]()

### Altitude Control

Actively change the ascent or descent rate. For a simpler demonstration,
only control the ascent rate. For a challenge, maintain an altitude set
point. For a greater challenge, extend the flight duration by
controlling altitude.[^2]

**Pairs with:** [Intra-balloon Environment Sensors]()

### Intra-balloon Environment Sensors

Develop a sensor platform to measure environmental conditions
(temperature, pressure, humidity) within the balloon from ambient,
through filling, and finally through the burst event. Send the data to
the main payload storage over a wired or wireless link.

As a stretch goal, instrument the bus with environmental sensors.
Compare balloon internal conditions to ambient ones add correlate it
with altitude rate of change or burst events.

**Pairs with:** [Altitude Control](), [Characterize Atmospheric
Composition](), [Model and Test Latex Balloon Burst Conditions]()

### On-board Image Processing

Perform image processing (of any level) on images or video on the
payload electronics in flight.[^3] For an extra challenge, apply any of
the following constraints:

- Payload electronics do not exceed \$30.
- Image processing algorithms have a practical or scientific usebeyond a simple demonstrator.
- Image processing takes place on an FPGA. Bonus if it occurs in realtime.
- Image processing includes data fusion with additional sensors orcamera sources.

**Pairs with:** [Stable Imaging Platform / Bus Attitude Control]()

### Real-time Data Transfer

Receive real time telemetry and payload data in flight. For a greater
challenge, send commands from a ground station during the flight. For a
simple demonstration, send limited health and status telemetry. As a
stretch, send rich data (like photos or live video) to a ground station
in flight.

**Pairs with:** [Intra-balloon Environment Sensors](), [Characterize
Atmospheric Composition](), [Characterize Radiation Environment](),
[Altitude Control](), [Stable Imaging Platform / Bus Attitude Control]()

### Characterize Atmospheric Composition

Measure atmospheric composition along the balloon's ascent. Characterize
how composition changes with altitude. For a greater challenge, use
multiple flights to see how composition changes with altitude from
different geographic locations, time of day, time of year, or different
weather conditions.

**Pairs with:** [Altitude Control](), [Intra-balloon Environment Sensors]()

### Characterize Radiation Environment

Measure radiation intensity along the balloon's ascent. Characterize how
intensity changes with altitude. For a greater challenge, use multiple
flights to see how intensity changes with altitude from different
geographic locations, time of day, time of year, or different weather
conditions.

**Pairs with:** [Altitude Control](), [Intra-balloon Environment Sensors]()

### Model and Test Latex Balloon Burst Conditions

Prior to launch, predict the conditions that lead to the balloon's burst
event. Instrument the payload and balloon to test the model in flight.
For an extra challenge, apply any of the following constraints:

- Model the burst event only using parameters that can be measured in
  flight.
- Test the model on the ground with simulated atmospheric conditions
  and a sub- or full-scale balloon.
- Record high-speed video of the balloon bursting in flight.

**Pairs with:** [Intra-balloon Environment Sensors]()

### Controlled Descent

After balloon cutdown, control the descent of the payload. For a simpler
challenge, use a reefed parachute. For a greater challenge, steer the
descent path using a parafoil or aero control surfaces.

**Pairs with:**

### Vegetation Density Experiment

Measure vegetation density using NDVI with cameras in flight. For a
greater challenge, do the image processing on-board.[^4]

**Pairs with:** [Stable Imaging Platform / Bus Attitude Control](),
[On-board Image Processing]()

### F' Flight Software Ecosystem

F' (F Prime) is a component-driven framework that enables rapid
development and deployment of spaceflight and other embedded software
applications.[^5] F' is part of NASA Jet Propultion Lab's technology
ecosystem, open source, and also has demos that are meant to be run on a
Raspberry Pi.

F' can be used to create common HAB flight software leveraging existing
components. The team will create additional components to meet the needs
of specific HABs, with the ability to open source for use by other HAB
teams.

- Run HAB FSW with F' using a one off greedy customization, not going
  out of the way for code reuse.
- Design HAB FSW with F' to be common and for use by other HAB teams
  as a base.
- Design hardware payloads with accompanying F' components to be
  common for use by teams that want a plug and play HAB payload.

**Pairs with:**

### Long Distance Communications

Send or receive data to the HAB in flight while it is beyond visual
range. For a greater challenge, send or receive data while the HAB is
beyond the geographical horizon of the ground station.

**Pairs with:** [Real-time Data Transfer]()

### Multispectral / Hyperspectral Instrument

Image the Earth, sky, or atmospheric limb with a camera sensitive to two
or more spectral bands. Optionally apply any of the following
constraints:

- Use components which cost no more than \$50.[^6]
- Calibrate the instrument on the ground (optionally in flight-like
  conditions)

**Pairs with:** [Stable Imaging Platform / Bus Attitude Control](),
[On-board Image Processing](), [Vegetation Density Experiment]()

### Star Tracker

Build an instrument that measures position of the payload bus based on
optical measurements of the sky.[^7][^8] Optionally apply any of the
following constraints:

- Use components which cost no more than \$50.
- Calibrate the instrument on the ground (optionally in flight-like
  conditions)
- Implement a custom algorithm to derive orientation from images of
  the sky.

**Pairs with:** [Stable Imaging Platform / Bus Attitude Control](),
[On-board Image Processing]()

### Synthetic Image Quality Enhancement

Use computer vision techniques to improve the effective resolution of
images by either of the following methods:

1. Stitch multiple image frames into a larger composite image of an
   area wider than the camera's field of view.[^9]
2. Use multi-frame super-resolution algorithms to create high
   resolution image products from low resolution images captured in
   flight.[^10][^11]

**Pairs with**: [Stable Imaging Platform / Bus Attitude Control](),
[On-board Image Processing]()

------------------------------------------------------------------------

## Reference Missions

This section outlines reference payloads and mission profiles for
TerraMICRO which satisfy the main mission objective of demonstrating the
uHAB avionics architecture by supporting a combination of technical or
scientific experiments.

### Vegetation Density Mapper

*The spiritual successor to* [Where U At
Plants?](https://github.com/RIT-Space-Exploration/hab-cv) *and Phil's
vision for* [HAB
CV](https://github.com/RIT-Space-Exploration/SPEX-Project-Definition-Documents/blob/master/HAB-CV/hab-cv.pdf).

Mount at least two ground-facing cameras to the HAB payload. Collect
photos or videos of the ground in the Red and Near-Infrared spectral
bands as needed to compute
[NDVI](https://www.earthdatascience.org/courses/earth-analytics/multispectral-remote-sensing-data/vegetation-indices-NDVI-in-R/)
on the ground below. Calibrate spectral response and lens distortion of
all payload cameras on the ground before flight.

**Experiments (Level I):**

- [Vegetation Density Experiment](): Record flight data (GPS
  coordinates, altitude, orientation) in sync with image captures. Use
  flight data, camera field of view, and image data to project image
  data onto a map. Flight data and imagery is stored to local memory.
  All data processing and analysis takes place after flight data is
  recovered.

**Experiments (Level II):**

- [On-board Image Processing](): Perform data processing (linking
  flight data to imagery) and analysis (compute NDVI) on-board during
  the flight.
- [Real-time Data Transfer](): Downlink all or part of the data to a
  ground station while in flight.

**Experiments (Level III):**

- [Stable Imaging Platform / Bus Attitude Control](): Use active
  control systems and actuators (reaction mass, ballast, electric
  motors, thrust) to stabilize the platform where the payload cameras
  are mounted. In addition to control actuators, pointing knowledge is
  necessary to feed the control system.

### Flight Conditions Characterizer

*A knowledge-gathering mission to inform flight characteristics and
environments on future HAB flights.*

Instrument the HAB bus to measure ambient conditions, internal
conditions within the bus structure, and internal conditions within the
balloon over a long-duration flight to gain detailed insights into the
conditions subjected to the hardware. Calibrate all sensors on the
ground in known conditions, ideally with an environmental test chamber,
prior to the flight.

**Experiments (Level I):**

- [Characterize Atmospheric Composition](): Measure temperature,
  humidity, pressure, and composition of the air over the course of
  the flight.
- [Characterize Radiation Environment](): Measure ionizing radiation
  flux (using a geiger counter) over the course of the flight.

**Experiments (Level II):**

- [Intra-balloon Environment Sensors](): Measure temperature,
  humidity, pressure and density of helium within the balloon. Also
  measure detailed thermal gradients throughout the payload bus and
  components.
- [Real-time Data Transfer](): Downlink all or part of the data to a
  ground station while in flight.
- [Model and Test Latex Balloon Burst Conditions](): Model and test
  (on the ground) the conditions that lead to the balloon's burst
  event. Instrument the balloon and payload to validate this model and
  characterize the burst event in detail.

**Experiments (Level III):**

- [Altitude Control](): Maintain flight at certain altitude(s) to gain
  more data about the conditions at that height in order to smooth out
  outliers and variations. Optionally extend mission flight time to
  gain more data.

### Flying Robot

*A knowledge-building mission that develops key building blocks toward
satellite-like operations tasks such as command and control, data links,
and ACS systems (like detumbling).*

Send commands from a ground station that are executed by the HAB in
flight. The HAB reacts to both command instructions and stimuli from its
environment.

**Experiments (Level I):**

- [Real-time Data Transfer](): Downlink all or part of the data to a
  ground station while in flight. Execute commands sent from a ground
  station and report acknowledgement of a received command to the
  ground.

**Experiments (Level II):**

- [Controlled Descent](): Automatically detect a free-fall state and
  use active controls and actuators (parafoil, control surfaces) to
  change the speed and direction of descent. Descent should be
  controlled in a way that makes recovery of the payload easier.

**Experiments (Level III):**

- [Altitude Control](): Maintain a set altitude in flight and change
  the altitude set point in response to a command from the ground
  station.
- [Stable Imaging Platform / Bus Attitude Control](): Maintain a set
  attitude (of the imaging platform) and change the target attitude in
  response to a command from the ground station.

[^1]: Haumpton, Shane. 2018. [How to create a DIY gimbal
    stabilizer](https://www.diyphotography.net/how-to-create-a-diy-gimbal-stabilizer/).
    DIY Photography.

[^2]: Sushko, Audrey, *et. al.* 2017. [Low Cost, High Endurance,
    Altitude-Controlled Latex Balloon for Near-Space Research
    (ValBal)](http://asl.stanford.edu/wp-content/papercite-data/pdf/Suskho.Tedjarati.ea.AERO2017.pdf).
    Standford Space Initiative.

[^3]: Linden, Philip, *et. al.* 2018. [On-Board Image Processing and
    Computer Vision Techniques on Low-Cost Consumer Electronics for
    Vegetation Density Mapping and Other
    Experiments](https://github.com/RIT-Space-Exploration/hab-cv/blob/master/reports/Project%20Definition%20Document/hab-cv.pdf).
    RIT Space Exploration.

[^4]: Linden, Philip. 2018. [Where U At Plants? (WUAP): Capturing and
    Masking Images from Raspberry Pi 3 + Pi
    Camera](https://github.com/RIT-Space-Exploration/hab-cv). RIT Space
    Exploration.

[^5]: NASA Jet Propulsion Lab. 2020. [F´: A Flight-Proven,
    Multi-Platform, Open-Source Flight Software
    Framework](https://github.com/nasa/fprime). GitHub.

[^6]: Sigernes, Fred, *et. al.*. 2018. [Do it yourself hyperspectral
    imager for handheld to airborne
    operations](https://www.osapublishing.org/DirectPDFAccess/898DF890-994C-43DA-FBF0E930CF791000_382214/oe-26-5-6021.pdf).
    Optics Express.

[^7]: McBryde, Christopher Ryan. 2012. [A star tracker design for
    CubeSats](https://repositories.lib.utexas.edu/handle/2152/ETD-UT-2012-05-4608).
    University of Texas at Austin.

[^8]: Smith, Casey Grant. 2017. [Development and implementation of star
    tracker based attitude
    determination](https://scholarsmine.mst.edu/masters_theses/7724/?utm_source=scholarsmine.mst.edu%2Fmasters_theses%2F7724&utm_medium=PDF&utm_campaign=PDFCoverPages).
    Missouri University of Science and Technology.

[^9]: Szeliski, Richard. 2006. [Image Alignment and Stitching: A
    Tutorial](http://www.cs.toronto.edu/~kyros/courses/2530/papers/Lecture-14/Szeliski2006.pdf).
    Foundations and Trends in Computer Graphics and Vision.

[^10]: Nelson, Kyle, *et. al.* 2012. [Performance Evaluation of
    Multi-Frame Super-Resolution
    Algorithms](https://ieeexplore.ieee.org/abstract/document/6411669).
    IEEE.

[^11]: Farsiu, Sina, *et. al*. 2004. [Fast and robust multiframe super
    resolution](https://ieeexplore.ieee.org/abstract/document/1331445).
    IEEE.
