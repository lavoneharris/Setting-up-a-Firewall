<h1>Setting up a Firewall Lab</h1>


<h2>Description</h2>
This Firewall Lab consist of new VM on Oracle Virtual Box,that will act as firewall. We will both create a firewall and set up rules for the firewall that will block a specific IP address. 


<br />


<h2>What is a Firewall:</h2>
As stated by the company Cisco, a firewall is a network security device that monitors incoming and outgoing network traffic and decides whether to allow or block specific traffic based on a defined set of security rules.


A firewall can be hardware, software, software-as-a service (SaaS), public cloud, or private cloud (virtual).

<br />


<h2>Types of Firewalls:</h2>
1. Packet Filtering Firewall
Packet filtering firewalls operate inline at junction points where devices such as routers and switches do their work. However, these firewalls don't route packets; rather they compare each packet received to a set of established criteria, such as the allowed IP addresses, packet type, port number and other aspects of the packet protocol headers. Packets that are flagged as troublesome are, generally speaking, unceremoniously dropped -- that is, they are not forwarded and, thus, cease to exist.
Packet Filtering Firewall Advantages:
1. A single device can filter traffic for the entire network
2. Extremely fast and efficient in scanning traffic
3. Inexpensive
4. Minimal effect on other resources, network performance and end-user experience
Packet Filtering Firewall Disadvantages:
1. Because traffic filtering is based entirely on IP address or port information, packet filtering lacks broader context that informs other types of firewalls
2. Doesn't check the payload and can be easily spoofed
3. Not an ideal option for every network
4. Access control lists can be difficult to set up and manage

2. Circuit-Level Gateway
Using another relatively quick way to identify malicious content, circuit-level gateways monitor TCP handshakes and other network protocol session initiation messages across the network as they are established between the local and remote hosts to determine whether the session being initiated is legitimate -- whether the remote system is considered trusted. They don't inspect the packets themselves, however.
Circuit-Level Gateway Advantages:
1. Only processes requested transactions; all other traffic is rejected
2. Easy to set up and manage
3. Low cost and minimal impact on end-user experience
Circuit-Level Gateway Disadvantages:
1. If they aren't used in conjunction with other security technology, circuit-level gateways offer no protection against data leakage from devices within the firewall
2. No application layer monitoring
3. Requires ongoing updates to keep rules current

3. Application-Level Gateway (aka Proxy Firewall)
his kind of device -- technically a proxy and sometimes referred to as a proxy firewall -- functions as the only entry point to and exit point from the network. Application-level gateways filter packets not only according to the service for which they are intended -- as specified by the destination port  but also by other characteristics, such as the HTTP request string.While gateways that filter at the application layer provide considerable data security, they can dramatically affect network performance and can be challenging to manage.
Application-Level Gateway Advantages:
1. Examines all communications between outside sources and devices behind the firewall, checking not just address, port and TCP header information, but the content itself before it lets any traffic pass through the proxy
2. Provides fine-grained security controls that can, for example, allow access to a website but restrict which pages on that site the user can open
3. Protects user anonymity
Application-Level Gateway Disadvantages:
1. Can inhibit network performance
2. Costlier than some other firewall options
3. Requires a high degree of effort to derive the maximum benefit from the gateway
4. Doesn't work with all network protocols

4. Stateful Inspection Firewall
State-aware devices not only examine each packet, but also keep track of whether or not that packet is part of an established TCP or other network session. This offers more security than either packet filtering or circuit monitoring alone but exacts a greater toll on network performance. A further variant of stateful inspection is the multilayer inspection firewall, which considers the flow of transactions in process across multiple protocol layers of the seven-layer Open Systems Interconnection (OSI) model.
Stateful inspection Firewall Advantages:
1. Monitors the entire session for the state of the connection, while also checking IP addresses and payloads for more thorough security
2. Offers a high degree of control over what content is let in or out of the network
3. Does not need to open numerous ports to allow traffic in or out
4. Delivers substantive logging capabilities
Stateful inspection Firewall Disadvantages:
1. Resource-intensive and interferes with the speed of network communications
2. More expensive than other firewall options
3. Doesn't provide authentication capabilities to validate traffic sources aren't spoofed

5. Next-Generation Firewall (NGFW)
A typical NGFW combines packet inspection with stateful inspection and also includes some variety of deep packet inspection (DPI), as well as other network security systems, such as an IDS/IPS, malware filtering and antivirus.While packet inspection in traditional firewalls looks exclusively at the protocol header of the packet, DPI looks at the actual data the packet is carrying. A DPI firewall tracks the progress of a web browsing session and can notice whether a packet payload, when assembled with other packets in an HTTP server reply, constitutes a legitimate HTML-formatted response.
NGFW Advantages:
1. Combines DPI with malware filtering and other controls to provide an optimal level of filtering
2. Tracks all traffic from Layer 2 to the application layer for more accurate insights than other methods
3. Can be automatically updated to provide current context
NGFW Disadvantages
1. In order to derive the biggest benefit, organizations need to integrate NGFWs with other security systems, which can be a complex process
2. Costlier than other firewall types
<br>

<h2>Why Firewalls are Important:</h2>
Firewalls have been a first line of defense in network security for over 25 years. They establish a barrier between secured and controlled internal networks that can be trusted and untrusted outside networks, such as the Internet. 
<br>
<br>

<h2>Utilities Used:</h2>
- Oracle Virtual Box <br>
- pfSense Community Edition <br>
- 7-Zip File Manager




<h2>Environments Used </h2>
- Windows 10



<h2> Firewall Setup Instructions Lab:</h2>
<p align="center">
We will be using a virtual machine that will act as Firewall <br/>
  <br/>
  <br/>
 1. Head to the pfSense website and download the pfSense Community Edition the ISO file in the below picture. Link:https://www.pfsense.org/download/<br/>
<img src="184.png" height="80%" width="80%" alt="Download Windows 10 ISO File"/>
<br />
<br />
 <p align="center">
2. Once the .iso.gz file is downloaded we will need to zip it by senidng it to acompressed folder , then unzip it  to access the .iso file .  <br/>
<img src="192,195,194,193.png" height="80%" width="80%" alt="Download Windows 10 ISO File"/>
<br />
<br />
Download Oracle Virtual Box. Choose Appropriate Platform Packages. Link:https://virtualbox.org/wiki/Downloads  <br/>
<img src="https://imgur.com/uWG2WwF.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
<br />
<br />
 3. Open VirtualBox and Click the New Icon. <br/> 
<img src=" https://imgur.com/a8VV8Zu.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
<br />
<br /> 
 4. Name the Vitual Machine, Make the type BSD and set version to FreeBSD 64 bit. We can set the Memory Size to default 1024 MB. Set option of Hard Disk to Create Virtual Disk Now.-> Create
 <img src=" 187.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
<br />
<br /> 
 5. Set Hard Disk File Type to VDI (VirtualBox Disk Image) -> Create
  <img src=" 189.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
<br />
<br /> 
 6. Go to settings icon of the Firewall Lab. We set the the VM to Bridge Networkmode to ensure the system has its own IP address vs sharing its IP with my host machine. In Network Tab set Attached to: Bridged Adpater. 
  <img src=" 190.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
    <img src=" 191.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
<br />
<br /> 
 7. Run the Firewall Lab by double clicking it to run. A window to setup the .iso disk we want to use will appear we will choose pfsense file we downloaded earlier. 

  <img src=" mac screenshot.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
    <img src=" .png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
<br />
<br /> 
 8. Follow the steps to insall pfsense.
      <img src=" .png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
<br />
<br /> 
