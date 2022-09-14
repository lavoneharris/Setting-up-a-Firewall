# Setting-up-a-Firewall
<h1>Setting up a Firewall Lab</h1>


<h2> Reference : </h2>

<h2>Description</h2>

<br />


<h2>What is a Firewall:</h2>

<br />


<h2>Types of Firewalls:</h2>



<h2>Why Firewalls are Important:</h2>
<br>
<br>

<h2>Utilities Used:</h2>
- Oracle Virtual Box <br>
- pfSense Community Edition <br>
- 7Zip <br>



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
2. Once the .iso file is downloaded we will need to unzip it to access the .iso file (IF NEEDED). You can use the program 7Zip to extract the files. Link:https://www.7-zip.org/download.html  <br/>
<img src="185.png" height="80%" width="80%" alt="Download Windows 10 ISO File"/>
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
