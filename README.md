<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Physical Machine (Windows or Mac)
- Azure Tenant (Free Subscription)
- Remote Desktop Application (if using Mac)
- Internet Connection


<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/s3LxRRA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
First step is to create a new resource group within Azure.
</p>
<br />

<p>
<img src="https://i.imgur.com/ipkKL2J.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Name your resource group and select your region. Then click on "Review + create". Then click "Create"
</p>
<br />

<p>
<img src="https://i.imgur.com/8T5Xq7a.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once your resource group is created, search "virtual machine" in the search bar and click on "Virtual machines"
</p>
<br />

<p>
<img src="https://i.imgur.com/z0jaAui.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once you click "virtual machines", click on "Create" then click "Azure virtual machine"
</p>
<br />

<p>
<img src="https://i.imgur.com/ExhsHrZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Select your resource group you previously created, then name your virtual machine, then select "Windows 10 Pro, version-21H2", then select "Standard_E2s_v3", then enter a username and password for the administrator account, then check the box for Licensing, then click, "Review + create", then click "Create" once validation is passed.
</p>
<br />

<p>
<img src="https://i.imgur.com/pDt82qW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once your virtual machine is created, find the Public IP address of the virtual machine by selecting "virtual machines" in the search bar then clicking on "osTicket"

Copy the Public IP address then open "Remote Desktop Connection" on your physical machine.
</p>
<br />

<p>
<img src="https://i.imgur.com/BVck2IU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Enter the copied Public IP address of the virtual machine and select "Connect".

Once prompted with the "Enter your credentials", enter the username and password you set when you were creating the virtual machine, then click "OK",  then select "Yes" when Windows warns you about the certificate error.
</p>
<br />

<p>
<img src="https://i.imgur.com/sZFpM7c.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once you are in your virtual machine, navigate to "Microsoft Edge", then enter "https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6" into the URL to download all the installation files. 

Once you have all the files downloaded, you will need to extract them from the zipped folders and then you will have all the prequisites downloaded.
</p>
<br />

<p>
<img src="https://i.imgur.com/LcC76j0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
We will enable Internet Information Services (IIS) on the virtual machine. 

Go to control panel and then select "Turn Windows features on or off", then select the box beside "Internet Information Services" then select the box beside "CGI", then click "OK"

Now you have IIS enabled.
</p>
<br />

<p>
<img src="https://i.imgur.com/O5v2isE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
We will now install some of the files from the Installation Files folder. 

Double click and run the setups for "PHPManagerForIIS_V1.5.0.msi" and "rewrite_amd64_en-US.msi"
</p>
<br />

<p>
<img src="https://i.imgur.com/sO6m0P2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Navigate to File Explorer and then to "This PC" then to "Windows (C:)" then create a new folder named "PHP".
</p>
<br />

<p>
<img src="https://i.imgur.com/IwYOMc6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the Installation Files folder, we will drag the "php-7.3.8-nts-Win32-VC15-x86" folder into the new folder we created named "PHP".

Next, from the Installation Files folder, we will execute "VC_redist.x86.exe" and "MySQL-5.5.62-win32"

"MySQL-5.5.62-win32" will follow this setup: Typical Setup --> Launch Configuration Wizard (after install) --> Standard Configuration --> Password1
</p>
<br />

<p>
<img src="https://i.imgur.com/KgBgiB1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After the installation, search "Internet Information Services (IIS) Manager" in the Windows search bar and run the manager as administrator. Then double click "PHP Manager" from within IIS Manager.
</p>
<br />

<p>
<img src="https://i.imgur.com/B9yrzLz.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once you have double clicked "PHP Manager", click "Register new PHP version", then click the "..." box to browse to the PHP folder we previously created and dragged the installation file into, then select "php-cgi" as the file, then click open, then click "OK"
</p>
<br />

<p>
<img src="https://i.imgur.com/R0nbLRR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once you have selected the PHP file, click "osTicket (osTicket\osTicketUser)" then click on "Restart" to restart the server.
</p>
<br />

<p>
<img src="https://i.imgur.com/lw5z7jL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now onto installing osTicket v1.15.8. First drag the "upload" folder from the Installation Files into C:\inetpub\wwwroot, then rename the "upload" folder to "osTicket"
</p>
<br />

<p>
<img src="https://i.imgur.com/R0nbLRR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Restart the "osTicket" server once more.
</p>
<br />

<p>
<img src="https://i.imgur.com/1vH01BA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once you have restarted the server, to enable the essential extensions for the osTicket setup, we must enable some more extensions that are not enabled by default. Click on "osTicket" in IIS, then double click on "PHP Manager", then click on "Enable or disable an extension"
</p>
<br />

<p>
<img src="https://i.imgur.com/wrWvu0i.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Right click on "php_imap.dll" and left click on "Enable". Repeat this process for "php_intl.dll" and "php_opcache.dll"
</p>
<br />

<p>
<img src="https://i.imgur.com/2mtNGS8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go back to IIS and click on the arrow to expand "Sites", then click on the arrow to expand "Default Web Site" then click on the "osTicket" folder, then click on "Browse *:80 (http)", then you should be taken to Microsoft Edge and have the "osTicket Installer" webpage opened.
</p>
<br />

<p>
<img src="https://i.imgur.com/Uy2VJRs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Navigate to "C:\inetpub\wwwroot\osTicket\include" then rename the file "ost-sampleconfig.php" to "ost-config.php"
</p>
<br />

<p>
<img src="https://i.imgur.com/iGAWNGM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After you have renamed the file, right click "os-config.php" then click "Properties", then click on the "Security" tab, then click "Advanced" within the Security tab, then click "Disable inhertiance", then click "Remove all inherited permissions from this object."
</p>
<br />

<p>
<img src="https://i.imgur.com/GwYQs18.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once you have removed inheritance, you will click "Add" then click "Select a principal", then type "Everyone" into the "Enter the obbject name to select" prompt, then click "Check Names", then click "OK", then click "OK" once more. 

In the next prompt, select the box beside "Full control", then click "OK", then click "OK" within "ost-config.php Properties"

Then click "Apply", then click "OK"
</p>
<br />

<p>
<img src="https://i.imgur.com/DaEJ8HH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go back to Microsoft Edge and you should still have the "osTicket Installer" webpage open.

Click "Continue >>"

Fill out all the boxes in red and make sure to write down this information because you will need it later.
</p>
<br />

<p>
<img src="https://i.imgur.com/dAbmm0k.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go back to the Installation Files folder then open the text file for the "HeidiSQL_12.3.0.6589_Setup.exe" then click the link "https://www.heidisql.com/installers/HeidiSQL_12.3.0.6589_Setup.exe" to download the setup file.

Run through the setup.exe file and then click "Finish" to open HeidiSQL. Then click on "Skip" when HeidiSQL opens.

</p>
<br />

<p>
<img src="https://i.imgur.com/PwEK6SU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
