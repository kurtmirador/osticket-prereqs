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

- Web Server
  - Configured to support .htacess when using Apache.
- PHP (v8.0-8.1 recommended)
  - Ensured proper PHP configuration.
- MySQL Database (v5.5+ or MariaDB equivalent)
  - Created a dedicated MySQL user and database for osTicket.
  - Used MySQL to store all ticket data, users, settings, etc.
- Download osTicket Source Files
  - Extracted and placed the files in your web server’s root directory.
- osTicket Web Installer
  - Accessed http://localhost/upload (or your domain) to run the installer.
  - Guided through DB setup, admin account creation, and final configuration.

<h2>Installation Steps</h2>

<p>
<img width="1003" alt="Screenshot 2025-04-08 at 3 11 27 PM" src="https://github.com/user-attachments/assets/9570f69c-e5a2-4e4d-8e7d-0ba06666e8d5" />

</p>
<p>
🔹 Step 1: Set Up the Virtual Machine
Description:
Create a Windows 10 VM in Microsoft Azure with 4 vCPUs.

- VM Name: osticket-vm

- Username: labuser

- Password: osTicketPassword1!
Log in using Remote Desktop Protocol (RDP) to begin the setup.
</p>
<br />

<p>
<img width="1440" alt="Screenshot 2025-04-08 at 3 36 18 PM" src="https://github.com/user-attachments/assets/133fa7f8-a821-41a0-9af7-970d2a3337e0" />
</p>
<p>
🔹 Step 2: Prepare the Environment
Description:
Download and extract the osTicket-Installation-Files.zip to your desktop.
Install and configure necessary tools and services:

- Enable IIS with CGI via Windows Features
- Install PHP Manager for IIS
- Install Rewrite Module
- Extract PHP 7.3.8 to C:\PHP
- Install VC++ Redistributable
- Install MySQL 5.5.62 with:
  - Username: root
  - Password: root
</p>
<br />

<p>
<img width="1440" alt="Screenshot 2025-04-08 at 3 53 42 PM" src="https://github.com/user-attachments/assets/7e2ed005-2fce-40b0-a4bd-299a03157c1f" />
</p>
<p>
🔹 Step 3: Configure IIS and PHP
Description:
- Open IIS Manager as Administrator
- Use PHP Manager to register php-cgi.exe from C:\PHP
- Restart IIS
- Unzip osTicket-v1.15.8.zip
- Copy upload folder to C:\inetpub\wwwroot and rename it to osTicket
- Browse to http://localhost/osTicket
</p>
<br />

<p>
<img width="1440" alt="Screenshot 2025-04-08 at 3 48 34 PM" src="https://github.com/user-attachments/assets/f07216f9-872c-4dca-87dc-4d0263223869" />
</p>
<p>
🔹 Step 4: Finalize PHP Extensions & Configuration
Description:
Enable required PHP extensions:
- php_imap.dll, php_intl.dll, php_opcache.dll
Rename:
- ost-sampleconfig.php → ost-config.php
Update file permissions:
- Remove inheritance
- Grant Everyone full access
Delete setup folder after install
Set ost-config.php to Read-Only
</p>
<br />

<p>
<img width="1440" alt="Screenshot 2025-04-08 at 3 49 40 PM" src="https://github.com/user-attachments/assets/713e4b43-501c-43e9-982c-1a2079e5c715" />
<img width="1440" alt="Screenshot 2025-04-08 at 3 50 07 PM" src="https://github.com/user-attachments/assets/eaca5628-3900-4eb4-b072-5a1aecee425d" />
</p>
<p>
🔹 Step 5: Set Up the Database & Complete Installation
Description:
- Install HeidiSQL
- Connect using root/root
- Create database: osTicket
- In browser, finish osTicket setup:
  - Name helpdesk
  - Enter admin email
  - Database: osTicket
  - Username: root, Password: root
After successful installation:
  - Admin Panel: http://localhost/osTicket/scp/login.php
  - End User: http://localhost/osTicket/
</p>
<br />
