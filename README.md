<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Computer)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 11 Pro </b> (25H2)

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- Internet Information Services (IIS)
- PHP Manager
- Rewrite Module
- VC Redist
- MySQL
- Heidi SQL
- osTicket v1.15.8
- Link to downloads: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6

<h2>Installation Steps</h2>


<p>
1. The first thing that you will need to do is create a virtual machine in Azure (https://portal.azure.com/). Set up your VM with Windows 11 Pro, version 25H2, and select any size with at least 2 vcpus and 16gbs of memory.
</p>

<p>
<img width="583" height="284" alt="image" src="https://github.com/user-attachments/assets/b9a3fcb6-e502-4c59-a704-3bd1da7f70bd" />

</p>
<br />


<p>
2. After you have created and deployed your new virtual machine, you will connect to it using remote desktop connection app (on windows). To connect to the virtual machine, find the public IP address, and then copy/paste it in the remote desktop connection app. Use the username and password that you set when you created your virtual machine.  



  
</p>
<p>
<img width="626" height="365" alt="image" src="https://github.com/user-attachments/assets/366cb7ca-a8fd-4977-beed-83e1a896c22d" />
<img width="399" height="239" alt="image" src="https://github.com/user-attachments/assets/4d42ba56-fb00-4000-a91b-73a4333449f7" />
</p>
<br />


<p>
3. From your virtual machine, open your control panel. Click "Programs", and select "Turn Windows Features on or off". 
</p>
<br />
<p>
<img width="850" height="477" alt="image" src="https://github.com/user-attachments/assets/c0049960-7e5c-404d-b559-d4a1e58e35c6" />
<img width="850" height="478" alt="image" src="https://github.com/user-attachments/assets/d00ed251-beb3-415d-b1e0-3b6ac0b9fc17" />

</p>

<p>
4. You will need to install/enable IIS in Windows, Web Management Tools, CGI, and Common HTTP Features.
  
  [+] Internet Information Services

  [X] Web Management Tools
  
  [+] World Wide Web Services
  
  [+] Application Development Features
  
  [X] CGI
  
  [X] Common HTTP Features
</p>

<p>
<img width="416" height="725" alt="image" src="https://github.com/user-attachments/assets/c067a664-844a-4da5-b016-2e4714047536" />


</p>
<br />


<p>
To verify that ISS is installed/enabled, go to your browser and search for 127.0.0.1
</p>
<br />
<p>
<img width="700" height="744" alt="image" src="https://github.com/user-attachments/assets/7af08bb5-0fbb-41f2-a1b6-4f56f3c4bbbd" />

</p>

<p>
5. Download the Installation Files (https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) and extract the files to the C drive.
</p>
<p>
6. Install PHP Manager for IIS (PHPManagerForIIS_V1.5.0) from the Installation Files.
</p><p>
7. Install the Rewrite Module (rewrite_amd64_en-US) from the Installation Files.
</p><p>
8. Create a folder in the C drive called PHP.
</p><p>
9. Extract php-7.3.88-nts-Win32-VC15-x86 to the newly created PHP folder.
</p><p>
10. Install VC_redist.x.86 from the Installation Files.
</p><p>
11. Install mysql-5.5.62-win32. In the setup wizard, select "typical setup". Launch configuration wizard, and select "standard configuration".

Make a new password for the root admin. 

<img width="263" height="202" alt="image" src="https://github.com/user-attachments/assets/e62d2be5-4934-4a44-96ee-b20ec3f8c0d9" />

Finish and execute. 

<img width="262" height="201" alt="image" src="https://github.com/user-attachments/assets/2762a99c-e704-4ee2-84c5-ea44d45cfc83" />



</p>
<br />


<p>
12. Open IIS as an administrator, and register PHP. You will need to search for IIS using either the windows search bar, or by clicking the Windows icon and then searching. 

- PHP Manager
  <img width="1002" height="525" alt="image" src="https://github.com/user-attachments/assets/e9e0f912-6caa-4b6a-becf-0a7142f3f0b3" />
- Register new PHP version
  <img width="997" height="523" alt="image" src="https://github.com/user-attachments/assets/ffe05422-b519-4a6c-9120-ab0f930865cb" />
- Provide path to the php executable file. This will be the php-cgi file in the PHP folder you created earlier on the C drive. (C:\PHP\php-cgi.exe)
  <img width="357" height="160" alt="image" src="https://github.com/user-attachments/assets/a410fde5-a272-4ada-a5bd-49c29a11613a" />

- Restart the IIS server
  <img width="1003" height="525" alt="image" src="https://github.com/user-attachments/assets/cb759795-e075-470d-a280-6930a0734e50" />



  
</p>
<br />

<p>
13. "Install" osTicket. Extract osTicket-v1.15.8 from the Installtion Files, and copy the "upload" folder to c:\inetpub\wwwroot, then rename the "upload" folder to "osTicket".

Restart IIS.
</p>
<br />


<p>
14. In IIS, navigate through "sites", "default web site", then "osTicket". Click on osTicket, then on the right column, click "Browse *:80 (http))
</p>
<img width="711" height="369" alt="image" src="https://github.com/user-attachments/assets/3da23959-546e-4a38-a430-5e6382cf8f9b" />
<img width="418" height="377" alt="image" src="https://github.com/user-attachments/assets/c2834f18-5e32-4fa2-98b3-6089b708e846" />

Some of the extentions you will need are not enabled. To enable them, go back to IIS, then from osTicket double click PHP manager, then "Enable or disable an extension".

<img width="709" height="371" alt="image" src="https://github.com/user-attachments/assets/498eb59a-ff06-4f47-a86f-ed87174beaa2" />
<img width="707" height="369" alt="image" src="https://github.com/user-attachments/assets/98c92ab2-dd7d-4378-8fff-e839c21df622" />

There are three extensions we want to enable:

- php_imap.dll

- php_intl.dll

- php_opache.dll
<br />


<p>
15. We will need to rename a file from ost-sampleconfig.php to ost-config.php. This file can be searched for in file explorer. C:\inetpub\wwwroot\osTicket\include

  Once renamed, right click the file -> properties -> security -> advanced -> disable inheritance, and remove all inherited permissions from this object.

  <img width="218" height="279" alt="image" src="https://github.com/user-attachments/assets/05984cb8-d1e6-4ffd-aa78-3c88c94e5232" />

  <img width="414" height="282" alt="image" src="https://github.com/user-attachments/assets/54efa753-9cbc-45df-b82a-f0dc44eea242" />

  <img width="283" height="153" alt="image" src="https://github.com/user-attachments/assets/9b79f6d5-5bf5-4ece-aa14-5a99fc26f501" />

We will now add new permissions. 

Click Add, select a principal, then type "Everyone" in the box. 

<img width="413" height="282" alt="image" src="https://github.com/user-attachments/assets/ab56bf4c-f43b-48cd-b2ba-490092b23db2" />

<img width="493" height="320" alt="image" src="https://github.com/user-attachments/assets/71490868-ff3a-4d69-ae4e-0120039346cb" />

<img width="309" height="185" alt="image" src="https://github.com/user-attachments/assets/6ccb676d-ad21-4df8-93ee-9c64a2f1e944" />

Allow full control, click apply and ok.

<img width="610" height="391" alt="image" src="https://github.com/user-attachments/assets/7ab8126e-532b-44cd-8cb3-680621d3c068" />


<img width="511" height="350" alt="image" src="https://github.com/user-attachments/assets/5a647293-8d2e-4999-898f-c7821452ac63" />

Go back to osTicket in the browser and click continue. You will need to fill out the required fields for osTicket Basic Installation. For now, complete the System Settings and Admin User sections. Note: the email addresses will need to be different.

Before filling out the Database Settings, you will need to install HeidiSQL from the Installation Files. 

<img width="401" height="312" alt="image" src="https://github.com/user-attachments/assets/092b952a-0f20-4f42-809f-7af5096fb37f" />

Create a new session

<img width="467" height="324" alt="image" src="https://github.com/user-attachments/assets/cafa92be-0bb9-4b39-8f4a-fa4eb7598dd5" />

Use the password to connect to your MySQL Server.

<img width="459" height="322" alt="image" src="https://github.com/user-attachments/assets/81ac0816-5b77-4032-a4a2-62b05bebce1b" />

You will now create a new database for osTicket to use: right click where it says "Unnamed", click "Create new", then "Database"

<img width="640" height="397" alt="image" src="https://github.com/user-attachments/assets/3e607179-406a-41f2-b2d0-164bdac51231" />

Back in the browser, complete the Database Settings with your new database details. 

<img width="376" height="246" alt="image" src="https://github.com/user-attachments/assets/d70af737-570d-4692-b046-e62a0267db84" />

<img width="552" height="431" alt="image" src="https://github.com/user-attachments/assets/fca814fa-9f91-43a9-bf34-fbcbfc7ab1df" />

You have successfully installed and setup osTicket!

You can now clean up your files and delete only the setup folder. (c:\inetpub\wwwroot\osTicket\setup).
</p>

