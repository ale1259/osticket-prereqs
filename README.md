<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Create a Resource Group on Azure.
- Create a Virtual Machine(VM) with 2-4 virtual CPUs with it's own VirtualNet(Vnet).
- Having the next installation files:

  -PHP Manager for IIS (PHPManagerForIIS_V1.5.0)

  -Rewrite Module(rewrite_amd64_en-US.msi) 

  -PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip)

  -VC_redist.x86

  -MySQL 5.5.62 (mysql-5.5.62-win32.msi)

  -HeidiSQL

  -osTicket v1.15.8
 - Link for an offline version of the installation files: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6

<h2>Installation Steps</h2>

- First we need to Install/Enable IIS,  for that we need to go to Control Panel->Programs->Turn Windows features on/off.


<img src="https://i.imgur.com/PCoURri.png)" height="40%" width="40%" alt="Disk Sanitization Steps"/>

- Then Internet Information Services->World Wide Web Services->Common HTTP Features and check all of them and in Application Development Features check CGI.

<img src="https://i.imgur.com/6OjOIy8.png)" height="40%" width="40%" alt="Disk Sanitization Steps"/><img src="https://i.imgur.com/vFjouJu.png)" height="40%" width="40%" alt="Disk Sanitization Steps"/>

- From the installation files let's install PHP Manager for IIS (PHPManagerForIIS_V1.5.0) and Rewrite Module(rewrite_amd64_en-US.msi).

- We also need to create the directory C:\PHP.

- From the Installation Files, download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP.

- From the Installation Files, download and install VC_redist.x86.exe.

- From the Installation Files, download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi).

  ->Typical Setup 
->Launch Configuration Wizard (after install) 
->Standard Configuration -> you need a password write it down for later

- Open IIS as an Admin.

- Register PHP from within IIS ->PHP Manager->Register new PHP version->browse for the php-cgi.exe inside C:\PHP
  <img src="https://i.imgur.com/hbwZwnV.png)" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>


- Reload IIS (Open IIS, Stop and Start the server).

- Install osTicket v1.15.8.
- Download osTicket from the Installation Files Folder.
Extract and copy “upload” folder to C:\inetpub\wwwroot.
Within C:\inetpub\wwwroot, Rename “upload” to “osTicket”.
- Reload IIS (Open IIS, Stop and Start the server).
- Go to sites -> Default -> osTicket.
On the right, click “Browse *:80”.

<img src="https://i.imgur.com/Jqu9qyY.png)" height="100%" width="100%" alt="Disk Sanitization Steps"/>

And this window should appear, if so, you have done everything correct.

<img src="https://i.imgur.com/bc3rOHn.png)" height="100%" width="100%" alt="Disk Sanitization Steps"/>

- Rename: ost-config.php

-From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php 

-To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

Assign Permissions: ost-config.php -> Properties -> Security -> Advanced -> Disable inheritance -> Remove All
New Permissions -> Add ->  Everyone -> Full Control -> Apply 


- Note that some extensions are not enabled
  
  -Go back to IIS, sites -> Default -> osTicket
Double-click PHP Manager
Click “Enable or disable an extension”
<img src="https://i.imgur.com/WIk0VD9.png)" height="80%" width="80%" alt="Disk Sanitization Steps"/>

 -Enable: php_imap.dll

 -Enable: php_intl.dll

 -Enable: php_opcache.dll

-Refresh the osTicket site in your browse, observe the changes. Should be like this now.
<img src="https://i.imgur.com/BXByLc5.png)" height="80%" width="80%" alt="Disk Sanitization Steps"/>

- Continue Setting up osTicket in the browser (click Continue)

  -Name Helpdesk
  
  -Default email (receives email from customers)

- From the Installation Files, download and install HeidiSQL. Note is a word document with the link within it to download. 
  
  -Open Heidi SQL
 
  -Create a new session, root/password you like, write it down -> Open
 
 <img src="https://i.imgur.com/RzLWDqv.png)" height="40%" width="40%" alt="Disk Sanitization Steps"/> <img src="https://i.imgur.com/A6Pd7xi.png)" height="46%" width="46%" alt="Disk Sanitization Steps"/>
 
- Create a database called “osTicket”
  
 <img src="https://i.imgur.com/WKdvVmi.png)" height="80%" width="80%" alt="Disk Sanitization Steps"/>

- Continue Setting up osticket in the browser
 -MySQL Database: osTicket
 -MySQL Username: root
- MySQL Password: password you write down
- Click “Install Now!”


Congratulations!!!, hopefully it is installed with no errors and look like this:

<img src="https://i.imgur.com/gn46jB1.png)" height="80%" width="80%" alt="Disk Sanitization Steps"/>


- Browse to your help desk login page: http://localhost/osTicket/scp/login.php

- End Users osTicket URL: http://localhost/osTicket/ 

- !!!!  Clean up
  
   -Delete: C:\inetpub\wwwroot\osTicket\setup

   -Set Permissions to “Read and execute” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php -> Properties -> Security -> Advanced -> select Everyone -> Edit -> Read and execute -> Apply

