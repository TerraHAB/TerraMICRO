# μHAB Architecture

!!! note
    μHAB is under active development. Visit the project's GitHub page for
    [µHAB designs and documentation](https://github.com/RIT-Space-Exploration/uHAB).

## Purpose

The purpose of μHAB is to provide a flexible, expandable, and affordable
platform that contains all of the necessary functionality for a
high-altitude balloon mission without the hassle of starting a
completely new design from scratch.

**Flexible**: μHAB contains a wealth of available I/O that is broken out
to easily accessible headers. Both 5V and 3.3V digital pins are
available for ease of future component integrations. The powerful
300MHz, 32-bit microcontroller has capabilities for CANbus, EBI/EMI,
Ethernet, I²C, IrDA, LINbus, MMC/SD/SDIO, QSPI, SPI, SSC, UART/USART,
USB, x24 16-bit ADC (with oversampling), and x2 12-bit DAC. μHAB also
features selection headers for multiple types of antennas and
remove-before-flight safes.

**Expandable**: The layout of the PCB includes the familiar pinout of
the common Arduino Mega so that commercial Arduino shields may be
utilized. Additional I/O is available separately. The microcontroller
selected offers enough processing power to handle many more additional
tasks and the available power supply allows for some limited draw for
future expansion modules called *helmets*.

**Affordable**: μHAB will contain only the components necessary for a
successful mission as outlined below. Extra functionality will be
available in the form of completely separate additional *helmets* as
needed. By reducing the functionality to a minimum, μHAB lowers the
overall costs associated for a HAB launch and allows for more expansion.

## Design Requirements

### Power Management

### Program Execution

### Data Storage

### Global Positioning

### Communications

### Cutdown / Flight Abort

### Remove Before Flight Safes
