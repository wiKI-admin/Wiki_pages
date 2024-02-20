**AVIONICS FULL-DUPLEX SWITCHED ETHERNET (AFDX)**

Avionics Full-Duplex Switched Ethernet (AFDX) is a data network, for
safety-critical applications that operates dedicated bandwidth while
providing deterministic quality of service (QoS). It is patented by the
international aircraft manufacturer Airbus. It is required because high
speeed commercial ethernet with provisions for guaranteed deterministic
timing and redundancy is needed for the aviation applications. The AFDX
data network is based on ethernet technology using commercial off the
shelf (COTS) components. Overall It is a network protocol tailored for
avionics applications, providing conclusive and reliable data
communication to ensure the safe and efficient operation of aircraft
systems.

The six key aspects of an AFDX data network comprises full duplex,
redundancy, determinism, high speed performance, switched and profiled
network. There are two types of devices in an AFDX architecture – Switch
and End System. Provisions have been added to secure the deterministic
behaviour. The AFDX network can define up to 64K virttual links
identified by a 16 bit identifier in the MAC (Media Access Control)
destination field of ethernet frame.

**OVERVIEW OF AFDX**

AFDX is like a high performance version of regular internet for
airplanes. It borrowed some ideas from telecom standards like
Asynchronous Transfer Mode (ATM) to make it better than regular Ethernet
and it creates a super reliable, two-way network with guaranteed data
speed and quality. The network is smart and super reliable makes sure
that the important messages get delivered quickly and without any
glitches. In AFDX, a smart switch is used to manage the data going in
and out. It also uses special cables, like twisted pairs or fiber
optics, to send and receive data separately. This makes the data super
reliable and makes sure it arrives when it's supposed to.

Additionally, it uses two networks working together, just in case one
has a problem. It's like having a backup plan to make sure everything
keeps running smoothly. AFDX also updates the different parts of the
network how to work together using something called as the OSI reference
model.

### **AFDX Specifications**

1\. Deterministic Communication: AFDX ensures forseeable and limited
data transmission, which is critical for avionics systems where timing
and reliability are predominant.

2\. Quality of Service (QoS): AFDX supports different traffic classes
with varying priorities to guarantee timely and reliable data delivery,
making it suitable for real-time and mission-critical applications,

3\. Redundancy: It includes redundancy at various levels to enhance
system error tolerance. Redundant switches and redundant network links
are often used.

4\. Ethernet-Based: It is based on Ethernet technology but adds
enhancements and restrictions to ensure deterministic behavior. It uses
a switched Ethernet topology for data transfer.

5\. Standardization: It is defined by the ARINC 664 Part 7 standard,
which defines how Commercial Off-the-Shelf networking components will be
used for future generation Aircraft Data Networks (ADN) and provides a
common framework for avionics data networks.

6\. Applications: It is widely used in aircraft for various purposes,
including flight control systems, navigation, communication, and
entertainment systems, where reliability and safety are essential.

**PARAMETERS USED**

Each visualsim AFDX switch has filtering, policing, and forwarding
functions that should be able to process at least 4096 virtual links. In
a network with multiple switches, the total number of virtual links is
nearly limitless. the user can limit the number of virtual links that
can be handled by each end system. the switch is non-blocking and the
data rates can be specified by each system integrator.

Below mentioned are some of the parameters used.

1\. Connectivity information

2\. Network Speed

3\. Distance betweeen Nodes

4\. Traffic profiles at each node- Start Time, Stop Time, Rate, Data
Size, UDP Class, VLAN

5\. Number of the Nodes.

## **VIRTUAL LINKS (VL)**

The main feature of an AFDX network are its virtual links. They are
unidirectional logic paths from the source end-system to all of the
destination end-systems. In the case of AFDX, the data transported
rather than the actual destination is identified by this virtual link
ID. The virtual link ID is a constant 32-bit field followed by a 16-bit
unsigned integer value. The switches are made to send an incoming frame
from a single end system to a preset group of end systems. Within each
virtual connection, there may be one or more linked receiving end
systems. The overall bandwidth is determined by the system integrator,
and dedicated bandwidth is assigned to each virtual link. The overall
bandwidth cannot, however, go beyond the network's top limit
(100Mbit/sec). Therefore, the provision of a complementary VL must be
necessary for bidirectional communications.

To guarantee that the network has the intended maximum traffic, each VL
is secured in specification, resulting in determinism. A VL
configuration table stored on the switch allows it to reject any
erroneous data transfer that may otherwise overwhelm other network
branches. Sub-virtual links (sub-VLs), which are intended to convey less
important data, are another possibility. A specific virtual connection
is given sub-virtual links. The virtual connections having data to
transmit are read in a round-robin fashion. Due to buffering,
sub-virtual connections do not also guarantee bandwidth or latency,
however AFDX specifies that latency is still evaluated using the traffic
regulator function.

**BAG Rates**

A key component of the AFDX protocol is the BAG, or bandwidth allocation
gap. Data may only be transmitted at this maximum rate and will always
be sent at those intervals. The BAG rate for each vertual links must be
carefully chosen to ensure that there is sufficient bandwidth for other
virtual links and that the combined speed does not exceed 100 Mbit/s.

## **SWITCHING OF VIRTUAL LINKS**

Filtering, policing, and forwarding functions on each switch should be
able to handle at least 4096 virtual links. As a result, the total
number of virtual links in a network with numerous switches is almost
infinite. The maximum number of virtual links that may be supported by
each end system is not defined, however it will depend on the BAG rates
and maximum frame sizes provided for each virtual liink in relation to
the ethernet data rate. There is a cap of four sub VLs that can be
established in a single virtual link, though. Additionally, the switch
needs to be non-blocking at the data speeds that the system integrator
specifies. and in practice, the switch shall have a switching capacity
that is the sum of all of its physical ports.

High performance COTS switches with Layer 2 routing can be used as AFDX
switches for testing purposes as a cost-saving approach because AFDX
uses the Ethernet protocol at the MAC layer. However, some features of a
real AFDX switch may be missing, such as traffic policing and redundancy
functions.
