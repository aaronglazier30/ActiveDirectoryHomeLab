<h1>Active Directory Home Lab</h1>

 ### [YouTube Demonstration](https://youtu.be/7eJexJVCqJo)

<h2>Description</h2>
This guide provides step-by-step instructions on setting up a Domain Controller, creating 1,000 user accounts, and establishing a Internal Network Infrastructure. Designed to simulate a corporate environment, it leverages Oracle VirtualBox to run the lab, making it an ideal resource for IT professionals or aspiring administrators to gain hands-on experience with Active Directory, user management, and network configuration.


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b>
- <b>Active Directory</b>
- <b>[Oracle Virtual Box](https://www.virtualbox.org/wiki/Downloads)</b>
  

<h2>Environments Used </h2>

- [Server 2019 ISO](https://www.microsoft.com/en-us/evalcenter/download-windows-server-2019)
- [Windows 10 ISO](https://www.microsoft.com/en-us/software-download/windows10)

<h2>Program walk-through:</h2>

<p align="center">
This is a diagram of the environment we will be simulating: <br/>
<img src="https://i.imgur.com/JVLb2sJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">
Download Server 2019 and Windows 10 as ISO files to your desktop for later:<br/>
<img src="https://i.imgur.com/NTO3kNu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">
Open Oracle Virtual Box/ Click 'New"/ Name it "DC"/ For Type: Microsoft Windows/ For Version: Windows Server 2019 (64-bit)/ Click "Finish".<br/>
<img src="https://i.imgur.com/ZCtyCIw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/HhEK60r.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">
Now right click on the VM we just named "DC"(mine is named "DC2" because I already had a VM named "DC")/ Click "Settings"/ Click "Network"/ Click "Adapter 2"/ Check the box to enable Network Adapter by clicking it/ For Attached to: Internal Network/ Click "OK".<br/>
<img src="https://i.imgur.com/5WVdyF0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/MuoTckU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">
Nows the fun part, double click the VM named "DC" to start it/ When the window pops up it will say DVD not selected/ Click the dropdown tab/ Select "other"/ Find the ISO file of Server 2019 that you downloaded and select it/ Click "Open"/ Click "Mount and Retry boot".<br/>
<img src="https://i.imgur.com/zdjilEX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/BMkkXYs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">
Select "English" or preferred launguage/ Click "Next"/ Click "Install"/ for Windows Set up select: Standard Evaluation(Desktop Expewrience) so we have a GUI/ Select "Custom windows install only"/ Click "Next"/ Click "Next".<br/>
<img src="https://i.imgur.com/ZQVeg5k.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/MA5jD2U.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/QSlRhcT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/cJUJodE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/j7W1cfS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">
After it Installs and reboots you should see a Customize Settings screen prompting you to create a password/ Enter: "Password1" (for lab purposes)/ Click "Finish"/ In order to unclock the windows screen right click the down arrow on the bottom right side of the VM/ Click "Insert Ctrl-Atl-Del"/ Enter the password we created "Password1"/ "Enter", and we're in! (The Server Manager Dashboard will pop up on its own)<br/>
<img src="https://i.imgur.com/wDZwoJh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/xdY0mx1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/dIcGlvL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/81kxaj9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">
Lets start off by Renaming the Desktop to DC/ Right click the start menu/ Click "Systems"/ click "Rename this PC"/ Name it "DC"/ Click "Next"/ Click "Restart now"/ Click "Continue".<br/>
<img src="https://i.imgur.com/bhTSl1l.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/e3r3bDz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/SmuhHMm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">
Before we assign an IP address to the Internal network lets identify which network is which/ Click the Network icon/ click "Network & Internet Settings"/ Click "Change Adapter Options"/ Right click the first Network/ Click "Status"/ Click "Details"/ IF the IPv4 address starts with "10." then it should be your home internet connection.<br/>
<img src="https://i.imgur.com/xUygiXw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/T9l6BFO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/d4yQI7L.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/C2X6s8K.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/JpM2J9j.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">
Lets Rename it/ Right click the Network we just identified/ Click "Rename"/ Type in "_Internet_"/ "Enter".<br/>
<img src="https://i.imgur.com/EAau1xb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">
Just to Verify lets do the same thing to the other Newtwork/ The autoconfiguration IPv4 starts with "169." so this looks like our internal network, lets rename it "X__Internal_X". <br/>
<img src="https://i.imgur.com/YiwHokT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/uohhWfY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">
Lets go ahead and assign an IP address to the intrernal network/ On the same screen right click the internal network/ Click "properties"/ Double Click "IPv4(TCP/IPv4)"/ Click "Use the following IP address"/ Now enter the IP, Mask, and DNS from the diagram in the begining of the walk-through under the Internal NIC/ Click "OK"/ Click "OK".<br/>
<img src="https://i.imgur.com/lMHFnyI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/d4qsKms.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">
Lets Create a Domain-AD DS/ Go to the Sewrver manager dashboard/ Click "Add roles and feautures"/ Click "Next"/ Click "Next"/ Click the server named "DC"/ Click "Active Directory Domain Services"/ Click "Next"/ Click "Next"/ Click "Next"/ Click "Install"/ Click "Close"/ Now click the notification flag icon on the top right of the dashboard/ Click "Promote this server to a Domain Controller"/ Click "add a new forest"/ for thr root domain name put "mydomain.com" (for lab purposes)/ Click "Next"/ For the password put "Password1"/ Click "Next"/ Click "Next"/ Click "Next"/ Click "Next"/ Click "Install"/ After it installs it should restart.<br/>
<img src="https://i.imgur.com/R4hT2Th.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/SOPZx6U.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/bYqQ2pR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/fZeSfAj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/eFitq7N.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/VCVWhqh.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/GZF4SAg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/FDJI5sN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">
We're going to create a dedicated admin account now/ <br/>



