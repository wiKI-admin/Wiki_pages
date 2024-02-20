# **Wireshark  
  
Installation & Usage**

|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |

# **Table of contents**

[1. Introduction 2](#introduction)

[1.1 What is Wireshark? 2](#what-is-wireshark)

[1.2 Intended Purpose 2](#intended-purpose)

[1.3 Benefits of Wireshark 2](#benefits-of-wireshark)

[1.4 What Wireshark is NOT? 3](#what-wireshark-is-not)

[2. Installation 3](#installation)

[2.1 Installation using APT Package Manager
3](#installation-using-apt-package-manager)

[2.2 Installation from the Official Wireshark Repository
4](#installation-from-the-official-wireshark-repository)

[3. Using Wireshark 4](#using-wireshark)

[4. File handling using tcpdump & tcpreplay
5](#file-handling-using-tcpdump-tcpreplay)

[4.1 tcpdump 5](#tcpdump)

[4.2 tcpreplay 6](#tcpreplay)

**<span class="underline">Purpose:</span>**

*The document aims to provide information related to Wireshark. In
addition to that, with the help of this document you will be able to
Install and Use Wireshark on your Ubuntu device and also will be able to
reuse the logged data in PCAP file with the TCP commands like tcpdump
and tcpreplay.*

*  
*

## Introduction

### What is Wireshark?

Wireshark is a popular open-source network protocol analyzer that allows
you to capture and analyze the data traveling back and forth on your
network. It is widely used for troubleshooting network issues, analyzing
network traffic, and security testing. Wireshark supports a wide range
of protocols and provides an easy-to-use graphical interface.

Wireshark does three things,

  - <span class="underline">Packet Capture</span>: Wireshark listens to
    a network connection in real time and then grabs entire streams of
    traffic – quite possibly tens of thousands of packets at a time.

  - <span class="underline">Filtering</span>: Wireshark is capable of
    slicing and dicing all this random live data using filters. By
    applying a filter, you can obtain just the information you need to
    see.

  - <span class="underline">Visualization</span>: Wireshark, like any
    good packet sniffer, allows you to dive right into the very middle
    of a network packet. It also allows you to visualize entire
    conversations and network streams.

### Intended Purpose

Here are some reasons people use Wireshark:

  - Network administrators use it to troubleshoot network problems

  - Network security engineers use it to examine security problems

  - QA engineers use it to verify network applications

  - Developers use it to debug protocol implementations

  - People use it to learn network protocol internals

  - Wireshark can also be helpful in many other situations.

### Benefits of Wireshark

  - <span class="underline">Comprehensive Network Analysis:</span>
    Wireshark offers extensive capabilities for capturing, analyzing,
    and dissecting network traffic.  

  - <span class="underline">User-Friendly Interface:</span> Wireshark
    provides a user-friendly graphical interface that allows users to
    navigate and analyze captured packets efficiently. 

  - <span class="underline">Open Source and Cross-Platform:</span>
    Wireshark is an open-source tool available for multiple operating
    systems, including Windows, macOS, and Linux.  

  - <span class="underline">Extensibility:</span> Wireshark supports
    various protocols and file formats, and it allows the addition of
    custom dissectors and plugins.  

  - <span class="underline">Educational Value:</span> Wireshark serves
    as an educational tool for understanding network protocols, packet
    structure, and network behavior.

### 1.4 What Wireshark is NOT?

Here are few things which Wireshark does not provide,

  - > Wireshark isn’t an intrusion detection system. It will not warn
    > you when someone does strange things on your network that he/she
    > isn’t allowed to do. However, if strange things happen, Wireshark
    > might help you figure out what is really going on.

  - > Wireshark will not manipulate things on the network, it will only
    > “measure” things from it. Wireshark doesn’t send packets on the
    > network or do other active things (except domain name resolution,
    > but that can be disabled).

## Installation

### Installation using APT Package Manager

> **Update the Package List:** Open a terminal and update the package
> list to ensure you have the latest information about available
> packages.

sudo apt update

**Install Wireshark:** Use the following command to install Wireshark
and its dependencies.

sudo apt install wireshark

During the installation, you'll be prompted to choose whether to allow
non-superusers to capture packets. To do this, the installer will add
the user to the "Wireshark" group. Choose "Yes" and press Enter.

**Restart the System or Re-login:** After the installation is complete,
it's recommended to either restart your system or log out and log back
in to apply the group changes.

**Run Wireshark:** Open a terminal and run Wireshark with elevated
privileges.

sudo wireshark

### Installation from the Official Wireshark Repository

**Add the Wireshark Repository:** Open a terminal and add the Wireshark
repository

sudo add-apt-repository ppa:wireshark-dev/stable

Press Enter when prompted to confirm.

**Update the Package List:** Update the package list to include the new
repository:

sudo apt update

**Install Wireshark:** Install Wireshark using the following command:

sudo apt install wireshark

**Restart the System or Re-login:** After the installation is complete,
it's recommended to either restart your system or log out and log back
in to apply the group changes.

**Run Wireshark:** Open a terminal and run Wireshark with elevated
privileges.

sudo wireshark

Remember that capturing packets requires elevated privileges, so either
run Wireshark with **‘sudo’** or configure your system to allow non-root
users to capture packets.

**Add User to Wireshark Group:** To allow non-root users to capture
packets, you need to add your user to the **‘wireshark’** group. Replace
**\<username\>** with your actual username.

sudo usermod -aG wireshark \<username\>

## Using Wireshark

**Open Wireshark:** Open Wireshark either from the application menu or
by typing wireshark in the terminal.

wireshark

**Choose Interface:** Wireshark will ask you to choose the network
interface to capture packets. Select the appropriate interface and click
"Start."

**Capture Packets:** Wireshark will start capturing packets on the
selected interface. You'll see a real-time display of captured packets.

**Filtering Packets:** You can use display filters to focus on specific
types of traffic. For example, to filter HTTP traffic, type **‘http’**
in the display filter box.

**Stop Capture:** To stop capturing, click on the red "Stop" button

**Inspect Packets:** You can click on any packet in the list to view its
details in the bottom panel. Wireshark also provides various analysis
tools and statistics.

**Save or Export Capture:** Save your capture for later analysis or
share it with others. Use File \> Save or File \> Export to save the
capture in different formats.

**Additional Features:** Explore other features like protocol hierarchy,
follow TCP stream, and more to analyze the captured data thoroughly.

**<span class="underline">Command-Line Capture (Optional):</span>**

If you prefer capturing packets from the command line, you can use the
dumpcap tool, which comes with Wireshark:

sudo dumpcap -i \<interface\> -w \<output\_file.pcap\>

Replace **‘\<interface\>’** with your network interface (e.g.,
**‘can0’**) and **‘\<output\_file.pcap\>’** with the desired output
file.

Remember to use Wireshark responsibly and ensure you have the necessary
permissions to capture network traffic. Additionally, consider the
privacy and legal implications of capturing and analyzing network data.

## File handling using tcpdump & tcpreplay

### tcpdump

**‘tcpdump’** is a command-line packet analyzer that allows users to
display and analyze the network traffic on a computer network. It
captures packets in real-time and can also read packets from a
previously saved capture file. tcpdump uses the PCAP library to capture
and process packets. It provides a flexible and powerful way to filter
and analyze network traffic based on various criteria such as
source/destination IP address, port numbers, protocols, and more.

Some examples of using tcpdump,

  - Capture packets on specific network interface

> tcpdump -i eth0

  - Save captured packets to a file for later analysis

> tcpdump -i eth0 -w capture\_file.pcap

  - Apply a filter to capture only specific packets
    
    tcpdump -i eth0 tcp port 80

### tcpreplay

**‘tcpreplay’** is a tool used to replay captured network traffic stored
in PCAP files back onto a network. It allows you to reproduce or emulate
real network conditions by sending the captured packets onto a network
interface. This can be useful for testing and analyzing the behavior of
network devices, intrusion detection/prevention systems, and other
network-related equipment.

Here are some basic examples of using tcpreplay:

  - Replay packets from a PCAP file onto a network interface

> sudo tcpreplay -i eth0 capture\_file.pcap

  - Adjust the replay speed

> sudo tcpreplay -i eth0 -t --loop=0.5 capture\_file.pcap

  - Replay packets with a specific inter-packet gap

> sudo tcpreplay -i eth0 --gap=10000 capture\_file.pcap

In summary, tcpdump is used for capturing and analyzing network packets,
while tcpreplay is used for replaying captured packets onto a network.
These tools are valuable for network administrators, security
professionals, and developers for troubleshooting, analyzing network
behavior, and testing network equipment in controlled environments.
