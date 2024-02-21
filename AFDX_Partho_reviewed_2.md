**Avionics Full Duplex Switched Ethernet (AFDX)  Guides and Standards** {#avionics-full-duplex-switched-ethernet-afdx-guides-and-standards .TOC-Heading}
======================================================================

  -------------------- ----------------
                       
                       
                       
                       
                       
                       
                       
                       
                       
                       
                       
                       
                       
  **Creation date:**   31.01.2024
  **Version 1.0:**     31.01.2023
  **Author:**          Aparna Sudheer
  -------------------- ----------------

 **Contents** {#contents .TOC-Heading}
============

[1. Scope 1](#scope)

[2. Introduction 1](#introduction)

[3. Avionics Full-Duplex Switched Ethernet (AFDX)
2](#avionics-full-duplex-switched-ethernet-afdx)

[4. AFDX Network Components 2](#afdx-network-components)

[5. AFDX Frame Structure 4](#afdx-frame-structure)

[5.1 **AFDX Ethernet Frame Structure**
5](#afdx-ethernet-frame-structure)

**Table of figures**

[1. AFDX EndSystem 4](#_Toc157595270)

[2. AFDX Virtual Links 5](#_Toc157595271)

[3. AFDX Switch 5](#_Toc157595272)

[4. Layered Architecture 6](#_Toc157595273)

[5. AFDX Ethernet Frame Structure 7](#_Toc157595274)

Scope
-----

The document aims to provide information about AFDX and its basic
structure. After reading the document, the user will be able to get
familiarize with the AFDX and have the information related to its
components and a basic idea about its architecture.

Introduction
------------

The term 'Avionics' is the combination of aviation and electronics,
which could be defined as electronics of aircrafts, artificial
satellites and spacecrafts. Avionic communication has been important
ever since electronic systems and controls were first used on aircraft.
In the 1990s, rack-mounted replaceable processors marked the beginning
of Integrated Modular Avionics (IMA), which later expanded to include
shared communications, computation, and I/O networks. Today's
fly-by-wire airplanes combine IMA with dependable networks and time- and
space-partitioned software to handle a multitude of tasks, cutting down
on the amount of control buses and computers.

Aerospace networks have more demanding goals than other commercial or
industrial networks. Safety in aerospace is of paramount importance, so
high levels of redundancy, security, environmental resiliency, and
error/failure isolation is critical for aerospace networks. Some of the
main aerospace networks are SpaceWire, MIL-STD-1553, AFDX, and TTE.
Space Wire is based on IEEE 1355 which provides low error, low cost and
deterministic communications using reliable electronics and is used by
the European Space Agency, NASA and JAXA. MIL-STD-1553 is a military
standard published by the United States Department of Defense. It
features redundant balanced line physical layers, time division
multiplexing and can handle up to 31 remote terminals. Limitations due
to topology or protocol in other networks forced the system integrators
to develop a new technology. AFDX is the leading-edge avionics network
technology today that is chosen by the greatest aircraft companies like
Airbus and Boeing. The first application of AFDX was started with A380
of Airbus and continued with A400M of Airbus Military and Boeing 787.

Avionics Full-Duplex Switched Ethernet (AFDX)
---------------------------------------------

AFDX is a data network, mainly used for in-space and air applications
that utilizes dedicated bandwidth while providing deterministic quality
of Service. The AFDX data network is based on Ethernet technology using
commercial off-the-shelf (COTS) components. The AFDX data network is a
specific implementation of ARINC Specification 664 Part 7, a profiled
version of an IEEE 802.3 network per parts 1 & 2, which defines how
commercial off-the-shelf networking components will be used for future
generation Aircraft Data Networks (ADN). It uses cascaded star topology
to reduce wire runs and weight and provides dual link redundancy. AFDX
uses parts of the MIL-STD-1553 terminology and network layout. In order
to fix the shortcomings of IEEE 802.3, AFDX adopted concepts such as
token bucket and Asynchronous Transfer Mode (ATM). Token bucket is an
algorithm used in packet-switched and telecommunication networks. ATM is
a telecommunications standard defined for digital transmission of
multiple types of traffic. Possibility of transmission collisions are
eliminated by full duplex Ethernet and uses twisted pair or fiber optic
cables for transmitting and receiving the data. AFDX extends standard
Ethernet to provide high data integrity and deterministic timing.

AFDX Network Components
-----------------------

       ** 4.1 AFDX End System**

AFDX End System (ES) is the part of an avionics system or an avionics
subsystem that connects a logical unit to a physical AFDX network. An
End System implements protocol specific functions and carries out
messaging features. Each Avionics Subsystem the End System interface to
guarantee a secure and reliable data interchange with other Avionics
Subsystems. This interface exports an application program interface
(API) to the various Avionics Subsystems, enabling them to communicate
with each other through a simple message transfer interface.

> ![](media/image4.png){width="3.5729166666666665in"
> height="1.7482852143482064in"}

**4.2 AFDX Virtual Links**

The central feature of an AFDX network are its virtual links (VL). VLs
are logical implementations of the unidirectional point-to-point
physical connections of ARINC 429. A transmitting Virtual Link may be
connected to an unlimited number of receiving Virtual Links, but a
receiving Virtual Link shall be connected to only and only one
transmitting Virtual Link. Each interface of an End System is connected
to the Switch which connects the End System to the AFDX network. This
connection is established via a single physical transmission line.
Definition of VLs enables establishing many separate logical connections
between End Systems on the same physical medium. An AFDX End System is
required to support up to 128 VLs. For less critical data communication
needs, AFDX allows Sub Virtual Links. These are data queues that share a
single VL and cannot distribute its messages across different VLs.

> ![](media/image5.png){width="3.3854166666666665in"
> height="2.4535159667541557in"}

**4.3 AFDX Switch**

Major Functions of an AFDX Switch are filtering, policing and forwards
packets towards their destination End Systems according to network
configuration. All incoming frames enter the filtering and policing
Functional block that drops invalid frames and switching functional
block deliver the valid frames to correct destinations. Information
about the frames is stored in the configuration tables. Switch is
configured with "static" configuration tables according to the network
architect's definitions. Monitoring Function is used to monitor and log
all switch operations and service health and network status data to the
subsystems. AFDX Switch plays the most important role for the shaped
traffic feature of the AFDX network.  

> ![](media/image6.png){width="4.260416666666667in"
> height="2.105909886264217in"}

AFDX Frame Structure
--------------------

OSI (Open System Interconnection) Reference Model is composed of
following seven layers:

-   Physical Layer,

-   Data Link Layer

-   Network Layer

-   Transport Layer

-   Session Layer

-   Presentation Layer

-   Application Layer

AFDX is also an open standard, inspired with these layered models and
common protocols.

![](media/image7.JPG){width="5.3125in" height="3.5571456692913386in"}

### ![](media/image8.png){width="5.905538057742782in" height="1.6871106736657917in"}5.1 **AFDX Ethernet Frame Structure**
