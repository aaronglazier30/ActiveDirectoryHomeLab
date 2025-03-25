<h1>Active Directory Home Lab</h1>

 ### [YouTube Demonstration]()...In Progress.

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

<p>Download Server 2019 and Windows 10 as ISO files to your desktop for later:</p>
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
We're going to create a dedicated admin account now/ After you log back in clicl the start menu/ Click "administrator tools"/ Then click "Active Directory users and computers"/ Richt click "mydomain.com"/ Click "New"/ Click "Organizational Unit" aka "OU"/ For the name type in "Admins"/ Click "OK"/ Right click on the "admins" OU we just made/ Click "New"/ Click "Users"/ Type in your first and last name in designated spots/ For User Logon Name put "a-" to signify you're a admin user followed by first letter of first name and last name/ Click "Next"/ For Password: "Password1" and uncheck the box saying "user must change password at next logon" (for lab purposes only)/ Click "Next"/ Click "Finish"<br/>
<img src="https://i.imgur.com/WEwZczD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/2iHWtjI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/kEMvvai.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/MSeF6z1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/1WMq8Ov.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">
Right click the user account we just made in the "admins" OU/ Click "Properties"/ Click "Members of"/ Click "Add"/ Enter "Domain Admins" int the text box/ Click "Check Names" and "Domain Admins" should be underlined now/ Click "OK"/ Click "Apply and "OK"/ Now Click "Start"/ Click the account profile icon/ Click "sign out" <br/>
<img src="https://i.imgur.com/XPaUJTU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/CWFr3um.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/xLySIuS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">
We're going to login on "other users" and use the login info of the admin account we just made/ User: a-aglazier PW: Password1/ Boom! LETS GO! <br/>
<img src="https://i.imgur.com/yTFyOsE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/QBmdNVa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">
Now lets allow access for the client to access the internet through the DC by creating a RAS-NAT/ Go to Server Manager-Dashboard/ Click "Add roles and feautures"/ Click "Next"/ Click "Next"/ Click "Next"/ Select "Remote Access"/ Click "Next"/ Click "Next"/ Click "Next"/ Select "Routing"/ Click "Add Feautures"/ Click "Next"/ Click "Next"/ Click "Next"/ Click "Install"/ Close once it finishes installing.<br/>
<img src="https://i.imgur.com/h9slytb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/6ery6Wj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">
Go to tools on the SM-Dashboard/ Select "Routing and remote access"/ Right click "DC"/ Click "configure and enable routing and remote access"/ Click "next"/ Select "Network address traslation (NAT)"/ Click "next"/ Use the public interface and select the Network we named "_Internet_". IP address starting in '10.'/ Click "Next"/ Click "Finish"<br/>
<img src="https://i.imgur.com/nOQwlFT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/6Tx2fWX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">
Next on the to do list is setting up a DHCP server on our domain controller with scope information allowing our windows 10 clients to get on the internet within a private internal network.<br/>
<p align="center">
Go to SMdashboard/ Click "add roles and feautures"/ Click "Next"/ Click "Next"/ Click "Next"/ Under server roles select "DHCP Server" and "add Feautures"/ Click "Next"/ Click "Next"/ Click "Next"/ Click "Install"/ Go to SM-dashboard "tools"/ Select "DHCP"/ Click and then right click on "IPv4"/ Click "Use Scope"/ Put name as scope range from the diagram in the beginning (172.16.0.100-200)/ Click "Next"/ Enter these IP addresses accordingly; start IP: 172.16.0.100, End IP: 172.16.0.200, Subnet mask: 255.255.255.0/ Click "Next"/ Click "Next"/ For lease dura tion we will leave it alone because this is a lab but this is basically asking what is the duration you want for a client to have a single IP address/ Make sure yes is selected for DHCP config. options for the scope, then click "Next"/ Enter IP address: 172.16.0.1, Click "add" then click "Next"/ Click "Next"/ Click "Next"/ Click "Next"/ Click "Finish" <br/>
<img src="https://i.imgur.com/FWA4lsj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/vnQBW7G.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/e0FjPEy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/T1JPdHB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/kVbIH1H.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/p8fOWa8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">
Right click on the DC server and click "authorize"/ Right click on it again and click "refresh". <br/>
<img src="https://i.imgur.com/pp9LYrc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/uyFNIag.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">
to make life a little easier for us on this lab we're going to turn off internet explorer security, by doing that go to "config local server" on the SM-dashboard/ Click "on" next to "IE Enhanced Security Configuration" turn them off, then click "OK".<br/>
<img src="https://i.imgur.com/9HblfYH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">
Next we will be using a command script on powershell to automate 1000 user accounts.<br/>
<p align="center">
Open up internet explorer/ Paste this Link in - (https://github.com/joshmadakor1/AD_PS/archive/master.zip) / Click "save as"/ Select "desktop"/ Click "Save"/ Go to desktop and right click the file/ open the file and drag the content out to the desktop/ Open the folder and double click "names"/ Add you first and last name to the top of the list then save the file. <br/>
<img src="https://i.imgur.com/fMZPIQW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/CpYhi2u.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">
Click on the start menu/ click on powershell/ Find Powershell ISE then right click on it/ Click "more then click "run as admin."/ find the folder icon on the top right of powershell and click it/ go to desktop/ find the folder we downloaded earlier and click it/ Click on the file named "CREATE USERS" then click "Open".<br/>
<img src="https://i.imgur.com/v0GpUIc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/oae5pzs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/Lm3TLIB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">
We wont be able to run the script just yet because of the execution policy so enter the command "Set-ExecutionPolicy Unrestricted"/ MAke sure you type in the command correctly or it wont work/ a small window should pop up asking are you sure, just click "yes"/ This is a lab so its not that important but in real world environments It would be very important so keep that in mind.<br/>
<img src="https://i.imgur.com/l1diZh4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">
Another thing we have to do before running the script to make it work is doing to the directory that has the list of names/ enter command "cd c:\Users\a-aglazier\Desktop\AD_PS-master"/ Command "ls" to see if the "names.txt" files is there/ Now we can click the green arrow at the top of the powershell to run the script.<br/>
<img src="https://i.imgur.com/dMhJQhq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/P67vMGa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">
After the script is finiosh running if you go to Active Directory Users and Computers you should see a new users Ou filled with users.<br/>
<img src="https://i.imgur.com/kOYaKMX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/ziECymT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">
Lets go back to Virtual box and create a new VM/ CLick "New"/ Name "CLIENT1"/ Type "Microsoft Windows"/ Version "windows 10 (64-bit)"/ Click "Finish"/ Double click the "CLIENT1" VM/ Click "Settings"/ Click "Network"/ Change Attached to: to "Internal Network"/ Click "OK"/ Start the VM/ Click the dropdown tab on DVD and select "other"/ Find the windows 10 ISO we downloaded earlier and click "Open"/ Click "mount and retry boot".<br/>
<img src="https://i.imgur.com/arvHRbD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/HLRlDJj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/RZnTHYw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">
Select "English" or preferred language then click "Next"/ Click "Install now"/ Click "I dont have a product key"/ Select "Windows 10 Pro" then click "Next"/ Accept the licewnse then click "Next"/ Select "Custom install windows only"/ Click "Next"<br/>
<img src="https://i.imgur.com/PkCrq6D.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/AlcmcOU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/0GAaJqu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/NkaUwEZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">
When it finishes installing click "Next"/ Click "yes"/ Click "Skip"/ Click "i dont have internet"/ Click "Continue with limited setup"/ For name pt "user"/ Click "next"/ Click "Next"/ Turn all the settings to "no" then click "accept"/ Click "not now"/ Go to command prompt and type in "ipconfig" to verify connection/ Right click thestart menu/ Click "Rename this PC(advanced)"/ Click "Change"/ For computer name insert "CLIENT1"/ for domain insert "mydomain.com"/ Then you can log into your admin or user account, lets do user (aglazier) pw (Password1)/ Then restart computer.<br/>
<img src="https://i.imgur.com/JOIXmC2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/AlcmcOU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/HtG0Gt2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/ZBZy4QI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/QBrQPbs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">
If you go to our DC desktop/ Go to "Active directory Users and Computers"/ Click the domain drop down and click on "computers" you can see Our client computer is connected to the domain.<br/>
<img src="https://i.imgur.com/yQYadOf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">
Now lets go back to the Client1 desktop and check it/ CLick "other users"/ Login with user acc. info. (aglazier) (Password1)/ Open Command Prompt/ Type im "whoami" it should show youre connected to the domain.<br/>
<img src="https://i.imgur.com/s9NHx8A.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>




