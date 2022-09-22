<h1>Setting up a Firewall Lab</h1>


<h2>Description</h2>
This Firewall Lab consist of new VM on Oracle Virtual Box,that will act as firewall. We will both create a firewall and set up rules for the firewall that will block a specific IP address. 


<br />


<h2>What is a Firewall:</h2>
As stated by the company Cisco, a firewall is a network security device that monitors incoming and outgoing network traffic and decides whether to allow or block specific traffic based on a defined set of security rules.


A firewall can be hardware, software, software-as-a service (SaaS), public cloud, or private cloud (virtual).

<br />


<h2>Types of Firewalls:</h2>
<strong>1. Packet Filtering Firewall</strong><br />
Packet filtering firewalls operate inline at junction points where devices such as routers and switches do their work. However, these firewalls don't route packets; rather they compare each packet received to a set of established criteria, such as the allowed IP addresses, packet type, port number and other aspects of the packet protocol headers. Packets that are flagged as troublesome are, generally speaking, unceremoniously dropped -- that is, they are not forwarded and, thus, cease to exist.<br />
<strong>Packet Filtering Firewall Advantages:</strong><br />
1. A single device can filter traffic for the entire network .<br />
2. Extremely fast and efficient in scanning traffic. <br />
3. Inexpensive. <br />
4. Minimal effect on other resources, network performance and end-user experience. <br />
<strong>Packet Filtering Firewall Disadvantages:</strong> <br />
1. Because traffic filtering is based entirely on IP address or port information, packet filtering lacks broader context that informs other types of firewalls. <br />
2. Doesn't check the payload and can be easily spoofed. <br />
3. Not an ideal option for every network. <br />
4. Access control lists can be difficult to set up and manage. <br />
<br />
<strong>2. Circuit-Level Gateway </strong><br />
Using another relatively quick way to identify malicious content, circuit-level gateways monitor TCP handshakes and other network protocol session initiation messages across the network as they are established between the local and remote hosts to determine whether the session being initiated is legitimate -- whether the remote system is considered trusted. They don't inspect the packets themselves, however.<br />
<strong>Circuit-Level Gateway Advantages:</strong><br />
1. Only processes requested transactions; all other traffic is rejected. <br />
2. Easy to set up and manage. <br />
3. Low cost and minimal impact on end-user experience. <br />
<strong>Circuit-Level Gateway Disadvantages:</strong><br />
1. If they aren't used in conjunction with other security technology, circuit-level gateways offer no protection against data leakage from devices within the firewall. <br />
2. No application layer monitoring. <br />
3. Requires ongoing updates to keep rules current. <br />
<br />
<strong>3. Application-Level Gateway (aka Proxy Firewall)</strong><br />
This kind of device, technically a proxy and sometimes referred to as a proxy firewall functions as the only entry point to and exit point from the network. Application-level gateways filter packets not only according to the service for which they are intended -- as specified by the destination port  but also by other characteristics, such as the HTTP request string.While gateways that filter at the application layer provide considerable data security, they can dramatically affect network performance and can be challenging to manage.<br />
<strong>Application-Level Gateway Advantages:</strong><br />
1. Examines all communications between outside sources and devices behind the firewall, checking not just address, port and TCP header information, but the content itself before it lets any traffic pass through the proxy.<br />
2. Provides fine-grained security controls that can, for example, allow access to a website but restrict which pages on that site the user can open.<br />
3. Protects user anonymity.<br />
<strong>Application-Level Gateway Disadvantages:</strong><br />
1. Can inhibit network performance. <br />
2. Costlier than some other firewall options. <br />
3. Requires a high degree of effort to derive the maximum benefit from the gateway. <br />
4. Doesn't work with all network protocols. <br />
<br />
<strong>4. Stateful Inspection Firewall</strong> <br />
State-aware devices not only examine each packet, but also keep track of whether or not that packet is part of an established TCP or other network session. This offers more security than either packet filtering or circuit monitoring alone but exacts a greater toll on network performance. A further variant of stateful inspection is the multilayer inspection firewall, which considers the flow of transactions in process across multiple protocol layers of the seven-layer Open Systems Interconnection (OSI) model.<br />
<strong>Stateful inspection Firewall Advantages:</strong><br />
1. Monitors the entire session for the state of the connection, while also checking IP addresses and payloads for more thorough security. <br />
2. Offers a high degree of control over what content is let in or out of the network. <br />
3. Does not need to open numerous ports to allow traffic in or out. <br />
4. Delivers substantive logging capabilities. <br />
<strong>Stateful inspection Firewall Disadvantages:</strong><br />
1. Resource-intensive and interferes with the speed of network communications. <br />
2. More expensive than other firewall options. <br />
3. Doesn't provide authentication capabilities to validate traffic sources aren't spoofed. <br />
<br />
<strong>5. Next-Generation Firewall (NGFW)</strong><br />
A typical NGFW combines packet inspection with stateful inspection and also includes some variety of deep packet inspection (DPI), as well as other network security systems, such as an IDS/IPS, malware filtering and antivirus.While packet inspection in traditional firewalls looks exclusively at the protocol header of the packet, DPI looks at the actual data the packet is carrying. A DPI firewall tracks the progress of a web browsing session and can notice whether a packet payload, when assembled with other packets in an HTTP server reply, constitutes a legitimate HTML-formatted response.<br />
<strong>NGFW Advantages:</strong><br />
1. Combines DPI with malware filtering and other controls to provide an optimal level of filtering. <br />
2. Tracks all traffic from Layer 2 to the application layer for more accurate insights than other methods. <br />
3. Can be automatically updated to provide current context. <br />
<strong>NGFW Disadvantages:</strong> <br />
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
 1. Head to the pfSense website and download the pfSense Community Edition the ISO file in the below picture. Link: https://www.pfsense.org/download/<br/>
<img src="https://imgur.com/T1Aosof.png" height="80%" width="80%" alt="Download Windows 10 ISO File"/>
<br />
<br />
 <p align="center">
2. Once the .iso.gz file is downloaded, we will need to extract it using 7 Zip File Manager to access the .iso file.  <br/>
<img src="https://imgur.com/LO2LAUP.png" height="80%" width="80%" alt="Download Windows 10 ISO File"/>
<img src="https://imgur.com/oKtsFG1.png" height="80%" width="80%" alt="Download Windows 10 ISO File"/>
<img src="https://imgur.com/3hgqElk.png" height="80%" width="80%" alt="Download Windows 10 ISO File"/>
<br />
<br />
Download Oracle Virtual Box. Choose Appropriate Platform Packages (necessary for your environment). Link:https://virtualbox.org/wiki/Downloads  <br/>
<img src="https://imgur.com/uWG2WwF.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
<br />
<br />
 3. Open VirtualBox and Click the New Icon. <br/> 
<img src="https://imgur.com/a8VV8Zu.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
<br />
<br /> 
 4. Give the Vitual Machine a name,set the type BSD, set version to FreeBSD 64 bit. We can set the Memory Size to default 1024 MB. Lastly set option of Hard Disk to Create Virtual Disk Now.-> Create
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
 7. Run the Firewall Lab by double clicking it to run. A window to setup the .iso disk we want to use will appear, we will choose pfsense file we downloaded and extracted earlier. 
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
9. Once the installation is done we will have to shut down the virtual machine. (Note: Not doing so would make the VM to run the installer again.) To stop this, we need to open the Oracle VirtualbOX Firewall virtual machine settings and remove the .iso file we used for installation. 
 <img src="https://imgur.com/FE89Cxg.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
 <img src="https://imgur.com/cLadsMK.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
<br />
<br />
<p align="center">
10. Now Restart the VM.
  <p align="center">
   <img src="https://imgur.com/RBN2RnI.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
   <br />
<br /> 
11. Choose option 1 and when asked “Should VLANs be set up now?” type “n”.
  <img src="https://imgur.com/UPQw36X.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
<br />
<br /> 
12. <br /> Step 1: Enter a WAN interface name.<br /> Step 2: Enter “em0”, and when asked to enter the LAN interface name, don’t enter anything and press Enter. <br /> Step 3: When asked to remove the LAN IP address, type “y”.
      <img src="https://imgur.com/YJqjB2p.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
<br />
<br /> 
   13. Note the IP address for pfsense.
      <img src="https://imgur.com/SJpvAmf.png" height="80%" width="80%" alt="Download Oracle Virtual Box"/>
<br />
<br /> 
   14. Enter the IP address into your host system in your web broswer to get to the pfsense login portal.U se the username:admin and the password:pfsense to log into the management console.
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
 Properties we set Creating a rule.<br />

 <strong>Actions:</strong> There are three actions we can take with our firewall rules:<br />
 <strong>Pass: </strong> Allow the traffic to pass through the firewall.<br />
<strong>Block:</strong> Prevents the traffic from passing through the firewall by dropping the connection, and not notifying the source IP (known as silent dropping).<br />
<strong>Reject:</strong> Prevents the traffic from passing through the firewall by dropping the connection, and informing the source IP.<br />
<strong>Disabled:</strong> Ticking this box will disable the rule, meaning that it is not actively used by the firewall, but the rule is not deleted so it can be enabled in the future.<br />
<strong>Interface:</strong> Choose the interface from which packets must come to match this rule. For this walkthrough, we only have a WAN interface configured.<br />
<strong>Address Family:</strong> Choose whether the rule applies to IPv4 traffic, IPv6 traffic, or both.<br />
<strong>Protocol::</strong> Which protocol this rule applies to. For example, we could block TCP traffic but allow UDP traffic. We can also choose to use Any protocol, instead of a specific one.<br />
<strong>Source:</strong> The source of the network connection the rule will apply to. For example, if we wanted to block connections to Facebook from this network, the source value would be 192.168.1.0/24, with a destination value of Facebook’s IP range.<br />
<strong>Destination:</strong> The destination of the network connection the rule will apply to. See the example under the Source heading to understand what this means.<br />
<strong>Log:</strong> We can optionally log traffic that matches this rule. If we were blocking connection to Facebook, we could log when this rule is enforced, allowing us to identify which hosts are attempting to connect to Facebook. In an enterprise, we would push these logs to a SIEM platform for centralized management and alerting.<br />
<strong>Description:</strong> We can assign a description for this rule. This is a good idea when working in teams, so that other team members can understand what this rule does, and what it’s being used for.<br />
   


 <p align="center">
1. In the pfsense interface go to Firewall > click Rules. (Note: There arent any firewall rules by default as a precaution.)  <br/>
<img src="https://imgur.com/tgsFlNQ.png" height="80%" width="80%" alt="Download Windows 10 ISO File"/>
<br />
<br />
2. Now we will create a rule to block the domain, Youtube.com. (Note: We can choose any domain for this exercise) Next open a Command Prompt as Admin on your Windows system, or a terminal on a Kali Linux virtual machine, and type ping Youtube.com. You can instantly press CTRL+C to stop pinging. You now have the IP address of Youtube.com please note it. (142.250.80.14)
<img src="https://imgur.com/S3DouQx.png" height="80%" width="80%" alt="Download Windows 10 ISO File"/>
<br />
<br /> 
 3. Now go back to the top of the pfsense interface and go to Firewall > Alias. Aliases acts as placeholders for real hosts, networks or ports. They can be used to minimize the number of changes that have to be made if a host, network or port changes. For example, if we create an Alias for a site we want to block, we can use that as the source or destination within firewall rules. If the IP of the site changes, we only need to change the Alias instead of every single rule. In the below screenshot we have set a name and the IP address of Youtube.com.
  <img src="250.png" height="80%" width="80%" alt="Download Windows 10 ISO File"/>
    <img src="251.png" height="80%" width="80%" alt="Download Windows 10 ISO File"/>
    <img src="252.png" height="80%" width="80%" alt="Download Windows 10 ISO File"/>
<br />
<br /> 
4. Next lets create a firewall rule that will block any host in our network connecting to YouTube.com. Follow the below set up and save.
Explanation of values:<br />
<strong>Action:</strong> Block – we want to block traffic to Redhunt.net <br />
<strong>Protocol:</strong> Any – we want to block all traffic (alternatively, we could choose to just block http (TCP 80) and https (TCP 443)).<br />
<strong>Source:</strong> Network, 192.168.1.0/24 – we want to enforce this rule for any system on our private home network.<br />
<strong>Destination:</strong> Single host or alias, YoutubeDOTCom (the alias we created earlier for the IP address of the website).<br />
   <img src="253.png" height="80%" width="80%" alt="Download Windows 10 ISO File"/>
<br />
<br />    
Note: So far the Firewall is currently constructed, we have all traffic iblocked by default with pfSense, so therefore we have two rules.<br />
Block ANY traffic to Youtube.com (142.250.80.14)<br />
Block ANY traffic <br />
 

Note: If we change the default gateway on our host system, we will have absolutely no internet connection, because pfSense is blocking everything. We need to create something known as an ALLOW ALL rule. Remember that your host is  running a local web application firewall, which will still work to block malicious traffic. This rule means that pfSense allows communications to come in and out from the internet, giving us a connection. <br />
Note: Firewalls follow a hierarchy when it comes to rules, working from the top down. This means pfSense will inspect the traffic and apply the rules in the following order: <br />
1. Firewall sees that Redhunt.net is blocked. If the packet is attempting to reach out to 3.11.197.46, drop the packet to prevent the connection. <br />
2. Firewall sees that all traffic is allowed. <br />

5. Create a allow rule. Follow the settings below.<br />
Note: Make sure the allow rule is placed below the Youtube.com blocking rule, when the we change the default gateway we will lose our internet connection until it is restored.
   <img src="254.png" height="80%" width="80%" alt="Download Windows 10 ISO File"/>
    <img src="255.png" height="80%" width="80%" alt="Download Windows 10 ISO File"/>
<br />
<br />  
6. Be sure to click Apply Changes.
     <img src="255.png" height="80%" width="80%" alt="Download Windows 10 ISO File"/>
<br />
<br />
8.  What we need to do is on our host system we need to gather our Ip address, Default Gateway, and DNS server. For example our host IP is 192.168.1.220, our default gateway to the internet is 192.168.1.254, and our DNS server is 192.168.1.254 (same as the gateway). The host is sending traffic from 192.168.1.220 to 192.168.1.254, then out to the internet. See diagram for example:
      <img src="https://imgur.com/3e24IRk.png" height="80%" width="80%" alt="Download Windows 10 ISO File"/>
      <img src="u1.png" height="80%" width="80%" alt="Download Windows 10 ISO File"/>
<br />
<br />
9. Our pfSense has the default gateway we assigned earlier, which is 192.168.1.1. Sometimes your router will sit at .1 in home networks, but in some cases, it is at .254. What you may need to do is:<br />
1. Tell our host system to use the pfSense virtual machine (192.168.1.251) as its default gateway. Traffic outbound for the internet will now go to pfSense.<br />
2. Tell our pfSense VM to use the router (192.168.1.254) as its default gateway, giving it internet connectivity.<br />
Diagram of what it should look like:<br />
<img src="u2.png" height="80%" width="80%" alt="Download Windows 10 ISO File"/>
  <br />
  <br />
10. Go in pfSense and change the default gateway in pfSense from 192.168.1.1 to the correct value, 192.168.1.254. Click Add New Gateway. 
  <img src="https://imgur.com/41ZqBC6.png" height="80%" width="80%" alt="Download Windows 10 ISO File"/>
  <br />
  <br />
  
11.  In the Windows 10 use the command Windows button + r  The following popup will display enter in “ncpa.cpl” and press enter. 
  You should see something similar to the below screenshot. Our ethernet network connection in this example is shown in the top right, as Keenetic=4693.
  <img src="257.png" height="80%" width="80%" alt="Download Windows 10 ISO File"/>
   <img src="https://imgur.com/GgGi1AF.png" height="80%" width="80%" alt="Download Windows 10 ISO File"/>
  <br />
  <br />
12.Right-click on your primary connection, and select “Properties”. Find the line that reads “Internet Protocol Version 4”, and double left-click to open a new window, shown below. Here we can change from “obtain an IP address automatically” and “obtain DNS server address automatically” to set the values we need from our pfSense system. We have shown the before and after screenshots below.   <br />
<br />
  Before:
   <img src="https://imgur.com/skqFbY5.png" height="80%" width="80%" alt="Download Windows 10 ISO File"/>
  <br />
  <br />
 After:
    <img src="https://imgur.com/nhCz5PM.png" height="80%" width="80%" alt="Download Windows 10 ISO File"/>
  <br />
  <br />
 13. Now lets try and go Youtube.Com if sucessful we should not be able to reach the address meaning our Firewall was a success !
      <img src="https://imgur.com/EPI4vwj.png" height="80%" width="80%" alt="Download Windows 10 ISO File"/>
  <br />
  <br />
