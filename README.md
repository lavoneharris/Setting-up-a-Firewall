<h1>Setting up a Firewall Lab</h1>


<h2>Description</h2>
This Firewall Lab consist of new VM on Oracle Virtual Box,that will act as firewall. We will both create a firewall and set up rules for the firewall that will block a specific IP address. 


<br />


<h2>What is a Firewall:</h2>
As stated by the company Cisco, a firewall is a network security device that monitors incoming and outgoing network traffic and decides whether to allow or block specific traffic based on a defined set of security rules.


A firewall can be hardware, software, software-as-a service (SaaS), public cloud, or private cloud (virtual).

<br />


<h2>Types of Firewalls:</h2>
1. Packet Filtering Firewall<br />
Packet filtering firewalls operate inline at junction points where devices such as routers and switches do their work. However, these firewalls don't route packets; rather they compare each packet received to a set of established criteria, such as the allowed IP addresses, packet type, port number and other aspects of the packet protocol headers. Packets that are flagged as troublesome are, generally speaking, unceremoniously dropped -- that is, they are not forwarded and, thus, cease to exist.<br />
Packet Filtering Firewall Advantages:<br />
1. A single device can filter traffic for the entire network .<br />
2. Extremely fast and efficient in scanning traffic. <br />
3. Inexpensive. <br />
4. Minimal effect on other resources, network performance and end-user experience. <br />
Packet Filtering Firewall Disadvantages: <br />
1. Because traffic filtering is based entirely on IP address or port information, packet filtering lacks broader context that informs other types of firewalls. <br />
2. Doesn't check the payload and can be easily spoofed. <br />
3. Not an ideal option for every network. <br />
4. Access control lists can be difficult to set up and manage. <br />
<br />
2. Circuit-Level Gateway <br />
Using another relatively quick way to identify malicious content, circuit-level gateways monitor TCP handshakes and other network protocol session initiation messages across the network as they are established between the local and remote hosts to determine whether the session being initiated is legitimate -- whether the remote system is considered trusted. They don't inspect the packets themselves, however.
Circuit-Level Gateway Advantages:<br />
1. Only processes requested transactions; all other traffic is rejected. <br />
2. Easy to set up and manage. <br />
3. Low cost and minimal impact on end-user experience. <br />
Circuit-Level Gateway Disadvantages:<br />
1. If they aren't used in conjunction with other security technology, circuit-level gateways offer no protection against data leakage from devices within the firewall. <br />
2. No application layer monitoring. <br />
3. Requires ongoing updates to keep rules current. <br />
<br />
3. Application-Level Gateway (aka Proxy Firewall)<br />
This kind of device, technically a proxy and sometimes referred to as a proxy firewall functions as the only entry point to and exit point from the network. Application-level gateways filter packets not only according to the service for which they are intended -- as specified by the destination port  but also by other characteristics, such as the HTTP request string.While gateways that filter at the application layer provide considerable data security, they can dramatically affect network performance and can be challenging to manage.<br />
Application-Level Gateway Advantages:<br />
1. Examines all communications between outside sources and devices behind the firewall, checking not just address, port and TCP header information, but the content itself before it lets any traffic pass through the proxy.<br />
2. Provides fine-grained security controls that can, for example, allow access to a website but restrict which pages on that site the user can open.<br />
3. Protects user anonymity.<br />
Application-Level Gateway Disadvantages:<br />
1. Can inhibit network performance. <br />
2. Costlier than some other firewall options. <br />
3. Requires a high degree of effort to derive the maximum benefit from the gateway. <br />
4. Doesn't work with all network protocols. <br />
<br />
4. Stateful Inspection Firewall <br />
State-aware devices not only examine each packet, but also keep track of whether or not that packet is part of an established TCP or other network session. This offers more security than either packet filtering or circuit monitoring alone but exacts a greater toll on network performance. A further variant of stateful inspection is the multilayer inspection firewall, which considers the flow of transactions in process across multiple protocol layers of the seven-layer Open Systems Interconnection (OSI) model.<br />
Stateful inspection Firewall Advantages:<br />
1. Monitors the entire session for the state of the connection, while also checking IP addresses and payloads for more thorough security. <br />
2. Offers a high degree of control over what content is let in or out of the network. <br />
3. Does not need to open numerous ports to allow traffic in or out. <br />
4. Delivers substantive logging capabilities. <br />
Stateful inspection Firewall Disadvantages:<br />
1. Resource-intensive and interferes with the speed of network communications. <br />
2. More expensive than other firewall options. <br />
3. Doesn't provide authentication capabilities to validate traffic sources aren't spoofed. <br />
<br />
5. Next-Generation Firewall (NGFW)<br />
A typical NGFW combines packet inspection with stateful inspection and also includes some variety of deep packet inspection (DPI), as well as other network security systems, such as an IDS/IPS, malware filtering and antivirus.While packet inspection in traditional firewalls looks exclusively at the protocol header of the packet, DPI looks at the actual data the packet is carrying. A DPI firewall tracks the progress of a web browsing session and can notice whether a packet payload, when assembled with other packets in an HTTP server reply, constitutes a legitimate HTML-formatted response.<br />
NGFW Advantages:<br />
1. Combines DPI with malware filtering and other controls to provide an optimal level of filtering. <br />
2. Tracks all traffic from Layer 2 to the application layer for more accurate insights than other methods. <br />
3. Can be automatically updated to provide current context. <br />
NGFW Disadvantages <br />
1. In order to derive the biggest benefit, organizations need to integrate NGFWs with other security systems, which can be a complex process. <br />
2. Costlier than other firewall types. <br />
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
<img src="https://imgur.com/T1Aosof.png" height="80%" width="80%" alt="Download Windows 10 ISO File"/>
<br />
<br />
 <p align="center">
2. Once the .iso.gz file is downloaded we will need to unzip it using 7 Zip File Manager to access the .iso file .  <br/>
<img src="https://imgur.com/LO2LAUP.png" height="80%" width="80%" alt="Download Windows 10 ISO File"/>
<img src="https://imgur.com/oKtsFG1.png" height="80%" width="80%" alt="Download Windows 10 ISO File"/>
<img src="https://imgur.com/3hgqElk.png" height="80%" width="80%" alt="Download Windows 10 ISO File"/>
<img src="192,195,194,193.png" height="80%" width="80%" alt="Download Windows 10 ISO File"/>
<br />
<br />
Download Oracle Virtual Box. Choose Appropriate Platform Packages. Link:https://virtualbox.org/wiki/Downloads  <br/>
<img src="https://imgur.com/uWG2WwF.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
<br />
<br />
 3. Open VirtualBox and Click the New Icon. <br/> 
<img src="https://imgur.com/a8VV8Zu.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
<br />
<br /> 
 4. Name the Vitual Machine, Make the type BSD and set version to FreeBSD 64 bit. We can set the Memory Size to default 1024 MB. Set option of Hard Disk to Create Virtual Disk Now.-> Create
 <img src="https://imgur.com/7bnOG2C.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
<br />
<br /> 
 5. Set Hard Disk File Type to VDI (VirtualBox Disk Image) -> Create
  <img src="https://imgur.com/eD3f4tO.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
<br />
<br /> 
 6. Go to settings icon of the Firewall Lab. We set the the VM to Bridge Network mode to ensure the system has its own IP address vs sharing its IP with my host machine. In Network Tab set Attached to: Bridged Adpater. 
  <img src="https://imgur.com/RBN2RnI.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
    <img src="https://imgur.com/4S8LKXz.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
<br />
<br /> 
 7. Run the Firewall Lab by double clicking it to run. A window to setup the .iso disk we want to use will appear we will choose pfsense file we downloaded earlier. 

  <img src="https://imgur.com/05DYmN6.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
<br />
<br /> 
 8. Follow the steps to insall pfsense.
      <img src="https://imgur.com/bFp1LU4.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
      <img src="https://imgur.com/V7pUXia.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
      <img src="https://imgur.com/fuSn8B6.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
      <img src="https://imgur.com/GkShdh6.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
<br />
<br /> 
<br /> 
9.Once the installation is done we will have to shut down the virtual machine. Not doing so would make the VM to run the installer again. To stop this, we need to open the Oracle VirtualbOX Firewall virtual machine settings and remove the .iso file we used for installation. 
 <img src="https://imgur.com/FE89Cxg.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
 <img src="https://imgur.com/cLadsMK.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
<br />
<br /> 
10. Restart the Vm.
11. select option 1 and when asked “Should VLANs be set up now?” type “n”.
  <img src="https://imgur.com/UPQw36X.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
<br />
<br /> 
12. enter a WAN interface name, enter “em0”, and when asked to enter the LAN interface name, don’t enter anything and press Enter. When asked to remove the LAN IP address, type “y”.
      <img src="https://imgur.com/YJqjB2p.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>

<br />
<br /> 
   13. Note the IP address for pfsense ”.
      <img src="https://imgur.com/SJpvAmf.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
<br />
<br /> 
   14. Enter the IP address into your host system in your web broswer to get pfsense login portal.Use the username:admin and the password:pfsense to log into the management console.
      <img src="https://imgur.com/9aRvMHs.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
<br />
<br /> 
 15. Follow the configuration wizard and configure as shown below.
         <img src="https://imgur.com/KjSe6Hi.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
       <img src="https://imgur.com/wRt6hlz.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
       <img src="https://imgur.com/Ozb3Qej.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
       <img src="https://imgur.com/8qWTKR2.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
       <img src="https://imgur.com/kfhQgCi.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
       <img src="https://imgur.com/K7YuKaF.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
       <img src="https://imgur.com/srYSMXr.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
       <img src="https://imgur.com/IO15fmt.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
       <img src="https://imgur.com/xRFCYbx.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>   
       <img src="https://imgur.com/I74U2HL.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
       <img src="https://imgur.com/mOrK2PJ.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>   
       <img src="https://imgur.com/T7L387Y.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
<br />
<br /> 
 <h2>Set Firewall Rules</h2>
<br />
 Properties we set Creating a rule.<br />

 <strong>Action</strong><br />
There are three actions we can take with our firewall rules:<br />
<strong>Pass:<strong> <br />Allow the traffic to pass through the firewall.<br />
<strong>Block:</strong> Prevents the traffic from passing through the firewall by dropping the connection, and not notifying the source IP (known as silent dropping).<br />
<strong>Reject:</strong> Prevents the traffic from passing through the firewall by dropping the connection, and informing the source IP.<br />
Disabled<br />
Ticking this box will disable the rule, meaning that it is not actively used by the firewall, but the rule is not deleted so it can be enabled in the future.<br />
Interface <br />
Choose the interface from which packets must come to match this rule. For this walkthrough, we only have a WAN interface configured.<br />
Address Family<br />
Choose whether the rule applies to IPv4 traffic, IPv6 traffic, or both.<br />
Protocol<br />
Which protocol this rule applies to. For example, we could block TCP traffic but allow UDP traffic. We can also choose to use Any protocol, instead of a specific one.<br />
Source<br />
The source of the network connection the rule will apply to. For example, if we wanted to block connections to Facebook from this network, the source value would be 192.168.1.0/24, with a destination value of Facebook’s IP range.<br />
Destination<br />
The destination of the network connection the rule will apply to. See the example under the Source heading to understand what this means.<br />
Log<br />
We can optionally log traffic that matches this rule. If we were blocking connection to Facebook, we could log when this rule is enforced, allowing us to identify which hosts are attempting to connect to Facebook. In an enterprise, we would push these logs to a SIEM platform for centralized management and alerting.<br />
Description <br />
We can assign a description for this rule. This is a good idea when working in teams, so that other team members can understand what this rule does, and what it’s being used for.<br />
   
