# 4.0 Practical Tools

## Extra tutorials - Helps reading this chapter.

## 4.0.1 Banners (AKA Service Fingerprinting)
Banner refers to a text message received from the host, usually, it includes information about the open prots and services with their version numbers.
	
- Types of Banner Grabbing
	- Active Banner Grabbing
	- Passive Banner Grabbing

- Banner Grabbing Tools
	> `whatweb`, `cURL`, `wget`, `telnet`, `Nikto`, `Nmap`, `Dmitry`, `BurpSuite`, `Netcraft`, `ID Serve`, `Wappalyzer(Browser Extension)`, `HTTP Header Live(Browser Extension)`

## 4.0.2 OSI Layer Model

**Developer Concentration Section**

Layer 7 - **Application**(FTP, Telnet, HTTP, SSH, IMAP, POP3, SMTP)

	- Provides access for users.
	- Provides network services to application processes.
	- Identify communication partners.
	- Provides user authentication.

Layer 6 - **Presentation** (Data Representation/ Syntax)

	- Ensures that data is readable by receiving system.
	- Formats data to be presented to application layer.
	- Structures data.
	- Negotiates data transfer syntax for application layer (ASCII or UNICODE).
	- Provides encryption.

Layer 5 - **Session** (Interhost communication)

	- Establishment maintenance and termination of sessions between applications.
	- Maintains security / name recognition / logging.
	- Two application processes on different machines can establish a session.

	Example: 

		- NetBIOS (Network Basic Inpt/Output System)
		- PPTP (Point to point tunneling protocol)

**Network Engineer Concentration Section**

Layer 4 - **Transport** (End to End Connections) (Datagrams or Segments)
	
	- Message segmentation (Splits message to smaller units)
	- Handles transportation issues between host.
	- Ensures data transport reliability.
	- Establishes, maintains and terminates virtual circuits.
	- Flow control (Manage data transmission).
	- Session Multiplexing.
		
	
	- TCP (Transmission Control Protocol)
		- If packet missing it will be re transmitted.		
		- Uses 3-way handshake.

	- UDP (User Datagram Protocol)
		- Does not provide reliability.
		- If packet are dropped they are lost.
		- Lightweight

Layer 3 - **Network** (Data Delivery) (Packets)
	
	- Have routing capabilities. Selects best path to deliver data.
		- OSPF (Open Shortest Path First)
		- BGP (Border Gateway Protocol)
		- IS-IS (Intermediate System-to-Intermediate System).
	
Layer 2 - **Data Link** (Physical Addressing and Access to Media) (Frames)
	
	- Defines how data is formatted for transmission and how access to the network is controlled.
	- Error Detection.

Layer 1 - **Physical** (Binary Transmission)(Bits)
	
	- What state represents 0 or 1.
	- Defines electrical, mechanical, procedural and functional specifications for activating maintaining
and deactivating the physical link.
	- Focused with physical devices and physical cabling.
	- Medium,


**More Details for OSI Layer Model**

- Process of conversion from layer to layer. (Always communication happens between layer n to layer n of the other side. Eg: Layer 7 communicates with Layer 7)
- [NetworkChuck Demonstrates the process of OSI Model well](https://www.youtube.com/watch?v=3kfO61Mensg&list=PLIhvC56v63IJVXv0GJcl9vO5Z6znCVb1P&index=5) 

## 4.1 NetCat

Utility that reads and writes data across network connections, using TCP or UDP protocols.

- Client mode 
	- Check if a port is open or closed.
	- Read a banner from the service listening on a port.
	- Connect to a network service manually.
	
	> `nc -nv <ip_address> <port>` - `-n`:Skip DNS name resolution, `-v`:Add some verbosity.

- Server mode
	> `nc -lvnp <port>` - `-l`:Listen, `-v`:Verbose output, `-n`:Skip DNS name resolution, `-p`:Define listening port.

- **Applications of NetCat**
	- Blind Shell

## 4.2 SoCat

## 4.3 PowerShell

## 4.4 PowerCat

## 4.5 Wireshark (Traffic  Sniffer)

Wireshark uses Libpcap101 (on Linux) or Winpcap102 (on Windows) libraries in order to capture packets from the network.		

## 4.6 TCP Dump

