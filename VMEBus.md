**VME (Versa Module Eurocard)**

The VME (Versa Module Eurocard) bus is a standardized computer bus
system used in embedded computing and industrial applications is based
on microprocessor technology,. It was originally developed in Europe but
has gained widespread use globally becuase of many applications. A
VMEbus may be used for traffic control systems, weapons controls
systems, robotic systems or other important hardware setups.

It is physically based on Eurocard sizes, mechanicals and connectors
(DIN 41612), but uses its own signalling system, which Eurocard does not
define. VMEBus is built in a variety of sizes to fit into a particular
rack space and has its own command and signal syntax to indicate various
states of operation. It was originally developed for the Motorola 68000
line of CPUs, but later widely used for many applications.

All in all VME bus is a standardized system that allows to easily add
different modules to a computer, making it very flexible and reliable,
especially in demanding environments like factories and military
equipment.

**OVERVIEW**

1.  Eurocard Standard: It's based on the Eurocard standard, which means
    these modules have a standard size and can fit into compatible slots
    or racks. This standardization allows for interoperability and easy
    expansion of systems.

2.  High Reliability: VME is known for its reliability and robustness,
    making it fit for use in environments where stability and endurance
    are essential, like in industrial automation and military
    applications.

3.  Multiple Bus Types: There are distinct versions of the VME bus,
    including VME64, VME64x, and VXS (VME Switched Serial). Each version
    builds upon the previous one, offering improvements in terms of data
    transfer speed and functionality.

4.  Modular and Versatile: VME is a interchangeable system, where you
    can add different cards or modules to a computer system. These
    modules can perform various functions, such as processing data or
    controlling devices.

5.  Wide Application: VME is commonly used in applications where
    real-time control, data acquisition, and processing are critical,
    such as in aerospace, telecommunications, and scientific research.

**HOW IT WORKS?**

VMEbus is an asynchronous bus. This implies that the timing of data
transmissions is not controlled by clocks. Using handshaking signals
that are interlocked, data is transferred between the different modules.
Each transfer's cycle speed is determined by the cycle's slowest
participating module. The master-slave architecture of the VMEbus is
used. Data is transferred between functional modules known as slaves and
functional modules known as masters. A multiprocessing bus is one that
can accommodate several masters. A master must first acquire the bus
through a central arbitrator before it can send data. This arbiter is a
component of the system controller module. Its job is to choose which
master gets to use the bus. Five auxiliary buses are used for overall
bus operations. The buses are called the Data Transfer Bus, the Data
Transfer Arbitration Bus, the Priority Interrupt Bus, the Utility bus
and the Serial Bus.

**VME Applications**

The VMEbus is used in a broad range of applications. In many cases, the
system designs have been defind to support specialized applications as
well. Some of the most commonly used include:

Aerospace: avionics, ﬂy-by-wire control systems, in-ﬂight video servers,
spacecraft experiment control, missile countdown sequencers, and many
others. Example, In 1998 the Mars Pathﬁnder used a VMEbus computer to
control spacecraft operation on the planet Mars.

Military: battleﬁeld command & control systems, ground and ﬂight radar
control systems, tank and gun controls, communications, and others.

Industrial Controls: factory automation, robotics, injection molding
machines, automotive body assembly and painting, sawmill controls, metal
working, steel manufacturing, and cardboard cutters.

High Energy Physics: particle accelerators, and particle detectors.

Transportation: railway controls, smart highway systems and light-rail
transit systems.

Telecom: advanced intelligent node (AIN) switch gear, cellular telephone
base stations.

Medical: CATSCAN imaging, MRI imaging and various acoustical systems.
