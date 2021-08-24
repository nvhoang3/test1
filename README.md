# Future Internet Lab Training 20211 <!-- omit in toc -->

- [Week 1](#week-1)
  - [1. Intro to Computer Network](#1-intro-to-computer-network)
  - [2. Conceptual Models of Computer Network](#2-conceptual-models-of-computer-network)
    - [2.1. OSI Model](#21-osi-model)
    - [2.2. TCP/IP Model](#22-tcpip-model)
  - [3. Data Encapsulation and De-encapsulation](#3-data-encapsulation-and-de-encapsulation)
    - [3.1. Data Encapsulation Process](#31-data-encapsulation-process)
    - [3.2. Data De-encapsulation Process](#32-data-de-encapsulation-process)


# Week 1

## 1. Intro to Computer Network

**Computer Network** is a _set of computers_ sharing resources located on or provided by _network nodes_.
The computers use common communication protocols over digital interconnections to communicate with each other.
The nodes of a computer network may include personal computers, servers, networking hardware, or other specialised or general-purpose hosts which are identified by hostnames and network addresses.
While hostnames serve as memorable labels for the nodes, network addresses serve for locating and identifying the nodes by communication protocols such as the Internet Protocol (IP).
A communication protocol is a system of rules that allows two or more entities of a communications system to transmit information via any kind of variation of a physical quantity.
The protocol defines the rules, syntax, semantics and synchronization of communication and possible error recovery methods.
Protocols may be implemented by hardware, software, or a combination of both.

Various communication services and applications are provided by the use of computer network, such as video conferencing, email, online chat, www, digital media as well as resources/data sharing, etc.

Different types of networks can be classified on basis of geographic scale.
Listed are some of computer network categories usually used:

- **Personal Area Network (PAN)** is the smallest and the most basic type of network. A PAN is usually made up of a wireless modem, one or several computers, phones, tablets, etc., and ***resolves around one person in one building***. This type of network is typically found in small offices or residences, managed by one person or organization from a single device.
- **Local Area Network (LAN)** is one of the most common and simple type of network. LANs connects groups of computers and devices together across ***short distances***, for example within a building or a group of two, three buildings in close proximity, in order to share information and resources. Enterprises typically manage and maintain LANs.
- **Metropolitan Area Network (MAN)** is a type of network which is larger than LAN but smaller than WAN, incorporating elements from both types of networks. MANs span an ***entire geographic area*** (typically a town or city). Ownership and maintenance is handled by either a singal person or company.
- **Wide Area Network (WAN)** connects computers together ***across longer physical distances***, allowing computers and devices to be ***remotely interconnected over one large network***. The Internet is the most basic example of WAN, connecting all computers together around the globe. Due to WAN's vast reach, it is maintained by multiple administrators or the public over one large network.

## 2. Conceptual Models of Computer Network

### 2.1. OSI Model

**Open Systems Interconnection (OSI) model** is a conceptual, reference model used to describe the functions of a networking system.
The OSI model characterizes computing functions into a universal set of rules and requirements in order to support interoperability between different products and software.
In the OSI reference model, the communications between a computing system are split into seven different abstraction layers: Physical, Data Link, Network, Transport, Session, Presentation, and Application.

<center><img src=./figures/osi_model.png width=500></center>

Below are descriptions of 7 layers in OSI model:

**1. Physical Layer**:

The lowest layer of the OSI Model is concerned with electrically or optically transmitting raw unstructured data bits across the network from the physical layer of the sending device to the physical layer of the receiving device.
It can include specifications such as voltages, pin layout, cabling, and radio frequencies.
At the physical layer, one might find “physical” resources such as network hubs, cabling, repeaters, network adapters or modems.

**2. Data Link Layer**

At the data link layer, directly connected nodes are used to perform node-to-node data transfer where data is packaged into frames.
The data link layer also corrects errors that may have occurred at the physical layer.

The data link layer encompasses two sub-layers of its own.
The first, media access control (MAC), provides flow control and multiplexing for device transmissions over a network.
The second, the logical link control (LLC), provides flow and error control over the physical medium as well as identifies line protocols.

**3. Network Layer**

The network layer is responsible for receiving frames from the data link layer, and delivering them to their intended destinations among based on the addresses contained inside the frame.
The network layer finds the destination by using logical addresses, such as IP (internet protocol).
At this layer, routers are a crucial component used to quite literally route information where it needs to go between networks.

**4. Transport Layer**

The transport layer manages the delivery and error checking of data packets.
It regulates the size, sequencing, and ultimately the transfer of data between systems and hosts.
One of the most common examples of the transport layer is TCP or the Transmission Control Protocol.

**5. Session Layer**

The session layer controls the conversations between different computers.
A session or connection between machines is set up, managed, and termined at layer 5.
Session layer services also include authentication and reconnections.

**6. Presentation Layer**

The presentation layer formats or translates data for the application layer based on the syntax or semantics that the application accepts.
Because of this, it at times also called the syntax layer.
This layer can also handle the encryption and decryption required by the application layer.

**7. Application Layer**

At this layer, both the end user and the application layer interact directly with the software application.
This layer sees network services provided to end-user applications such as a web browser or Office 365.
The application layer identifies communication partners, resource availability, and synchronizes communication.

### 2.2. TCP/IP Model

Transmission Control Protocol/Internet Protocol was designed and developed by Department of Defense (DoD) in 1960s and is based on standard protocols.
The TCP/IP model is a concise version of the OSI model.
Unlike 7 layers of OSI model, TCP/IP model consists of 4 layers: Network Access, Internet, Transport, Application.

<center><img src=./figures/TCPvsOSI.jpg width=450></center>
<br>

**1. Network Access Layer**

This layer corresponds to the combination of Data Link Layer and Physical Layer of the OSI model.
It looks out for hardware addressing and the protocols present in this layer allows for the physical transmission of data.

**2. Internet Layer**

This layer parallels the functions of OSI’s Network layer. It defines the protocols which are responsible for logical transmission of data over the entire network. The main protocols residing at this layer are :

- IP – Internet Protocol. It is responsible for delivering packets from the source host to the destination host by looking at the IP addresses in the packet headers. IP has 2 versions: IPv4 and IPv6. IPv4 is the one that most of the websites are using currently. But IPv6 is growing as the number of IPv4 addresses are limited in number when compared to the number of users.
- ICMP – Internet Control Message Protocol. It is encapsulated within IP datagrams and is responsible for providing hosts with information about network problems.
- ARP – Address Resolution Protocol. ARP conceptually exists between the data link and Internet layers. Its job is to find the hardware address of a host from a known IP address. ARP has several types: Reverse ARP, Proxy ARP, Gratuitous ARP and Inverse ARP.

**3. Transport Layer**

This layer is analogous to the transport layer of the OSI model.
It is responsible for end-to-end communication and error-free delivery of data.
It shields the upper-layer applications from the complexities of data.
The two main protocols present in this layer are :

- Transmission Control Protocol (TCP) – It is known to provide reliable and error-free communication between end systems.
It performs sequencing and segmentation of data.
It also has acknowledgment feature and controls the flow of the data through flow control mechanism.
It is a very effective protocol but has a lot of overhead due to such features.
Increased overhead leads to increased cost.
- User Datagram Protocol (UDP) – On the other hand does not provide any such features.
It is the go-to protocol if your application does not require reliable transport as it is very cost-effective.
Unlike TCP, which is connection-oriented protocol, UDP is connectionless.

**4. Application Layer**

This layer performs the functions of top three layers of the OSI model: Application, Presentation and Session Layer.
It is responsible for node-to-node communication and controls user-interface specifications.
Some of the protocols present in this layer are: HTTP, HTTPS, FTP, TFTP, Telnet, SSH, SMTP, SNMP, NTP, DNS, DHCP, NFS, X Window, LPD.

- HTTP and HTTPS – Hypertext transfer protocol.
It is used by the World Wide Web to manage communications between web browsers and servers. HTTPS stands for HTTP-Secure.
It is a combination of HTTP with SSL(Secure Socket Layer).
It is efficient in cases where the browser need to fill out forms, sign in, authenticate and carry out bank transactions.
- SSH – Secure Shell.
It is a terminal emulations software similar to Telnet.
The reason SSH is more preferred is because of its ability to maintain the encrypted connection.
It sets up a secure session over a TCP/IP connection.
- NTP – Network Time Protocol.
It is used to synchronize the clocks on our computer to one standard time source.
It is very useful in situations like bank transactions.

## 3. Data Encapsulation and De-encapsulation

**Data Encapsulation** is the process in which some extra information is added to the data item to add some features to it.
Data encapsulation adds the protocol information to the data so that data transmission can take place in a proper way. This information can either be added in the header or the trailer (footer) of the data.
The data is encapsulated on the sender’s side, starting from the application layer to the physical layer.
Each layer takes the encapsulated data from the previous layer and adds some more information to encapsulate it and some more functionalities with the data.
These functionalities may include proper data sequencing, error detection and control, flow control, congestion control, routing information, etc.

**Data De-encapsulation** is the reverse process of data encapsulation.
The encapsulated information is removed from the received data to obtain the original data.
This process takes place at the receiver’s end.
The data is de-encapsulated at the same layer at the receiver’s end to the encapsulated layer at the sender’s end.
The added header and trailer information are removed from the data in this process.

<center><img src=./figures/encapsulation.png width=400></center>

<br>

Different terms to represent encapsulated data used by layers in OSI model and TCP/IP model are listed as follows:

|Term|OSI layer|TCP/IP layer|
|---|---|---|
|Data|Application|Application|
|Data|Presentation|Application|
|Data|Session|Application|
|Segment|Transport|Transport|
|Packet|Network|Network|
|Frame|Data Link|Data Link|
|Bits|Physical|Physical|

### 3.1. Data Encapsulation Process

The encapsulation process of data happens at sender's side following below steps:

- **Step 1**: The Application, Presentation, and Session layer in the OSI model, or the Application layer in the TCP/IP model takes the user data in the form of data streams, encapsulates it and forwards the data to the Transport layer. It does not necessarily add any header or footer to the data. But it is application-specific and can add the header if needed.

- **Step 2**: The Transport layer (in the OSI or TCP/IP model) takes the data stream from the upper layers, and divide it into multiple pieces. The Transport layer encapsulates the data by adding the appropriate header to each piece. These data pieces are now called as data segments. The header contains the sequencing information so that the data segments can be reassembled at the receiver’s end.

- **Step 3**: The Network layer (in the OSI model) or the Internet layer (in the TCP/IP model) takes the data segments from the Transport layer and encapsulate it by adding an additional header to the data segment. This data header contains all the routing information for the proper delivery of the data. Here, the encapsulated data is termed as a data packet or datagram.

- **Step 4**: The Data-Link layer (in the OSI or TCP/IP model) takes the data packet or datagram from the Network layer and encapsulate it by adding an additional header and trailer (footer) to the data packet or datagram. The header contains all the switching information for the proper delivery of the data to the appropriate hardware components, and the trailer contains all the information related to error detection and control. Here, the encapsulated data is termed as a data frame.

- **Step 5**: The Physical layer (in the OSI or TCP/IP model) takes the data frames from the Data-Link layer and encapsulate it by converting it to appropriate data signals or bits (corresponding to the physical medium).

<br>
<img src=./figures/encapsulation_process.png>
<br>

### 3.2. Data De-encapsulation Process

The de-encapsulation process of data happens at receiver's side (reverse of encapsulation process discussed above) following these steps:

- **Step 1**: The Physical layer (in the OSI or TCP/IP model) takes the encapsulated data signals or bits from the sender, and de-encapsulate it in the form of a data frame to be forwarded to the upper layer, i.e., the Data-Link layer.

- **Step 2**: The Data-Link layer (in the OSI or TCP/IP model) takes the data frames from the Physical layer. It de-encapsulates the data frames and checks the frame header whether the data frame is switched to the correct hardware or not. If the frame is switched to the incorrect destination, it is discarded, else it checks the trailer information. If there is any error in the data, data retransmission is requested, else it is de-encapsulated and the data packet is forwarded to the upper layer.

- **Step 3**: The Network layer (in the OSI model) or the Internet layer (in the TCP/IP model) takes the data packet or datagram from the Data-Link layer. It de-encapsulates the data packets and checks the packet header whether the packet is routed to the correct destination or not. If the packet is routed to the incorrect destination, the packet is discarded, else it is de-encapsulated and the data segment is forwarded to the upper layer.

- **Step 4**: The Transport layer (in the OSI or TCP/IP model) takes the data segments from the network layer and de-encapsulate it. It first checks the segment header and then reassembles the data segments to form data streams, and these data streams are then forwarded to the upper layers.

- **Step 5**: The Application, Presentation, and Session layer in the OSI model, or the Application layer in the TCP/IP model takes encapsulated data from the Transport layer, de-encapsulate it, and the application-specific data is forwarded to the applications.
