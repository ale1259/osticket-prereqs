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

- Create a Resource Group on Azure
- Create a Virtual Machine(VM) with 2-4 virtual CPUs with it's own VirtualNet(Vnet)
- Having the next installation files:
  - PHP Manager for IIS (PHPManagerForIIS_V1.5.0)
  -  Rewrite Module(rewrite_amd64_en-US.msi) 
  -  PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip)
  -  VC_redist.x86
  -  MySQL 5.5.62 (mysql-5.5.62-win32.msi)
  -  HeidiSQL
  -  osTicket v1.15.8
 - Link for an offline version of the installation files: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6

<h2>Installation Steps</h2>
First we need to Install/Enable IIS,  for that we need to go to Control Panel->Programs->Turn Windows features on/off

<p>
<img src="https://i.imgur.com/PCoURri.png)" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
Then Internet Information Services->World Wide Web Services->Common HTTP Features and check all of them and in Application Development Features check CGI
</p>
<br />

<p>
<img src="https://i.imgur.com/6OjOIy8.png)" height="40%" width="40%" alt="Disk Sanitization Steps"/><img src="https://i.imgur.com/vFjouJu.png)" height="40%" width="40%" alt="Disk Sanitization Steps"/>
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
